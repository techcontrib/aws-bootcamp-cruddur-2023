FROM python:3.10-slim-buster

# Within/Inside Container (Make a new folder inside the container)
WORKDIR /backend-flask

# Outside Container --> Inside Container
# Below file contains all the necessary libs needed to run the image
COPY requirements.txt requirements.txt

# Within/Inside Container
# Install Python libs used for the and by the app
RUN pip3 install -r requirements.txt

# Outside Container --> Inside Container
# "." means everything in the current dir
# first period "." to copy from outside container "/backend-flask"
# second period "." to copy inside the container "/backend-flask"
COPY . .

# Inside the container & will  remain set when container running
ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
# python3 -m flask run --host=0.0.0.0 --port=4567