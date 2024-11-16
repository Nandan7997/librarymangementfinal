## Application Details
|               |
| ------------- |
|**Generation Date and Time**<br>Thu Aug 22 2024 08:37:23 GMT+0000 (Coordinated Universal Time)|
|**App Generator**<br>@sap/generator-fiori-freestyle|
|**App Generator Version**<br>1.14.4|
|**Generation Platform**<br>SAP Business Application Studio|
|**Template Used**<br>simple|
|**Service Type**<br>None|
|**Service URL**<br>N/A|
|**Module Name**<br>leftmenu|
|**Application Title**<br>App Title|
|**Namespace**<br>|
|**UI5 Theme**<br>sap_horizon|
|**UI5 Version**<br>1.127.1|
|**Enable Code Assist Libraries**<br>False|
|**Enable TypeScript**<br>False|
|**Add Eslint configuration**<br>False|

## leftmenu

An SAP Fiori application.

### Starting the generated app

-   This app has been generated using the SAP Fiori tools - App Generator, as part of the SAP Fiori tools suite.  In order to launch the generated app, simply run the following from the generated app root folder:

```
    npm start
```

#### Pre-requisites:

1. Active NodeJS LTS (Long Term Support) version and associated supported NPM version.  (See https://nodejs.org)
#### Library Management SAPUI5 Application
This SAPUI5 application serves as a library management system, providing functionalities like user authentication, navigation, user registration, and managing book-related data. It integrates with an OData service to perform CRUD operations on the backend.
#### Features
1.Left Navigation Menu
.Displays a list of navigable pages including:
.Home
.Student Registration
.Student Category Registration
.Book Issue Log Form
.Books Return Form
.Branches Form
.Books
.Book Categories
.Implements onItemSelect for page routing using the router.
3. User Authentication
.Login functionality (onLoginPress) to validate user credentials against OData records.
.Displays success or error messages based on authentication results.
4. User Registration
.Modal-based user registration using a custom fragment (leftmenu.view.RegisterUser).
.Fields include User ID, Name, Username, and Password.
.Validation checks:
.Ensures all fields are filled.
.Verifies UserId is unique and within the valid range (0–255).
.Creates a new user record in the OData service (onCreatePress).
5. Data Management
.Fetches user data (getTableData) and binds it to the view for dynamic updates.
.Uses ODataModel to read and create records on the /zusersSet entity set.

#### File Structure
#### Controller
.File: App.controller.js
.Implements core functionalities like:
.Initialization (onInit)
.Navigation and data fetching
.CRUD operations
.User authentication and registration handling
#### View
.Uses XML views to define the navigation menu, forms, and dialog fragments.
.Fragment: RegisterUser.fragment.xml for user registration.
.OData Integration
.Service URL: /sap/opu/odata/sap/ZLIBRARY_SRV/
.Entity Set: /zusersSet for user management.
.Data Models
.Navigation Model (leftmenuModel)
Holds the menu structure for navigation.

Example:
{
  "navigation": [
  
    { "title": "Home", "route": "home" },
    
    { "title": "Student Registration", "route": "page1" }
    
  ]
}
#### OData Model
Connects to the backend for dynamic data operations.

#### How to Run
#### Prerequisites
SAPUI5 development environment set up.
Backend OData service (ZLIBRARY_SRV) configured and available.
Steps
Clone or add this project to your SAPUI5 workspace.
Ensure the OData service /sap/opu/odata/sap/ZLIBRARY_SRV/ is accessible.
Deploy and run the application in your SAPUI5 environment.
Navigate through the pages and use the provided functionalities.
Key Functions
onInit
Initializes the router and sets up models for navigation and OData integration.
getTableData
Fetches user data from the backend and stores it in a JSON model.
onLoginPress
Validates user credentials against the backend records.
onRegisterPress
Opens the user registration dialog.
onCreatePress
Validates and creates a new user in the backend.
onItemSelect
Handles navigation to the selected menu item using the router.
Error Handling
Displays error messages using MessageToast and MessageBox for failed operations like data fetching or record creation.
Future Enhancements
Add input validation for all form fields.
Implement user role management for restricted access to specific pages.
Enable batch processing for OData requests.
Integrate additional pages for managing library assets like books and authors.
