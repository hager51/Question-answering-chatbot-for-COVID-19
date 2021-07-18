# Question-answering-chatbot-for-COVID-19
The aim of our project is to create A COVID-19 Question Answer Chatbot to  improve answer selection process on the specific domain of COVID-19. With  InferMedica, we hope to learn whether public information from reputable  sources could be more effectively organized and shared in the wake of a crisis  as well as to understand issues that the public were most immediately curious  about. 
we can run project in local machin or on colab directly
how to run local ?
step 1 
1- Install flask and flask libraries.

$pip install Flask

2- Run virtual environment in case of implementing on local machine. Use 
a virtual environment to manage the dependencies for your project, both 
in development and in production. 
Create an environment
Create a project folder and a venv folder within:

> mkdir myproject
> cd myproject 
> py -3 -m venv venv

Activate the environment
Before you work on your project, activate the corresponding 
environment: 

> venv\Scripts\activate

3- Install ngrok in case of implementing on a cloud like colab. 
!pip install flask-ngrok
4- Prepare your model to call it in the flask function. 
Preparing the model differs from one approach to another but the main 
idea in our project as a chat-bot is to get a function that could take a 
Question from user and make processes on that input then generate the 
proper answer. 
5- Make your html files in folder named “templates”. 
6- Make your Css and is file in folder named “static”. 
7- Make your flask function and link your model with the interface you get 
from html and Css. 
- First, we imported the Flask class. An instance of this class will be our 
WSGI application. 
- Next, we create an instance of this class: The first argument is the 
name of the application’s module or package. __name__ is a 
convenient shortcut for this that is appropriate for most cases. This is 
needed so that Flask knows where to look for resources such as 
templates and static files. 
- We then use the route() decorator to tell Flask what URL should 
trigger our function. 
- Use render template method to render the template you want. 
- Use request.args.get() to get the get the message/ input the user enter 
then return it with the function that make response from the model to 
get the answer. 
>
from flask import Flask, render_template, request, redirect, url_for
from flask_ngrok import run_with_ngrok
app = Flask(__name__)
run_with_ngrok(app)   
  
app.static_folder = 'static'
@app.route("/")
def home():
    return render_template("home.html")
@app.route("/get")
def get_bot_response():
    userText = request.args.get('msg')
    return answer_question(userText)
    
app.run()
>
8- Run your code and get your API. 




