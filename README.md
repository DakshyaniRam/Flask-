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

5. To open the default browser to the rendered page, Ctrl+click the http://127.0.0.1:5000/ URL in the terminal.















 
