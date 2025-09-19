# C1-web-dev-formative-assignment
This is group 6,
the members are: Irakora Des Gasana,
                 Isingizwe Aurore Marie Pascaline, Ishimwe Yvan Ralph and
                 Inema Amanda Leslie

                 
           Project overview      
 This project processes MoMo SMS data in XML format, cleans and categorizes the data, stores it in a relational database, and builds a frontend interface to analyze and visualize the data.
           
           
           Objectives aimed at when creating the project
Parse and clean raw SMS data from XML files.
Categorize transactions into the given types.
Store structured data in a relational database.
Build a user-friendly dashboard website that help to visualize the transactions in different formats.

Features
Backend:

Parses and cleans MoMo SMS XML data.
Stores processed data into a MySQL database.

Frontend:

Dynamically displays data using JavaScript.
Allows filtering of transactional data based on user preferences.
Generates interactive charts for data visualization.

Technologies Used

Backend:
Python (with FastAPI for API development)
MySQL (for data storage)
XML Parsing Libraries (for handling SMS data)

Frontend:
HTML
CSS
JavaScript
         
         Architecture diagram created:

1. Development Workflow Chart

Complete Git branching strategy
Pull request and code review process
Testing and documentation requirements
Merge and deployment flow

2. Data Flow 

Visual representation of ETL process
Shows data transformation stages
Includes error handling (dead letter )
Storage and frontend visualization layers

3. Technology Stack Architecture

Layered architecture visualization
Frontend, API, Backend, and Storage layers
Technology dependencies and connections

4. Project Management Workflow

Git branching 
Feature branch examples (XML parser, data cleaner, dashboard)


5.  Planning & Task Flow

Scrum workflow visualization
Backlog to sprint planning process
Daily standup and task movement
Provides APIs to retrieve data using FastAPI.


### Setup Database
1. First create Database 
mysql -u username -p -e "CREATE DATABASE momo_sms;"
2. Run Import command
mysql -u username -p database_name < momo_sms_backup.sql


The link for the diagram :(https://drive.google.com/file/d/1iDtIdav-qSg7X8-AtWlEIHjRkuAnIz2d/view?usp=sharing)

This is the link to our scrum board: https://app.clickup.com/90121199296/v/b/2kxu8qp0-212

This is the link for database documentation :https://docs.google.com/document/d/1fbD71wfCGhUVtXfMK0qPDAimaabetJOKBJJPuYlsm38/edit?usp=sharing
