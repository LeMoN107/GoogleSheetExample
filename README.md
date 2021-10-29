# Google Spreadsheets on edit example

Through utilizing <a href="https://developers.google.com/apps-script/guides/triggers">simple triggers</a>, you're now able to send events to your scripts which trigger on user edits within a google spreadsheet.

* Obtain basic understanding of triggers in GoogleApi
* Easy to use and simple to understand code
* Add data to spreadsheet and update script
* Allows saved space in CPU and is the most efficient way to update once spreadsheet is edited.

# How it works
1. Through the use of <a href="https://flask.palletsprojects.com/en/2.0.x/">flask</a>, you're able to set up a local hosted server to recieve requests.
2. Then, using <a href="www.heroku.com">Heroku</a>, the user is able to host their site permanatly. 
3. Using google web api you're able to recieve trigger events which fetch this flask url
4. Adding what ever code you need into this Get section of the code (outlined in source) you're able to run information on spreadsheet updates.

# Usage
### Python Applications

#### Instructions

1. Follow <a href="https://docs.gspread.org/en/v4.0.1/oauth2.html">this guide</a> to set up a suitable google sheet and get required permissions to access sheet from developer account. 

2. Run the following code:
    ```diff
    git clone https://github.com/LeMoN107/GoogleSheetExample.git
    ```
3. In the downloaded folders dir, run ```python app.py``` to make sure the server works on ```localhost:3000```

4. Set up a free <a href="www.heroku.com">Heroku</a> account and follow the github repo installation steps.

5. On heroku, go to the deploy tab and manually deploy the application.
<br>
6. Press ```Open App``` on heroku to view your server.
<br>
7. Press More, and View logs on your main heroku screen, you should see ```Hello``` printed each time you access the site.
<br>
8. Go onto your Google Sheet, naviate to Tools, and script editor. Paste:
    ```diff
    function edit(){
       UrlFetchApp.fetch("https://YourHerokuServerDomain.com")
    }
    ```
9. Then access the ```triggers``` section on the left side of the Script Editor and run ```edit()``` on the function ```onEdit()```
