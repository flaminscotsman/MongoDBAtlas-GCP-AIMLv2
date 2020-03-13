# GCP project and configuring GCP Vision API setup

* Go to [cloud.google.com](https://cloud.google.com/) and login with your Google account. If you don't have a Google account, please create a free trial account by following [these instructions](https://console.cloud.google.com/freetrial).

* Next, click on the "Go to console" button and/or login to [https://console.cloud.google.com/](https://console.cloud.google.com/) directly.

* Create a new project by selecting the dropdown next to "Google Cloud Platform" on the top left, i.e., click "My First Project" in the following example:

> ![image](images/image30.png)

* A new window will pop up.  In it, select "New Project" on the top right:

> ![image](images/image14.png)

* Give your new Vision API project a name.  Let's go with “mongodb-vision-demo” and click the “Create” button:

> ![image](images/image28.png)

* This results in a new project being created:

> ![image](images/image31.png)

* Once complete, make this your current project. Either type the name in the main search bar...

> ![image](images/image22a.png)

* ...or go back to the dropdown from before and select your new project by name:

> ![image](images/image22.png)

* When the right project is selected, your screen should look like this:

> ![image](images/image22b.png)

* Next, in the search box type "Cloud Vision API" and choose that option in the drop down

> ![image](images/newss06.png)

* Enable the Cloud Vision API

> ![image](images/newss01.png)

* Your screen should now look like the following:

> ![image](images/newss01a.png)

* Next we will create a credential of type "Service Account Key" (with a name of your choosing), where "Key Type" is `JSON`, and "Role" of `Owner`. To do so we begin by selecting the "APIs & Services" entry from the hamburger menu on the top left of the window and then select "Credentials", as follows:

> ![image](images/newss01b.png)

* Clicking 'Create credentials' results in a selection of different credential types. Select "Service Account" here:

> ![image](images/image-j-2.png)

* On the 'Service account details' screen, type a 'Service Account Name' (anything is fine), then click 'create'.

> ![image](images/image-j-3.png)

* From the "Select a role" dropdown, select "Project" and then "Owner". Once you've selected "Owner", click "Continue". 

> ![image](images/image-j-5.png)

* Under the "Create key (optional)" section, click "+ Create Key" _(note: this is not optional)_

> ![image](images/image-j-4.png)

* Ensure that `JSON` is selected as the type (it is the default), then click "Create".

> ![image](images/image-j-6.png)

* As part of the creation process, the system will download the JSON file. We will use the contents of this file to populate the `gcpcreds.json` file in our change streams application shortly. The dialog should look like the following:

> ![image](images/image-j-7.png)

