# set up the container with Python 3.10
FROM python:3.10-slim

# copy in your current directory to the app directory
COPY . /app

# set the app directory as the working directory
WORKDIR /app

# install for all the packages listed in requirements file
RUN pip install -r requirements.txt

# port 80, standard port for HTTP
EXPOSE 80

# create a streamlit directory in the home directory of the container
RUN mkdir ~/.streamlit

# copy configuration file into the streamlit directory
RUN cp config.toml ~/.streamlit/config.toml

# copy streamlit credentials file into the streamlit directory
RUN cp credentials.toml ~/.streamlit/credentials.toml

# default command for the container to run the app with streamlit
ENTRYPOINT ["streamlit", "run"]

# run your main.py script when the container starts
CMD ["main.py"]