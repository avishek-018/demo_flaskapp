STEP 1 : Create a virtual environment with pipenv and install Flask and Gunicorn .

$ pipenv install flask gunicorn 

STEP 2 : Create a “Procfile” and write the following code.

web: gunicorn wsgi:app

STEP 3 : Create “runtime.txt” and write the following code.

python-3.7.5

STEP 4 : Create a folder named “app” and enter the folder.

STEP 5 : Create a python file, “main.py” and enter the sample code.

from flask import Flask 
  
app = Flask(__name__) 
  
@app.route("/") 
def home_view(): 
        return "<h1>Welcome to Geeks for Geeks</h1>"



STEP 6 :Get back to the previous directory “eflask”.Create a file“wsgi.py” and insert the following code.

from app.main import app 
  
if __name__ == "__main__": 
        app.run() 


STEP 7 : Run the vitual environment.

$ pipenv shell 

STEP 8 : Initialize an empty repo, add the files in the repo and commit all the changes.

$ git init 
$ git add .
$ git commit -m "Initial Commit"
STEP 9 : Login to heroku CLI using

heroku login
Now, Create a unique name for your Web app.

$ heroku create eflask-app

STEP 10 : Push your code from local to the heroku remote.

$ git push heroku master