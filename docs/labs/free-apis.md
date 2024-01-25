# Free APIs Available in Skills Network Labs

While taking labs within Skills Network Labs, your learners will have free access to some APIs. 
This helps learners get started with the interesting stuff right away, without immediately worrying about registration.

## Learner Quotas

Learner usage of Skills Network-provided APIs is subject to a quota. The quota is based on actual cost, so if you choose lower-cost APIs (e.g. lower cost models), then your learners will be less likely to hit their quota.

When a learner has reached their quota, they will receive an error message like this one:

```shell
RateLimitError: Error code: 429 - {'error': 'You have exceeded your usage quota for Skills Network-provided <api endpoint> for the day. Your quota will reset in 6 hours 32 minutes from now.'}
```

## Limitations

These free Skills Network-provided APIs are available for learning and experimentation. They are not suitable when it comes to deploying an application. 

Learners will have access to these APIs within their:
- Cloud IDE (from their terminal/shell, or when running an application from within Cloud IDE)
- JupyterLab IDE (from their notebook, or from the JupyterLab terminal/shell)
- Rstudio IDE

Learners will _not_ have free access to these APIs within their:
- Code Engine projects
- Kubernetes cluster namespaces
- OpenShift cluster namespaces


## Free APIs

### watsonx.ai

##### IMPORTANT: You must use version `1.0.321` of `ibm-watson-machine-learning`

You can install it by running:

```python
pip install ibm-watson-machine-learning==1.0.321
```

##### Usage
To use the free Skills Network-provided watsonx.ai project, you need to specify `"token": "skills-network"` (not to be confused with `"apikey": "skills-network"` ) and `project_id = "skills-network"`. For example, you can modify [the example from the official documentation for the ibm_watson_machine_learning library](https://www.ibm.com/docs/en/watsonx-as-a-service?topic=models-python-library#example-prompt-a-foundation-model-with-default-parameters):



You can then use it like this:
```python
from ibm_watson_machine_learning.foundation_models.utils.enums import ModelTypes
from ibm_watson_machine_learning.foundation_models import Model
import json

my_credentials = {
    "url"    : "https://us-south.ml.cloud.ibm.com",
    "token" : "skills-network" # <--- NOTE: specify "skills-network" as your token (NOT as your apikey) 
}


model_id    = ModelTypes.FLAN_T5_XXL
gen_parms   = None
project_id  = "skills-network" # <--- NOTE: specify "skills-network" as your project_id
space_id    = None
verify      = False

model = Model( model_id, my_credentials, gen_parms, project_id, space_id, verify )   
 
prompt_txt = "In today's sales meeting, we "
gen_parms_override = None

generated_response = model.generate( prompt_txt, gen_parms_override )

print( json.dumps( generated_response, indent=2 ) )
```

### OpenAI

To use the free Skills Network-provided OpenAI APIs, no additional configuration is necessary. You can use [the examples from the official documentation](https://platform.openai.com/docs/api-reference/chat/create) without modification.

For example:
```python
from openai import OpenAI
client = OpenAI()

completion = client.chat.completions.create(
  model="gpt-3.5-turbo",
  messages=[
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Hello!"}
  ]
)

print(completion.choices[0].message)
```
