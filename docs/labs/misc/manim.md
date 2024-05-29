---
sidebar_position: 1
---

# Manim for Animated Videos

[Manim](https://github.com/3b1b/manim) is a Python library used to create high-precision math and computer science animated videos.

Manim can be difficult to install so this tutorial will teach you how to run it more simply using a Docker container.

## Setup

<ol>
  <li><p>The first thing you're going to need is Docker. If you don't already have docker, you can download it <a href="https://docs.docker.com/get-docker/">here</a>.</p></li>
  <li><p>Pull the docker image for manim:</p>

```bash
docker pull manimcommunity/manim
```

  <p>For more information, check out <a href="https://hub.docker.com/r/manimcommunity/manim">mainimcommunity/manim</a></p>

  </li>
  <li><p>There are several ways to interact with Manim. We're going to work with Jupyter Lab. For different methods check out <a href="https://hub.docker.com/r/manimcommunity/manim">this link</a>.</p></li>
  <li><p>First, make sure nothing is running on port 8888, then open a terminal window and run the following command to start up the manim docker container:</p>

```bash
docker run -it -p 8888:8888 manimcommunity/manim jupyter lab --ip=0.0.0.0
```

  </li>
  <li><p>You should see the following output:</p>

```
    file:///manim/.local/share/jupyter/runtime/jpserver-1-open.html

Or copy and paste one of these URLs:

    http://1a7fb2e74b32:8888/lab?token=542f72b2a4f0f8eb58089e3ab795f43c1ad3730b0500af58

 or http://127.0.0.1:8888/lab?token=542f72b2a4f0f8eb58089e3ab795f43c1ad3730b0500af58
```

  <p>Cut and Paste one of the above links in your browser. You should see the following:</p>

<img width="70%" src={require('@site/static/img/labs/misc/manim_browser.png').default} />

  </li>
  <li>Congratulations! You're now ready to use manim!</li>
</ol>

## Example

Let's start with a simple example:

<ol>
  <li><p>Open a new JupyterLab notebook and import all the contents of the manim library in a cell:</p>

```python
from manim import *

# To download image used in this example:
!wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/assets/logos/SN_favicon.png
```

  </li>

  <li><p>Objects in manim are generally divided into three categories:</p>
    <ul>
      <li><p>Scene</p></li>
      <li><p>Mobject</p></li>
      <li><p>Animation</p></li>
    </ul>

  <p>To create a scene, we create a <code>Scene</code> object as follows:</p>

```python
class SN(Scene):

   def construct(self):
       sn_logo = ImageMobject("SN_favicon.png")
       text1 = Text("Skills" ).shift(DOWN).shift(DOWN).shift(DOWN)
       text2 = Text("Skills Network", t2c={'[0:6]': PURPLE}).shift(DOWN).shift(DOWN).shift(DOWN)

       self.add(sn_logo)
       self.play(Write(text1))
       self.play(ReplacementTransform(text1, text2))
       self.wait(2)
```

  </li>
  <li><p>To run the scene, execute the following in the next code cell:</p>

```python
%manim SN
```

  <p>More generally, <code>%manim [name of class]</code> - where <code>[name of class]</code> is the name of the scene class you defined.</p>

  </li>
  <li><p>You should see a scene resembling the following:</p>

<img width="70%" src={require('@site/static/img/labs/misc/manim_scene.png').default} />

  <p>For more information, check out the <a href="https://docs.manim.community/en/stable/">Manim docs</a>.</p>

  </li>
</ol>

### Saving your work

**If you shut down your Docker Container you will lose your work.**
So you're going to need to download the video and JupyterLab. The lab is straightforward; let's see how to download the video:

<ol>
  <li><p>Go to the directory <code>./media/Jupiter/</code></p></li>
  <li><p>Download the video, which is the name of the class followed by an <code>@</code> and the date:</p>

  <p>For example, <code>SN@2022-05-02@02-43-50.mp4 more generally [name of class]@[date].mp4</code> as seen in the image below:</p>

<img width="30%" src={require('@site/static/img/labs/misc/manim_download_video.png').default} />

  </li>
  <li><p>Finally, when you close your application you must make sure the container is closed, open a terminal window and type:</p>

```bash
docker ps
```

  <p>You should see a list of your running containers, for example:</p>

```
CONTAINER ID   IMAGE                  COMMAND                  CREATED      STATUS      PORTS                    NAMES

1a7fb2e74b32   manimcommunity/manim   "jupyter lab --ip=0.…"   3 days ago   Up 3 days   0.0.0.0:8888->8888/tcp   peaceful_kowalevski
```

  </li>
  <li><p>stop the container by typing <code>docker stop [name of container]</code> for this case it would be </p>

```bash
docker stop peaceful_kowalevski
```

  </li>

</ol>
