# Link to Webapp 

https://wb-dashboard-flask-akash.herokuapp.com/

# World Bank API Data Dashboard using Flask

This is a flask app that visualizes data from the world bank API. 
Data is pulled directly from the API and then visualized using Plotly.

## Getting Started 

To deploy the app to Heroku, follow the instructions given below.

## Prerequisites

To install the flask app, you need:
- python3
- python packages in the requirements.txt file

 Install the packages with
``` 
pip install -r requirements.txt
```

## Branches

The `master` branch contains code that can be run in a local environment. 
The `heroku` branch contains code that can be deployed over to [Heroku](https://www.heroku.com/).

## Deploying to Heroku

1. Go to www.heroku.com and create an account if you haven't already.

2. Move everything from the root directory to a directory called _web_app_

3. Create a virtual environment. Note that you can create the virtual environment inside the web_app folder. But then you would end up uploading that folder to Heroku unecessarily. Consider creating the virtual environment in a different folder. Or alternatively, you can create a .gitignore file at the root folder so that the virtual enviornment folder gets ignored.

4. pip install the libraries needed for the web app. In this case those are flask, pandas, plotly, and gunicorn.

5. Next install the heroku command line tools with the following command:

   ```
   curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
   ```

   https://devcenter.heroku.com/articles/heroku-cli#standalone-installation

6. Then check the installation with the command:

   ```
   heroku --version
   ```

7. Next, log into heroku using the command:

   ```
   heroku login
   ```

   and then enter your email and password when asked.

8. Remove `app.run()` from the `worldbank.py` file (if not already done)

9. Go into the web_app folder with:

   ```
   cd web_app
   ```

10. create a procfile with the command

    ```
    touch Procfile
    ```

    and put the following in the `Procfile`

    ```
    web gunicorn worldbank:app
    ```

11. Then create a requirements file with this command:

    ```
    pip freeze > requirements.txt
    ```

12. Next, initialize a git repository with the following commands:

    ```
    git init
    git add .
    ```

13. Configure the email and user name, you can use these commands:

    ```
    git config --global user.email email@example.com
    git config --global user.name "my name"
    ```

14. Make a commit with this command:

    ```
    git commit -m "first commit"
    ```

15. Create a uniquely named heroku app. Use this command:

    ```
    heroku create my-app-name
    ```

    If you get a message that the app name is already taken, try again with a different app name until you find one that is not taken.

16. Check that heroku added a remote repository with this command:

    ```
    git remote -v
    ```

17. Push the app to Heroku:

    ```
    git push heroku master
    ```

18. Go to the link for your web app to see if it's working. The link should be https<nolink>://app-name.heroku.com.

