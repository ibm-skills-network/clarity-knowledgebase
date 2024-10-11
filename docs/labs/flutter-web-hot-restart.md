# Flutter Web Hot Restart in Cloud IDE

Flutter Web has awesome hot restart feature that allows you to see your changes in the browser instantly by pressing **r** in the terminal. This feature automatically refreshes the web app without needing to manually stop and start the server each time you make a change.

However, in our Cloud IDE, this feature doesn’t work as expected. This is because the Cloud IDE environment differs from the standard setup of a browser connected to a display server, which Flutter relies on for hot restart to function. But don't worry! We’ve created a simple workaround using a bash script to mimic the hot reload functionality.

## Hot Reload with a Bash Script

To overcome this limitation, you can use the following bash script to monitor file changes and automatically restart your Flutter web server. The script will ensure that your project is rebuilt and the changes are visible in the browser, just like the hot restart would.

### Steps to Use the Script:

1.  **Copy and Paste the Bash Script**  
    Copy the following script into a file (for example, `hot_reload.sh`).
    
    ```
    #!/bin/bash
    
    # Path to your Flutter project directory
    PROJECT_DIR="/home/project/hello_world_web/lib"
    
    # Function to run Flutter web server
    start_server() {
        echo "Starting Flutter web server..."
    
        cd $PROJECT_DIR/..
        flutter build web
        # Goto build directory
        cd build/web
        # Start server on port 8080
        python3 -m http.server 8080 &
        SERVER_PID=$!
    
        echo "Flutter server started with PID $SERVER_PID"
    }
    
    # Function to stop Flutter web server
    stop_server() {
        if [ ! -z "$SERVER_PID" ]; then
            echo "Stopping Flutter web server with PID $SERVER_PID"
            kill $SERVER_PID
            wait $SERVER_PID 2>/dev/null
        fi
    }
    
    # Watch for file changes and restart server
    watch_and_reload() {
        inotifywait -m -r -e modify,create,delete --exclude '\.git|build|\.dart_tool|\.idea|\.vscode' $PROJECT_DIR |
        while read -r directory events filename; do
            echo "Change detected in $directory$filename. Restarting server..."
            stop_server
            start_server
        done
    }
    
    # Cleanup function to handle script exit
    cleanup() {
        echo "Cleaning up before exit..."
        stop_server
        exit 0
    }
    
    # Trap SIGINT (Ctrl-C) and call the cleanup function
    trap cleanup SIGINT
    
    # Initial server start
    start_server
    
    # Start watching for changes
    watch_and_reload
    ``` 
    
2.  **Set the Correct Project Directory**  
    In the script, make sure to update the line that sets `PROJECT_DIR` to point to your Flutter project directory.
    
    `PROJECT_DIR="/home/project/your_flutter_project/lib"` 
    
3.  **Run the Script**  
    After saving the script, give it execute permissions and run it:
    
    ```
    chmod +x hot_reload.sh
    ./hot_reload.sh
    ``` 
    
    The script will start the Flutter web server, and any time you modify a file in your project, it will detect the change, rebuild the project, and restart the server automatically.
    
4.  **Stop the Script**  
    To stop the script, simply press `Ctrl + C` in the terminal. This will cleanly stop the server.
    
