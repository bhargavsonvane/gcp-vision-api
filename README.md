<p>
  <a href="https://in.linkedin.com/in/bhargav-sonvane">
   <img src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white">
 </a>
  <a href="https://opensource.org/licenses/MIT">
   <img src="https://img.shields.io/badge/License-MIT-yellow.svg?&style=for-the-badge&logoColor=white">
 </a>
</p>

# gcp-vision-api
A project to extract texts from the input image powered by GCP's Cloud Vision API

This includes 4 steps:
1.  Creating Virtual Machine on Google Cloud Platform.
2.  SSH Connection from local machine to VM on Google Cloud Platform.
3.  Setting up Vision API credentials.
4.  Python code for conversion.

We will use SSH for connecting Local Machine to Cloud VM: 
SSH Instructions for Windows User:
- Download Putty
- Open Putty Key Generator
- Click on generate key
- You can change Key Comment field with your project name.
- Copy Complete Key value.

Create & setup your GCP Account if you haven't from below link: 
https://cloud.google.com/

After creating account successfully. Go to Compute Engine > VM instances and
create VM with Ubuntu OS.

For tutorial on VM Creation check the below link:
https://cloud.google.com/compute/docs/quickstart-linux

Steps to implement :
-  Open VM instance & Click on instance1 (your instance name)
 
<img align="center" src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/openvminstance.png?raw=true">   

-  Click Edit
 
<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/edit.png?raw=true">

-  In SSH keys section click on “show and edit” option
 
<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/saveedit.png?raw=true">

-  Paste public key
 
<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/pastepkey.png?raw=true">

-  Allow HTTP and HTTPS traffic and click on save.
 
<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/allow.png?raw=true">

- Save Public and Private keys in Putty Key Generator. (It saves in the form of files)
- In Putty Configuration window go to SSH >Auth and browse private key file that you already saved in your system.
- In Putty Configuration window go to Session enter external IP address of VM instance and Hit Enter. It’s done..... 

- Now we have to create API Key on GCP. So, go to APIs & Services > Credentials. After that go to Create Credentials > Service Account Key. In Service account key section select service account as new service account and do rest changes as per
below screenshot.

<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/createjson.png?raw=true">

After clicking on Create button you will get a .json file. Save that file in local machine.

- Now we have to copy the contents of the downloaded .json file to paste it in our server machine.
1. Copy contents of .json file.
2. In VM Instance create .json file and paste contents in it.

This .json file contains private key for secure connection to APIs.
- Let’s connect to API by using following command: “export GOOGLE_APPLICATION_CREDENTIALS=~/Path of your .json file”

- After doing this your server may not work even after restart. So now we will update .profile file.
- open .profile file and paste, “export GOOGLE_APPLICATION_CREDENTIALS=~/Path of your .json file” at the end of file.
- Now to update this change in entire system enter command “source ~/.bashrc”.

- Now everything is done at background. Our VM is ready and We installed Vision API on it. It’s time to write python code.
- First download the image that you want to convert into text. Use “wget Image_address” to download it from web. (Copy image address by right clicking on
image)
- For example, This is the input image we want to Convert:

<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/img.jpeg?raw=true">

- Output
<img align="center"  src="https://github.com/bhargavsonvane/gcp-vision-api/blob/main/images/output.png?raw=true">

And We are done!!!...
You can copy this quote and paste anywhere!!!
You can design good user interface or android application on top of it.
