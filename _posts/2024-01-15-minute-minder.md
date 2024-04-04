---
title: 'Minute Minder - JavaScript'
date: 2024-01-15
permalink: /posts/2024/01/minute-minder/
tags:
  - JavaScript
  - CSS
  - HTML
  - Express.js
  - node
---

An interactive application using front-end technologies for time tracking of various tasks.

## Introduction
The aim of this project is to use CSS and HTML to design a front-end UI of a time-tracking software, and build in functionality using JavaScript. 

Users have the ability to:
* Create new tasks
* Cancel the creation of a new task
* Start, stop and reset timers for each task
* Delete old tasks from the list

When a user inputs information for one task they have the option of tracking the time for that task. The user has the options of `Start`, `Stop`, and `Reset` on the timer for full control of task tracking, and `Cancel Task` if they change their mind. Once finished, the `Complete` button logs the time in the table. At this point, a `New Task` can be created for tracking, or old tasks can be deleted.    

Below is an image of an already-tracked task, and an ongoing task below it.   

![MinuteMinder - Running Task](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/minute-minder-task-running.png)   

Below is an image of two tracked tasks, with the options to Delete the tasks.   

![MinuteMinder - Task Done](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/minute-minder-task-done.png)   


## Technologies
This application was built with the following technology:
* JavaScript
* HTML
* CSS
* Express
* node  
  

## Implementation
Minute Minder's time tracking table allows users to enter in tasks and track the amount of time they spend on each task. The table is broken down into the following columns:
* Users can be selected by a dropdown for each task.
* A task description must be entered for each task tracked. This section is editable, only when the task is currently being tracked. Once the task-tracking is finished, the description can no longer be edited.
* The Start Date automatically uses the current date. 
* Track Work includes `Start`, `Stop`, and `Reset` buttons for the timer
* The Total Time counts up in an `HH : MM : SS` format. If a task is completed prior to selecting `Stop`, the application automatically stops the timer at this moment to track the time.
* The `Complete`/`Delete` button section completes a time tracking session, and deletes the selected time tracking session, respectively.

The application was implemented in Visual Studio Code using HTML, CSS, JavaScript, Express, and node.

JavaScript DOM EventListener's were used to track button clicks on the application, and trigger actions. A timerUtility() function was created to operate the timer clock hours, minutes, and seconds correctly.


## Run
To run the application follow the steps below:
1. Clone the following repo: `https://github.com/erincameron11/minuteminder`
2. Navigate to the applications `server` folder on your computer
3. Run the following command in the terminal: `node app`
  * Note: if you do not have npm or node installed, visit `www.npmjs.com` to download
4. Open a web browser and type in `localhost:8888/index.html`


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