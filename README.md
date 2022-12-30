# Flask-
POC of Flask Framework-Python

Follow the below commands to create a simple flask application to run with and without debug mode.

PREREQUISITES :

1. Install the Python extension.

 To install other Python packages you must run the command in the terminal.
 
          sudo apt install python3-pip
          
 
On Windows, make sure the location of our Python interpreter is included in your PATH environment variable. You can check the location by running path at the command prompt. 
If the Python interpreter's folder isn't included, open Windows Settings, search for "environment", select Edit environment variables for your account, then edit the Path variable to include that folder.

CREATE A PROJECT ENVIRONMENT :

1. On your file system, create a project folder, such as "flask".
2. Creating a virtual environment 
 
        python -m virtualenv venv
        
3. Activating a virtual environment  

       .venv/bin/activate
       
NOTE: Use a stock Python installation when running the above commands. If you use python.exe from an Anaconda installation, you see an error because the ensurepip module isn't available, and the environment is left in an unfinished state.

4. Open the project folder by running code., or by running VS Code and using the 'File > Open Folder' command.
   
5. Open the Command Palette (View > Command Palette or (Ctrl+Shift+P)). Then select the Python: Select Interpreter command.From the list, select the virtual environment in your project folder that starts with ./.venv or .\.venv:

6. Update pip in the virtual environment by running the following command :

            python -m pip install --upgrade pip

7. Install Flask in the virtual environment by running the following command :

            python -m pip install flask

8.We now have a self-contained environment ready for writing Flask code. If we open a separate command prompt or terminal, activate the environment again using the command[.venv/bin/activate].

CREATE A MINIMAL FLASK APP :

1. Create a new file in your project folder named 'app.py'.
2. In app.py, add code to import Flask and create an instance of the Flask object.

         from flask import Flask
         app = Flask(__name__)
         
Also in app.py, add a function that returns content, in this case a simple string, and use Flask's app.route decorator to map the URL route / to that function:

         @app.route("/")
         def home():
            return "Hello, Flask!"
            
NOTE: We can use multiple decorators on the same function, one per line, depending on how many different routes we want to map to the same function.

3. Save the app.py file and run the app using the command,

        python -m flask run
        
4. Once we run the flask ,we could see the following output ,

(.venv) D:\py\\hello_flask>python -m flask run
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

5. To open the default browser to the rendered page, Ctrl+click the http://127.0.0.1:5000/ URL in the terminal.We could see a statement as,
  
         Hello,Flask!!
         
 RUN THE APP IN THE DEBUGGER :
 
      Debugging gives the opportunity to pause a running program on a particular line of code. When a program is paused, we can examine variables, run code in the Debug Console panel, and otherwise take advantage of the features described on Debugging. Running the debugger also automatically saves any modified files before the debugging session begins.

1. Replace the contents of app.py with the following code, which adds a second route and function that can step through in the debugger:

import re
from datetime import datetime

from flask import Flask

app = Flask(__name__)


@app.route("/")
def home():
    return "Hello, Flask!"


@app.route("/hello/<name>")
def hello_there(name):
    now = datetime.now()
    formatted_now = now.strftime("%A, %d %B, %Y at %X")

    # Filter the name argument to letters only using regular expressions. URL arguments
    # can contain arbitrary text, so we restrict to safe characters only.
    match_object = re.match("[a-zA-Z]+", name)

    if match_object:
        clean_name = match_object.group(0)
    else:
        clean_name = "Friend"

    content = "Hello there, " + clean_name + "! It's " + formatted_now
    return content


2. Set a breakpoint at the first line of code in the hello_there function (now = datetime.now()) and switch to RUN the code with debugging mode,and we will be able to see the statement in the browser as,

        Hello there, Ram! It's Monday, 20 March, 2022 at 20:45:30
        













 
