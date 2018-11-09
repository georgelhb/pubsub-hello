#### The code shows you how to get started publishing messages with Cloud Pub/Sub using the Python client library.
---
1) Install the Cloud Pub/Sub Python client library: <br/>
```
sudo pip install --upgrade google-cloud-pubsub
```
2) Set the environment variable PROJECT_ID: <br/>
```
export PROJECT_ID=[PROJECT_ID]
```
3) Run the publisher script to create Pub/Sub Topic: <br/>
```
python publisher.py $PROJECT_ID create MyTopic
```
4) List all Pub/Sub topics: <br/>
```
python publisher.py $PROJECT_ID list
```
5) Create a Pub/Sub subscription for topic with subscriber.py script: <br/>
```
python subscriber.py $PROJECT_ID create MyTopic MySub
```
6) list all subscribers in given project: <br/>
```
python subscriber.py $PROJECT_ID list_in_project
```
7) Publish some sample messages to MyTopic: <br/>
```
gcloud pubsub topics publish MyTopic --message "Hello 1"
gcloud pubsub topics publish MyTopic --message "Hello 2"
gcloud pubsub topics publish MyTopic --message "Hello 3"
```
8) Use MySub to pull the message from MyTopic: <br/>
```
python subscriber.py $PROJECT_ID receive MySub
```
