FROM python:3.10-slim-buster

#Inside Container
#Make a new folder inside container
WORKDIR /backend-flask

#Outside the container => Inside the container
#This contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

#Inside Container
#Installs the python libraries used for the app
RUN pip3 install -r requirements.txt

#Outside the container => Inside the container
# .. means everything in the current directory
# . first period represents ./backend flask(outside conntainer)
#.. second period represents ./backend flask(inside container)
COPY . .

#Environment variables
#Set environmment variables (Env Vars)-inside the container , will remain set when the environemt is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
