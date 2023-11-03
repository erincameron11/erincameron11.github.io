---
title: 'Health Information - JSON to HTML'
date: 2021-01-24
permalink: /posts/2021/01/health-information/
tags:
  - JSON
  - HTML
  - formatting
  - jupyter notebook
  - python
  - npm
---

A simple web application that parses a JSON file to display patient data in HTML.

## Objective:
The objective of the project was to create a simple web application that can parse the `patient.json` JSON file and display the following patient data in HTML:

`Name of patient: <name>`   
`Organization name: <org_name>`   
`Gender: <gender>`   
`Number of conditions they have: <number>`   
`List of all conditions: <conditions_bullet_list>`   


## Tech Stack:
The application uses the following technologies:
* HTML to format the web page
* CSS for page styling
* JavaScript for inline scripts that grab data from the JSON file and place the data into the correct locations in the HTML page


## Installation & Dependencies:
1. Clone the `github.com/erincameron11/health-information` github repo in your terminal

2. Navigate to the folder `parse-json` in your terminal

3. Install npm with command: `npm install`
    * If you do not have npm installed, first download nodejs: `https://nodejs.org/en/download/`. To check if you have it installed type command `node -v`

4. Install python3 by visiting <a href="https://www.python.org/downloads/">python's site here</a> to download. 
    * To check if you have installed it correctly use command `python3 -version` on Mac, and `python --version` on Windows


## Run:
5. Once python3 has been downloaded, serve the application via python's SimpleHTTPServer module with command: `python3 -m http.server 8000` for Mac and `python -m http.server 8000` for Windows

6. To view the application in a browser type the following into the URL: `localhost:8000/index.html`


## Output:
Once the application has been served to the browser, the output will look something like below:
![Health Information HTML Site](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/health-information-html.png)

The application uses HTML to format the web page in a table layout. CSS is then used for page styling. Finally, JavaScript is used for inline scripts that grab data from the JSON file and place the data into the correct locations in the HTML page.