# Description
A lean container with Python 3.7 (Alpine base) and NLTK 

# Overview
This is a lean Docker image containing Python 3.7 and the NLTK library.

You'll have to bring your own NLTK data to the party - otherwise the NLTK functions would not work. The NLTK data is intentionally not packaged with the container, with the following advantages:

* container size can be kept small
* container is reusable
* able to swap out the NLTK models without having to rebuild the container
* able to include only the necessary models needed for your environment

# Mounting NLTK Data to the Container
* Go to https://github.com/nltk/nltk_data and download the repo
* Extract the "packages" folder from the zip archive (it should contain folders like "chunkers", "corpara", "grammars"
* Mount the folder onto the container at the container path /nltk_data
* For example: `docker run --rm -i -v /path/to/nltk_data:/nltk_data luppy2/python-alpine3.7-nltk:latest your-nltk-script.py`

# Dockerfile
```
FROM python:alpine3.7 

RUN pip install nltk

ENTRYPOINT ["python"]
```
