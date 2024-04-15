---
title: 'Currency Converter - React'
date: 2024-04-14
permalink: /posts/2024/04/currency-converter/
tags:
  - React
  - Next.js
  - TypeScript
  - Tailwind CSS
  - ESLint

---

A Next.js React application using front-end technologies to create a Currency Converter UI, pulling up to date currency conversion rates from an exchange rate API.

## Introduction
A simplistic currency converter application that allows a user to:
* Input an initial currency
* Input monetary value for the initial currency
* Input a currency to convert to
* View the currency conversion output    



![Currency Converter](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/currency-start.png)   


## Technologies
This application was built with the following technology:
* React - Next.js
* TypeScript
* Tailwind CSS
* ESLint
  

## Implementation
The application was implemented in Visual Studio Code.  

The aim of this project is to use the Next.js React framework and CSS to design a front-end UI of a Currency Converter form, and make API fetch calls to calculate the conversion with the most current exchange rates. When a user enters in an initial monetary value, initial currency, and exchange-to currency, they can then click the "Convert" button to view the output. If a user attempts to enter incorrect currencies, an error will display.

The application was built using two main components: `CurrencyForm.js` and `CurrencyWrapper.js`. The `CurrencyWrapper.js` imports the `CurrencyForm.js` and displays it as output. 

React States were used to track the input of data into the form fields. The `CurrencyForm.js` uses handler functions to set the states of each value entered into the input fields of the form. When a user clicks `Convert`, `preventDefault()` is first called to prevent the page from reloading. The API URL is defined, using the state value of countryOne. An API fetch call is initiated to this URL, and data is retrieved from the API. Using this data, we locate the conversion rate, calculate the converted value, set the second currency value, and catch any errors that occur.
  


Below is an image of a conversion from CAD to USD.   

![Currency Converted](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/currency-ok.png)   


  
Below is an image of an error when a user enters an incorrect currency value of "CA" instead of "CAD".   

![Currency Error](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/currency-error.png)      


## Run
To run the application follow the steps below:
1. Clone the following repo: `https://github.com/erincameron11/react-currency-converter`
2. Navigate to the new repo on your machine, and into the `currency-app` folder G
3. Get the development server running by typing `npm run dev`.
4. Open in a browser using the link [http://localhost:3000](http://localhost:3000).
