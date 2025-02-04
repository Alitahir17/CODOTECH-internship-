NOTE: THE CODE IS WRITTEN AND IMPLEMENTED ON GOOGLE COLAB PLEASE IMPORT PYTHON IF ERROR ACCURRING ON OTHER PLATFORM......THANKU!

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~SIMPLE to-do list app TASK~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
#simple to-do list app(Build a console based to-do list application where user can add,view,edit,and delete task)
def task():
   task=[]
   total_task=int(input('enter how many task you want to add...'))
   for i in range (1,total_task+1):
       task_name=input(f'enter task{i}=')
       task.append(task_name)
       print(task)
   while True:
         operation=int(input('enter 1 for view \n,2 for add \n,3 for edit \n,4 for delete\n,5 for exit \nselect:'))
         if operation==1:
          print(task)
         elif operation==2:
          add=input('enter task name:')
          task.append(add)
          print(task)
         elif operation==3:
           edit=input('enter task name you want to update:')
           if edit in task:
              update=input('enter new task name:')
              ind=task.index(edit)
              task[ind]=update
              print(update)
         elif operation==4:
             delete=input('enter task name you want to delete:')
             if delete in task:
                ind=task.index(delete)
                del task[ind]
                print(delete,'is deleted')
         elif operation==5:
             print('thank u for using task management app')
             break
         else:
             print('invalid operation')
task()
```````````````OUTPUT``````````````````````````````````````````
enter how many task you want to add...5
enter task1=lunch
['lunch']
enter task2=dinner
['lunch', 'dinner']
enter task3=gym
['lunch', 'dinner', 'gym']
enter task4=sleep
['lunch', 'dinner', 'gym', 'sleep']
enter task5=wake up
['lunch', 'dinner', 'gym', 'sleep', 'wake up']
enter 1 for view 
,2 for add 
,3 for edit 
,4 for delete
,5 for exit 
select:1
['lunch', 'dinner', 'gym', 'sleep', 'wake up']
enter 1 for view 
,2 for add 
,3 for edit 
,4 for delete
,5 for exit 
select:2
enter task name:gamming
['lunch', 'dinner', 'gym', 'sleep', 'wake up', 'gamming']
enter 1 for view 
,2 for add 
,3 for edit 
,4 for delete
,5 for exit 
select:3
enter task name you want to update:gym
enter new task name:study
study
enter 1 for view 
,2 for add 
,3 for edit 
,4 for delete
,5 for exit 
select:4
enter task name you want to delete:study
study is deleted
enter 1 for view 
,2 for add 
,3 for edit 
,4 for delete
,5 for exit 
select:5
thank u for using task management app



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~RANDOM PASSWORD GENERATOR~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# RANDOM PASSWORD GENERATOR
import random
import string
print('welcome to random password generator')
def password_generator():

    length=int(input('enter the length of password'))
    lower=string.ascii_lowercase
    upper=string.ascii_uppercase
    num=string.digits
    symbols=string.punctuation
    all=lower+upper+num+symbols
    temp=random.sample(all,length)
    password="".join(temp)
    print('YOUR RANDOM PASSWORD IS',password)
password_generator()
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~OUTPUT~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
welcome to random password generator
enter the length of password15
YOUR RANDOM PASSWORD IS B&:g',_dMS+bx"@


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~SIMPLE CHATBOT USING PYTHON'S NLP~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords


nltk.download("punkt")
nltk.download("stopwords")


def preprocess_text(text):
    tokens=word_tokenize(text.lower())
    stop_words=set(stopwords.words("english"))
    filtered_tokens=[word for word in tokens if word.isalnum() and word not in stop_words]
    return " ".join(filtered_tokens)

def generate_response(user_input):
    if user_input.lower()=="hello":
        return "Hi there! How can I assist you today?"
    elif user_input.lower()=="how are you":
        return "I'm just a program, but thanks for asking!"
    elif user_input.lower()=="what is ai":
        return "AI stands for Artificial Intelligence, the simulation of human intelligence by machines."
    elif user_input.lower()=="bye":
        return "Goodbye! Have a great day!"
    else:
        return "I'm not sure I understand that."

def chatbot():
    print("Welcome to the chatbot! Type 'quit' to exit.")
    while True:
        user_input=input("You: ")
        if user_input.lower()=="bye":
            print("Chatbot: Goodbye!")
            break
        response = generate_response(user_input)
        print("Chatbot:", response)

chatbot()
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~OUTPUT~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[nltk_data] Downloading package punkt to /root/nltk_data...
[nltk_data]   Unzipping tokenizers/punkt.zip.
[nltk_data] Downloading package stopwords to /root/nltk_data...
[nltk_data]   Unzipping corpora/stopwords.zip.
Welcome to the chatbot! Type 'quit' to exit.
You: hello
Chatbot: Hi there! How can I assist you today?
You: how are you
Chatbot: I'm just a program, but thanks for asking!
You: what is ai
Chatbot: AI stands for Artificial Intelligence, the simulation of human intelligence by machines.
You: bye
Chatbot: Goodbye
