---
title: 'Electronic Health Records UI Application'
date: 2023-12-05
permalink: /posts/2023/12/electronic-health-records/
tags:
  - Java
  - CSS
  - JavaFX
  - FXML
---

Create a basic Electronic Health Records (EHR) application User Interface (UI).

## Introduction
An Electronic Health Records (EHR) application provides a secure portal for both Patients and Health Care Providers (HCP) to access confidential health records and medical information. The aim of this project is to design a simplified UI of the application for faster turnaround.    


## Assumptions
Below I discuss Assumptions to aid in defining the project scope that apply to both the minimum viable product as well as a full system design for future development:
* The design of this application specifically caters to the needs of a doctor's office, but could be extended in future development for use in specialized clinics and hospitals by creating further functionality and modules
* Different interfaces should display based on a User’s Permission status, outlined below:
  * Health Care Providers’ Permission – “HCP”
  * Patients’ Permission – “PATIENT”
* All users should be able to perform basic operations, such as:
  * Login, logout, perform password recovery
* A HCP user should be able to perform Create, Read, Update, Delete (CRUD) operations throughout the application, such as:
  * Search for patients in the database, read the Patient Overview page including the patient synopsis and medical history sections, read upcoming Appointments, read Medical Information previous doctor visit notes (but not able to delete notes), read Lab Results, and create a Lab Requisition.
* A Patient should be able to perform CRUD operations within the application, such as:
  * Read the Patient Overview page including the patient synopsis and medical history sections, read upcoming appointments, create a new appointment, read Medical Information previous visit doctor notes, and read Lab Results.   


## Modules
The modules are divided into a split hierarchy based on what Permissions the User has. If the user has Health Care Practitioner (HCP) Permissions, they follow the left arm of the hierarchy tree, and if the user has PATIENT Permissions, they follow the right arm of the hierarchy tree. I designed the application to follow a two-pronged hierarchical approach to allow for scalability of the application. In addition to this, both the Patient and HCP views share a nearly identical structure, promoting reusability, with the inclusion or exclusion of specific functionalities based on the user's permissions. Modules include: Login, Forgot password, Home, HCP Home, HCP Search, Medical Information, HCP Medical Information, HCP New Chart, Appointments, HCP Appointments, Lab Results, HCP Lab Results, and HCP Lab Requisition pages.   

![EHR Application File Structure](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig1.png)

## HCI Fundamentals
The HCI Fundamentals of the design are described below. The interface was designed based on the 8 Golden Rules of Interface Design, and can be seen through the following examples:
* Strive for consistency – All fonts, buttons, colours, layouts, navigation, verbiage, actions, and dissemination of information throughout the application is consistent.
* Universal usability – The design is intended to be deployed worldwide, for users of all ages, abilities, and different technologies as it is a very simple interface with basic features that enable users to understand the content immediately.
* Offer informative feedback – When a user enters incorrect information during login, the system offers feedback by displaying red text, and guiding the user to input correct information.
* Design dialogs to yield closure – Dialog boxes give an explanation for the event, like success in scheduling an appointment, and provides an avenue to move forward through a Continue button.
* Prevent errors – Form fields accept only a certain type of data format. For example, the email address field only accepts xxx@xxx.xxx format, and menu items appear grayed out when they are not meant to be clickable.
* Permit easy reversal of actions – There are Cancel buttons included on all forms to undo actions, such as creating a new Lab Requisition. In addition, required form fields validate the input, and display errors in red highlighting and text to reverse any data entry errors.
* Keep users in control – The design ensures that users remain in control over the interface by never revoking control from the users' input devices (mouse and keyboard).
* Reduce short-term memory load – The application is very straightforward, and simple to use, and therefore does not require the user to memorize large amounts of data.

Some further fundamental design considerations were made outside of the recommendations made in the 8 Golden Rules, and are pertinent to a well-rounded end product:
* **Colour** – The interface was designed using a monochromatic styling, with accent colours of only blue and red, as these are the only colour-blind safe colours for users with visual disabilities.
* **Primary Interaction Style** – Direct Manipulation was utilized as it is an excellent technique for novice users, and can be seen in the design through the use of the pop-up calendar DatePicker on the Appointments Page using the point-and-click method. This method of date selection allows a user to perform “rapid, incremental, reversible actions” (Shneiderman, 2016, p.232) by re-selecting different dates on the calendar widget. 
* **Navigation Design** – The navigation menu was designed in the selection interaction style that allows point-and-click selection. Navigation design techniques were implemented in the design, including the Content Organization arrangement being displayed in a ‘most frequently used links first’ hierarchical structure, darker Colour of the menu items indicating active links, Menu Phrasing consisting of concise 1-2 descriptive words, Error Prevention with items that users should not be able to click on have been disabled and appear grayed out, and Error Correction as the interface allows users to backtrack when necessary by clicking on the desired page in the menu.
* **Form Design** – Forms have been used sparingly within the design to avoid the overuse of data entry for users. In the cases where form fill-in was necessary, the following form design choices were followed: each form includes a Meaningful Title to identify the action being performed, Instructions clearly indicate what data to enter in each field, Field Labelling for all fields are presented in a fixed format to allow for directions on where to enter data, Accessibility alternative text has been included for logos and text fields to allow screen readers to interpret the interface correctly, Prompt Text is displayed to aid in data-type signaling, and Required Fields are clearly marked on each form with the traditional red asterisk so the user knows what fields are necessary to complete to be able to progress through the form and submit.
* **Dialog Design** – Dialog boxes are small windows that are used in interface design to interrupt the user to allow for important selections, or notifications. Dialog boxes are used sparingly in the interface design, and includes some main features such as: Meaningful Titles that describe the nature of the notification such as “Successful Chart Submission”, Consistency in sizing and colour to allow users to recognize when a dialog box appears, Limiting Occlusion in order to avoid obstructing the main page behind the dialog box, Noticeability through the different colouring of the dialog box that allows users to easily distinguish the difference between the main pages and a dialog box that requires attention, and Sequencing of elements on the dialog box follows the top-left to bottom-right typical sequencing, where the information starts in the top-left corner, and leads the user to the bottom-right.   


## Technologies
This application was built with the following technology
* JavaFX (version 21.0.1)
* FXML
* Java (version 20.0.2)
* Eclipse IDE (version 4.29.0)  
  

## Login
Login information for both a Patient and HCP user are below:     
Patient:   
`Email address: pat@email.com`   
`Password: health456`.  

HCP:   
`Email address: hcp@email.com`.  
`Password: admin123`   

## User Interface
The source code can be found at: <a href="https://github.com/erincameron11/electronichealthrecordsUI">https://github.com/erincameron11/electronichealthrecordsUI</a>

**All Users View:**
![EHR Login](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig2-3.png)
![EHR Forgot Password](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig4-5.png)

---

**Patient View:**
![EHR Patient View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig6-7.png)
![EHR Patient View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig8-9.png)
![EHR Patient View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig10.png)

-- 

**Health Care Practitioner View:**
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig11-12.png)
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig13-14.png)
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig15-16.png)
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig17-18.png)
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig19-20.png)
![EHR HCP View](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/ehr-fig21-22.png)