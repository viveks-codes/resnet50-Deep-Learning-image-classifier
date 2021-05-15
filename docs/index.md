<h1 align="center">Welcome to resnet50-Deep-Learning-image-classifier 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-2.O-blue.svg?cacheSeconds=2592000" />
  <a href="https://raw.githubusercontent.com/vivolscute/resnet50-Deep-Learning-image-classifier/main/README.md" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
</p>

 ResNet-50 is a CNN(convolutional neural network) that is 50 layers deep. we can load a pretrained version of the network trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, birds and many animals.

### 🏠 [Homepage](https://github.com/vivolscute/resnet50-Deep-Learning-image-classifier)

### ✨ [Demo](https://resnet50.pythonanywhere.com/)

## Deployment

Everything you need to get started. Google Cloud. Start building right away on our secure, intelligent platform. New customers can use a $300 free credit to get started with any 
[Google Cloud](https://console.cloud.google.com/).
 https://console.cloud.google.com/

> genral note (for Qwiklabs users) :-
If you use resources that are not related to the lab, you could be locked out of the lab and lose your work. For example, if you start up more VMs than the number called for in the lab instructions, your lab will end, you will be locked out of Qwiklabs, and you will receive the message "Your account has been blocked".torial may block your Qwiklabs account.It is always good to have one personal GCP account. New customers can use a $300 free credit to get started with
[Google Cloud](https://console.cloud.google.com/).

# Step 0: 

<b>Activate Cloud Shell</b>
![](https://cdn.qwiklabs.com/vdY5e%2Fan9ZGXw5a%2FZMb1agpXhRGozsOadHURcR8thAQ%3D)

In the Cloud Console, in the top right toolbar, click the Activate Cloud Shell button.
<b>after that Click Continue.</b>

# step 1:

## clone this repo
clone this repo via following command

```
git clone https://github.com/vivolscute/resnet50-Deep-Learning-image-classifier.git
```
Change directory into  <i>resnet50-Deep-Learning-image-classifier</i>

```
cd resnet50-Deep-Learning-image-classifier
```

# step 2:
## Authenticate API Requests

Set an environment variable for [YOUR_PROJECT_ID], replacing [YOUR_PROJECT_ID] with your own project ID:

```
export PROJECT_ID=[YOUR_PROJECT_ID]
```
> if you are using qwiklabs account run following
(for qwiklabs)
```
gcloud iam service-accounts create qwiklab \
  --display-name "My Qwiklab Service Account"
```
Create a Service Account to access the Google Cloud APIs when testing locally:
```
gcloud iam service-accounts create resnet50 \
  --display-name "My GCP Account"

```
> if you are using qwiklabs account run following
(for qwiklabs)
```
gcloud iam service-accounts create qwiklab \
  --display-name "My Qwiklab Service Account"
```
Give your newly created Service Account appropriate permissions:

```
gcloud projects add-iam-policy-binding ${PROJECT_ID} \
--member serviceAccount:resnet50@${PROJECT_ID}.iam.gserviceaccount.com \
--role roles/owner
```
> if you are using qwiklabs account run following
(for qwiklabs)
```
gcloud projects add-iam-policy-binding ${PROJECT_ID} \
--member serviceAccount:qwiklab@${PROJECT_ID}.iam.gserviceaccount.com \
--role roles/owner
```

After creating your Service Account, create a Service Account key:
```
gcloud iam service-accounts keys create ~/key.json \
--iam-account resnet50@${PROJECT_ID}.iam.gserviceaccount.com
```
> if you are using qwiklabs account run following 
(for qwiklabs)
```
gcloud iam service-accounts keys create ~/key.json \
--iam-account qwiklab@${PROJECT_ID}.iam.gserviceaccount.com
```

```
export GOOGLE_APPLICATION_CREDENTIALS="/home/${USER}/key.json"
```

# Run tests

## create environment

```python
virtualenv -p python3 env
```
activate the environment
```
source env/bin/activate
```
# step 3:
## install dependencies
```sh
pip install -r requirements.txt
```
## Creating an App Engine App
create an App Engine instance by using:
```
gcloud app create
```
## Create a Storage BucketCreating a Storage Bucket

```
export CLOUD_STORAGE_BUCKET=${PROJECT_ID}
```

## create a bucket
 ```
 gsutil mb gs://${PROJECT_ID}
 ```

## Running the Application
Execute the following command to start your application:
```
python main.py
```
Once the application starts, click on the Web Preview icon in the Cloud Shell toolbar and choose "Preview on port 8080."

![](https://cdn.qwiklabs.com/a6YnJv8GlGae4rnJIbjA27J8c7YApa%2B6noPFkkKxZjk%3D)

# Deploying the App to App Engine
## Update your Cloud Build timeout:
```
gcloud config set app/cloud_build_timeout 1000
```
# Deploy your app on App Engine by using gcloud
```
gcloud app deploy
```
> If asked, Do you want to continue (Y/n), press Y and then Enter.

After the application is deployed, open the app in your web browser with the following URL:
```
https://<PROJECT_ID>.appspot.com
``` 
Now You are all set!⭐️ 
## Author

👤 **vivek patel**

* Website: http://viveks.codes/vivek-codes
* Github: [@vivolscute](https://github.com/vivolscute)
* LinkedIn: [@vivek-patel-0553731a5](https://linkedin.com/in/vivek-patel-0553731a5)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/vivolscute/resnet50-Deep-Learning-image-classifier/issues). You can also take a look at the [contributing guide](https://github.com/vivolscute/resnet50-Deep-Learning-image-classifier/pulls).


## resources
[Deploying a Python Flask Web Application to App Engine Flexible](https://www.qwiklabs.com/focuses/3339?parent=catalog)

[Deploy Machine Learning Models to Production: With Flask, Streamlit, Docker, and Kubernetes on Google Cloud Platform](https://www.amazon.in/Deploy-Machine-Learning-Models-Production/dp/1484265459)


## Show your support

Give a ⭐️ if this project helped you!

***
