# Article CMS (FlaskWebProject)

This project "Article Content Management System" is a Python web application built using Flask. The user can log in and out and create/edit articles. An article consists of a title, subtitle, author and body of text; stored in an Azure SQL Server along with an image that is stored in Azure Blob Storage. I have also implemented OAuth2 Sign-in with Microsoft using the `msal` library, along with app logging.

![app_demo](example_images/app_demo.gif)
## Log In Credentials for FlaskWebProject

- Username: admin
- Password: pass

Or use Microsoft Account to Sign In
![aOauth2_demo](example_images/oauth2_demo.gif)

## Udacity Project Instructions (For Student)

You are expected to do the following to complete this project:

1. [x] Create a Resource Group in Azure.
2. [x] Create an SQL Database in Azure that contains a user table, an article table, and data in each table (populated with the scripts provided in the SQL Scripts folder).
    - [x] Provide a screenshot of the populated tables as detailed further below.
3. [x] Create a Storage Container in Azure for `images` to be stored in a container.
    - [x] Provide a screenshot of the storage endpoint URL as detailed further below.
4. [x] Add functionality to the Sign In With Microsoft button. 
    - [x] This will require completing TODOs in `views.py` with the `msal` library, along with appropriate registration in Azure Active Directory.
5. [x] Choose to use either a VM or App Service to deploy the FlaskWebProject to Azure. Complete the analysis template in `WRITEUP.md` (or include in the README) to compare the two options, as well as detail your reasoning behind choosing one or the other. Once you have made your choice, go through with deployment.
6. [x] Add logging for whether users successfully or unsuccessfully logged in.
    - [x] This will require completing TODOs in `__init__.py`, as well as adding logging where desired in `views.py`.
7. [x] To prove that the application in on Azure and working, go to the URL of your deployed app, log in using the credentials in this README, click the Create button, and create an article with the following data:
	- Title: "Hello World!"
	- Author: "Jane Doe"
	- Body: "My name is Jane Doe and this is my first article!"
	- Upload an image of your choice. Must be either a .png or .jpg.
   After saving, click back on the article you created and provide a screenshot proving that it was created successfully. Please also make sure the URL is present in the screenshot.
8. [x] Log into the Azure Portal, go to your Resource Group, and provide a screenshot including all of the resources that were created to complete this project. (see sample screenshot in "example_images" folder)
9. [x] Take a screenshot of the Redirect URIs entered for your registered app, related to the MS Login button.
10. [x] Take a screenshot of your logs (can be from the Log stream in Azure) showing logging from an attempt to sign in with an invalid login, as well as a valid login.


## example_images Folder

1. article-cms-solution.png is a screenshot of deployed app
![app](example_images/article-cms-solution.png)

2. azure-portal-resource-group.png is a screenshot from the Azure Portal showing all of the contents of the Resource Group I have created.
![app_resources](example_images/azure-portal-resource-group.png)

3. sql-storage-solution.png is a screenshot showing the created tables and one query of data from the initial scripts.
![app_sql_storage](example_images/sql-storage-solution.png)

4. blob-solution.png is a screenshot showing an example of blob endpoints for where images are sent for storage.
![app_blob_storage](example_images/blob-solution.png)

5. uri-redirects-solution.png is a screenshot of the redirect URIs related to Microsoft authentication.
![app_uri](example_images/uri-redirects-solution.png)

6. log-solution.png is a screenshot showing one potential form of logging with an "Invalid login attempt" and "admin logged in successfully", taken from the app's Log stream.
![app_log](example_images/log-solution.png)

## Stand Out Suggestions
I have added all the features suggested in the rubric

1. [x] Modified both the Python Application and SQL Database to include a Subtitle field.
2. [x] Added functionality for the deletion of created article or removal of an image
3. [x] Ability to track which user is logged in, when signed-in with Microsoft.

## Dependencies
### Deployement
1. A free Azure account
2. A GitHub account
3. Python 3.7 or later
4. Visual Studio 2019 Community Edition (Free)
5. The latest Azure CLI (helpful; not required - all actions can be done in the portal)

### App dependencies
All Python dependencies are stored in the requirements.txt file. To install them, using Visual Studio 2019 Community Edition:
1. In the Solution Explorer, expand "Python Environments"
2. Right click on "Python 3.7 (64-bit) (global default)" and select "Install from requirements.txt"

## Troubleshooting

- Mac users may need to install `unixodbc` as well as related drivers as shown below:
    ```bash
    brew install unixodbc
    ```
- Check [here](https://docs.microsoft.com/en-us/sql/connect/odbc/linux-mac/install-microsoft-odbc-driver-sql-server-macos?view=sql-server-ver15) to add SQL Server drivers for Mac.