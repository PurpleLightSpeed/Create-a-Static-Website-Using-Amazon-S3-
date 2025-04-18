# Creating a Static Website Using Amazon S3

## Objective
The purpose of this project is to demonstarte how to create a static website using an Amazon S3 bucket.

### Skills Learned
Using AWS S3 to host a static internet facing website.

### Tools Used
- AWS (You will need an AWS free tier account to complete this project)
- <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html"> AWS S3 </a>
- <a href="https://notepad-plus-plus.org/"> Notepad++ </a> (HTML)

## Steps

### Download Notepad++ (optional) and Create a Static Website
While downloading Notepadd++ is optional, you should create your own simple static website with <code>html</code> and save it to you computer for easy access.

I used Notepad++, but any program that allows you to save your static website in <code>.html</code> will work.

I built a static website based on a simplified version of my resume to use in this project.

![image](https://github.com/user-attachments/assets/7b069710-e421-40a0-bf16-08e09a58f013)

I saved the static website as <code>resume.html</code>

![image](https://github.com/user-attachments/assets/cd940e85-a5d3-44a1-80b9-c270c674f90a)

Opening the file with Firefox or any web browser of your choice should bring you to your static website.

![image](https://github.com/user-attachments/assets/b95ec7bd-8f6a-4031-9f54-a216abba01d8)

Notice that the URL is the file path that leads to the folder that you save your static website initially. Using this URL outside of your local machine will not bring you to your static website.

### Create the S3 Bucket
Navigate to you AWS console, select storage and click on S3 to create a bucket to host your website.

![image](https://github.com/user-attachments/assets/e75b1db5-a76c-4be3-89bd-32944ca71487)

Name the bucket, leave all other settings as default (we will come back and change some setting later) and click <code>Create Bucket</code>

![image](https://github.com/user-attachments/assets/bbcfbd03-c2e3-4aa1-9c5a-3465de24520c)

Once created, you will need to add all the files associated with you static website and upload them to your S3 bucket.

![image](https://github.com/user-attachments/assets/93da0d53-f1d6-4917-bcfb-4498bc4c9427)

When you have uploaded the files, click on the object with <code>.html</code> and navigate to <code>Object URL</code>. This will be the URL for your website.

![image](https://github.com/user-attachments/assets/483acf70-86e8-415e-9bea-488443f1a72c)

When you click on the link initially you will notice that it has an <code>Access Denied</code> on the page with your static website missing.

![image](https://github.com/user-attachments/assets/994ba6ca-3675-4663-8302-4c5ee09a70d2)

From here we will need to <code>Enable the Static Website Hosting</code>

To do this, Navigete back to the page containing your bucket and click on properties. Scroll down to Static Website Hosting and click <code>Edit</code>

![image](https://github.com/user-attachments/assets/03f35b7d-14b0-4fae-b0c4-4db008c24b4d)

Once here, <code>Enable</code> Static Website Hosting and enter in the name of your index document. In this case it would be <code>resume.html</code>. Click save changes.

![image](https://github.com/user-attachments/assets/cfb9e070-0571-4d8f-aae5-988b024bed00)

Now when you refresh you website and notice its still saying <code>Access Denied</code> we're still missing something.

![image](https://github.com/user-attachments/assets/994ba6ca-3675-4663-8302-4c5ee09a70d2)

When we created this static website we could access it locally from our machine without internet, but within AWS we need to enable access to the website over the internet.

To do this we need to navigate to permissions for our S3 bucket. Scroll down to <code>Block public access (bucket settings)</code>, click edit and uncheck <code>Block All Public Access</code> and save changes.

![image](https://github.com/user-attachments/assets/baf2e5e8-e20b-489d-ba4b-c5423c65a1d4)

Now going back to check your website, its still saying access denied. With this we need to make all the objects within the bucket publiclly accessible.

To do this we need to select all the objects in our bucket and select the action <code>Make public using ACL</code> but if this action is unavalables, we need to enable it.

Go to permissions and scroll down to Object Ownership and edit to enable ACLs. Acknowklegde and Save Changes.

![image](https://github.com/user-attachments/assets/0460401f-df60-40de-9d2e-93b6ad5337b1)

Go back select all the objects and select the action <code>Make public using ACL</code>

![image](https://github.com/user-attachments/assets/0799ebbf-8705-4c60-b9fd-208299f941e8)

Make Public!

![image](https://github.com/user-attachments/assets/60869e1e-8c62-4c47-8a35-f1d0171b0274)

Once Public, refresh your Object URL and it should be your static website hosted on AWS.

![image](https://github.com/user-attachments/assets/32a12bc2-9141-42dd-8db1-f80a02a61e3d)

That concludes this project. Thank You!


