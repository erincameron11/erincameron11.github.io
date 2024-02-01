---
title: 'Balloon Pop - JavaScript'
date: 2024-01-24
permalink: /posts/2024/01/balloon-pop/
tags:
  - JavaScript
  - CSS
  - HTML
  - Express.js
  - node
---

Creating an interactive application using front-end technologies for blowing up a balloon.

## Introduction
The aim of this project is to use CSS and HTML to design a front-end UI of a balloon, and animate it using JavaScript. When a user "blows" up the balloon, the balloon inflates. But be careful, once the balloon hits its maximum size, it pops!    


## Technologies
This application was built with the following technology:
* JavaScript
* HTML
* CSS
* Express
* node  
  

## Implementation
The application was implemented in Visual Studio Code. Audio input was utilized to sense blow intensity.   

![Balloon Start](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/balloon-start.png)   

Once the intensity passes a certain threshold, the balloon begins to inflate. 
![Small Balloon](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/balloon-small.png)   

![Medium Balloon](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/balloon-medium.png)   

![Large Balloon](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/balloon-large.png)   

If the balloon reaches a specific randomized size, the elastic of the balloon can no longer take the stretching and pops! A sound bite of a balloon popping is played, and the Restart button displays.   

![Balloon Restart](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/balloon-restart.png)   

HTML and CSS were used for front-end styling of the balloon, and animation. JavaScript was used to accept and process audio input from the users microphone. This audio input was then analyzed to find the average sound intensity input, and then this data was used to create balloon animations and actions.   


## Run
To run the application follow the steps below:
1. Clone this repo
2. Navigate to the applications `server` folder on your computer
3. Run the following command in the terminal: `node app`
  * Note: if you do not have npm or node installed, visit `www.npmjs.com` to download
4. Open a web browser and type in `localhost:3000/index.html`


## Code Creation
To create the code infrastructure I followed the below steps using Github, NodeJS and Express:
1. Create a new Github repository, and copy the HTTPS URL.
2. Navigate to the location you would like the repository on your machine. Run the command in the terminal `git clone <HTTPS_URL>`
3. Open the folder in a text editor (I used VS Code)
4. Create a new folder `server`
5. Inside `server`, create a new file called `app.js`, and a new folder called `public`
6. Navigate to the new `server` folder in your terminal using `cd` and type the following commands:
  * `npm init --y`
  * `npm i express`
Once the application is coded and you want to serve the application, follow the instructions above in `Run` section

Ref: https://www.youtube.com/watch?v=fyc-4YmgLu0