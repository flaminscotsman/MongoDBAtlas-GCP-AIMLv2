# MongoDB Atlas & GCP AI/ML

# Background

This is a tutorial on how to use [MongoDB Atlas](https://cloud.mongodb.com) in conjunction with Google's [AI & Machine Learning Products](https://cloud.google.com/products/ai/) to create an event-driven model in Python.

This is part of a workshop series presented by [MongoDB](https://www.mongodb.com/) and [Google Cloud](https://cloud.google.com/), however it can also be followed along on its own. The Google aspects of the workshop are based on Google's [Vision AI](https://cloud.google.com/vision/).

## Technical Complexity

_Beginner to Intermediate_ 

## Technology  

Familiarity with the following technologies will be of benefit:

* Python 3
* HTML
* Basic JSON (will be covered in MongoDB introduction slides)


## Software Requirements

1. Modern web browser such as [Google Chrome](https://www.google.com/chrome/) *(Required to access MongoDB Atlas, GCP Console, and Google CloudShell)*
2. Optionally install [MongoDB Compass](https://www.mongodb.com/download-center/compass), the GUI for MongoDB

## Duration

_45 Minutes_

# Setup

## High Level Readme

* Setup a MongoDB Atlas Account
* Deploy a free-tier MongoDB Atlas M0 cluster
* Create a database username/password and setup a suitable IP whitelist entry to allow access to the cluster
* Make note of the connection string for Python
* Create a Google Cloud account if required
* Enable the _Cloud Vision API_
* Create a service credential and download the JSON file 
* Create a GCP instance
* Open firewall rules in GCP for ports 8088 and 8089 for this instance
* Install python and clone this github repo on the GCP instance
* Configure the `FinishedSampleCode/settings.cfg` and `FinishedSampleCode/gcpcreds.cfg` with the Atlas connection string and GCP credentials that you created earlier
* Install any python requirements by running `pip install -r FinishedSampleCode/requirements.txt`
* Start the application using `python3 FinishedSampleCode/runner.py`
* Open a web browser to the GCP instance running on port 8088 over http: `http://<host>:8088`


## Low Level Readme
*Note: You can choose between using pre-written code, which is linked/cloned in the 'Readme for configuring the GCP instace' section (3a), **or** to write the code from scratch, following along in the section (3b) that follows*

1. [Readme for configuring MongoDB Atlas](Guides/AtlasSetup.md)
2. [Readme setup GCP project and configuring GCP Vision API](Guides/GCPProjectAndVisionSetup.md)
3a. [Readme for configuring the GCP Instance](Guides/GCPInstanceSetup.md) *or;* 
3b. [Readme for writing this code from scratch](Guides/Code.md)

## Other Readme's
* [The guide for CRUD operations used during the instruction part of workshop](Guides/CRUD.md)
* [Instructor's Notes](Guides/Instructors.md)

# Execution

* Start the application using `python3 FinishedSampleCode/runner.py`
* Open a web browser to the GCP instance running on port 8088 over http
* Insert a document into the database using MongoDB Compass or the new Data Explorer view in MongoDB Atlas which you can get to via the "Collections" button. The document you insert should have a field called `url` which is a full URL to an image.
* Alternately enter the URL into the web page directly and press the green "Insert" button
* Notice that in the web page and on the CLI output of the python script that it saw an insert
* Notice that after the insert, the change stream called the Google Vision API to see what is in it. Refresh the Compass or Atlas Data Explorer view and see the rich data structure of the GCP Vision API.

![Compass](Guides/images/newss03.png)

# Sample Data

Feel free to use the following URLs for execution:

1. https://storage.googleapis.com/demo-visionapi-atlas/StatueofLiberty.jpeg
2. https://storage.googleapis.com/demo-visionapi-atlas/crash1.jpg
3. https://storage.googleapis.com/demo-visionapi-atlas/nike_logo_30021.jpg
4. https://storage.googleapis.com/demo-visionapi-atlas/Marketing/eiffel-tower.jpg
5. https://storage.googleapis.com/demo-visionapi-atlas/Finance/check.jpg

# Extra Credit

* Create a GCP Cloud Storage Bucket to host your own images
* Follow along with the `runnerAdvanced.py` using the GCP Natural Language API to do sentiment analysis on non-URL text in the `text` attribute of a document
  * When the runnerAdvanced.py script is running you can enter text into the search box of the web application and the code will perform sentiment analysis on it, presenting the results in the output pane
  * Note: you will need to enable the 'Cloud Natural Language API' in your GCP project before running the runnerAdvanced.py script, in the same way you enabled the 'Cloud Vision API'
* Find another GCP API and integrate with it. Examples:
  * Use the Cloud Translation API to extend the `runnerAdvanced.py` to translate your text into another language
  * Consider integrating the Google Assistant API

