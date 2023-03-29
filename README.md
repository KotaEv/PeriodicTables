# Capstone: Periodic Tables

## Description
The Periodic Tables full stack application is a restaurant reservation system utilized by restaurant personnel when a customer calls to request a reservation. The application allows employees to create, edit, or cancel reservations as well as search for reservations already created in the database with the attached phone number. The application also allows the user to seat reservations and keep track of the tables that are occupied or free for further use. 
NOTE: This project was completed as the final capstone for the Thinkful Software Engineering Bootcamp.

## Application
[Periodic Tables](https://periodic-tables-front.vercel.app/dashboard)

## Table of Contents

* [Tech Stack](#tech-stack)
* [File Management](#file-management)
* [API](#api)
* [Features](#features)
* [Installation](#installation)
* [Tests Information](#running-tests)

## Tech Stack

### Front-End:
-	React
-	JavaScript
-	CSS3
-	HTML5
-	Bootstrap
### Back-End:
-	Node.js
-	Express.js
-	PostgreSQL
-	Knex
-	Moment.js

## File Management

This repository is setup as a monorepo, meaning that the frontend and backend projects are in one repository. This allows for opening and editing in the same editor window.

| Folder/file path | Description                                                      |
| ---------------- | ---------------------------------------------------------------- |
| `./back-end`     | The backend project, which runs on `localhost:5001` by default.  |
| `./front-end`    | The frontend project, which runs on `localhost:3000` by default. |

## API
The API is built using RESTful API principles. This API allows for creation, reading, and updating reservations. The user can also create and read tables, and update the status of the table from occupied to free. There is currently not capability for the user to delete reservations or tables at this time.

### Endpoint Description:
- GET /reservations returns all reservations
- POST /reservations creates and returns a new reservation
- GET /reservations?date='YYYY-MM-DD' returns reservations by date (sorted asc)
- GET /reservations?mobile_number=123 returns reservations by partial match of phone number
- GET /reservations/:reservationId returns reservation matching the reservationId
- PUT /reservations/:reservationId updates and returns the reservation matching the reservationId
- PUT /reservations/:reservationId/status updates only the status of a reservation
- GET /tables returns all Tables
-	POST /tables creates and returns a new table
-	PUT /tables:table_id/seat updates a table with a reservationId and changes status to "occupied"
- Delete /tables:table_id/seat updates a table by deleting reservationId and changes status to "free"


## Features

### Dashboard
Reservations and tables are managed through the dashboard screen. By default, the dashboard will list reservations for the current day (today). Using the ‘previous’ and ‘next’ buttons, the user can navigate through reservations by date.
Tables and their availability are displayed below the current day’s reservations.

### Create a Reservation
Users can create a new reservation by selecting the ‘New Reservation’ button in the sidebar menu.
All of the form fields are required, and an error banner will appear if the user enters incorrect data.

### Edit a Reservation
Users may edit an existing reservation by selecting the ‘Edit’ button on the reservation listing. All fields can be edited, but the same restrictions apply as when creating a reservation.

### Seat a Reservation
Reservations can be seated at a table by selecting the ‘Seat’ button on a reservation display. Tables with capacities smaller than the reservation’s party size cannot be selected. Selecting ‘Seat’ and confirming set the reservation status to ‘seated’ and the table status to ‘occupied’.

### Search Reservations
Users are able to search for existing reservations by the phone number associated with the reservation. This feature can be found by selecting the ‘Search’ button in the sidebar.

### Add Tables
Users are able to add additional tables based on the restaurants needs by clicking the ‘New Table’ button on the sidebar. All of the fields are required.

### Finish a Reservation
Once a reservation has finished at a table, the user can select the ‘Finish’ button. This will set the status of the reservation as ‘finished’ and the table will return to the ‘free’ status and a new reservation can be placed at the selected table.


## Installation
1.	Fork and clone this repository.
1.	Run npm install to install dependencies.
1.	Run npm run start:dev to start the application


