# Flask Web App On Openshift Local

Based off of techwithtim's Flask-Web-App-Tutorial

## Setup & Installation

For a more comprehensive guide visit this Google Doc https://docs.google.com/document/d/18uC2K_3djwtpqNTfefchUuhVx6Jz3kMIPUqPEPjTQqU/edit?usp=sharing

Install crc and oc from Openshift Local Console.

Make sure you have the latest version of Python installed.

```bash
git clone <repo-url>
```
Start Openshift Local crc tool

```cli
crc start
```
Login to webconsole: https://console-openshift-console.apps-crc.testing
Use credentials as provided after running crc start

Enter directory and deploy helm charts using these commands

```cli
helm upgrade flask-app ./flask-helm --install --atomic -n flask-app --create-namespace --debug
```

```cli
helm upgrade postgres ./postgres-minimal --install --atomic -n flask-app --create-namespace --debug
```


## Running The App
Enter web console, both pods flask-app and postgres and their services should be running.

Create a route: 
 1) Sidebar -> Networking -> Routes
 2) Create route
 3) Select flask-app service


## Viewing The App

Go to `http://flask-flask-app.apps-crc.testing`
