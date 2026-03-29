---
icon: globe
---

# Geodesk User Manual

## Geodesk User Manual

Welcome to **Geodesk.ai**, a user-friendly tool designed to integrate your assay data with the comprehensive OSNACA database seamlessly and use Machine Learning to generate valuable insights. This manual will guide you through the key features, functions, and steps needed to make the most of Geodesk.

### 1. Introduction

Geodesk helps geologists and researchers upload, analyse, and compare their assay data with the OSNACA database. With built-in data validation, machine learning models, and visualisation options, it provides valuable insights that can be tailored to your preferences.

### 2. Getting Started

The purpose of this user manual is to guide the new developers on setting up the project on their local machine.

The user needs the following to get started:

* Prerequisites (e.g., required software, versions, libraries, and dependencies)
* Instructions for cloning the repository and setting up the environment (e.g., virtual environments, package managers)
* Database setup and migration instructions
* Running the development server or build process
* Troubleshooting common setup issues

**High-level File Overview:** Explain the structure of the project directory and the role of key files and folders.

* Description of major directories (e.g., **`/views/`, `/models/`, `/templates/`, `/static/`**)
* Explanation of where business logic, templates, and front-end assets are located
* Naming conventions and file organisation rules, if any

**Front-end Details:** Describe the design and functionality of the front-end components, especially the spreadsheet interface and buttons.

* Description of key front-end files and how they interact with back-end logic
* Explanation of JavaScript/AJAX/ components
* Interaction patterns for user input and button functionality
* Any custom CSS or front-end libraries used: Bootstrap5

**Back-end Details:** Explain how the back-end processes user actions from the spreadsheet and the buttons.

* Explanation of the back-end routes and their functions
* Key Django views, controllers, and forms related to the spreadsheet
* Explanation of business logic (e.g., how button actions are processed)
* Any middleware or API interaction details with external services
* Explanation of session management, authentication, and authorisation (if applicable)

**Database Design and Management:** Provide details about the table schemas and how data is managed in the system.

* Overview of the database (e.g., PostgreSQL) and key tables
* Relationships between tables, constraints, and indexes
* How to perform migrations or updates to the schema
* Any database seeding or sample data for testing

**Testing and Debugging:** Provide instructions on testing the system and debugging common issues.

* How to run unit tests, integration tests, or end-to-end tests — we do not have any as described by Sahaj in Phase 1 due to the time constraints
* Explanation of test coverage and how to write new tests
* Check if Manual Testing is done: check if error pages are shown
* Debugging techniques (e.g., using Django debug mode, browser developer tools, logging)
* Common issues and solutions during development or in production

**Extending the System:** Give instructions for future developers on how to extend the system with new features.

1. Guidelines for adding new buttons and UI components:
   1. Add it to the corresponding tab
   2. If it is a POST request, make a unique URL for it
   3. If it is a GET request, you can choose to either make a new URL or add kwargs`?arg=something` to an existing GET request
   4. Create a function which handles functionality for the button and add context accordingly
   5. On the front end, add a new if statement with the other buttons in the menu tab to handle this view
      1. You can choose the action to either call a JS function that does something, activate a modal, or just a form whose action is the URL
      2. The JS function would this basic layout: (AJAX with alert)
2. How to extend the back-end logic for new features:
   1. Provide steps to ensure new features integrate smoothly with existing functionality
3. How to test and validate new features before deploying:
   1. Specifically, how to allow Admins to change information about existing Machine learning models?
4. How to allow more parameter options for each model type?

**Appendix:** Include references and supplementary information.

* Glossary of terms and abbreviations used in the project
* External links to documentation for libraries or frameworks used copiously in the system (e.g., Django, Bootstrap)
* Code snippets or examples of common patterns

#### System Requirements

* **Supported Browsers**: Chrome, Firefox, Safari, Edge
* **Supported File Formats for Upload**: CSV, Excel (.xls, .xlsx)

#### Login and Access

1. Visit the **Geodesk** web application.
2. Log in using your credentials or create a new account.
3. Navigate to the **Dashboard** to start your analysis.

### 3. Uploading Data

**Step-by-Step Instructions for Uploading Assay Data:**

1. **Navigate to the Upload Page**: Click on the **“Upload Data”** tab in the sidebar.
2. **Choose a File**: Select your assay data file from your device (formats supported: **CSV and Excel**).
3. **Data Validation**: The system will automatically validate your data for common issues such as:
   * Missing required fields
   * Incorrect data formats
4. **Error Notifications**: If there are any errors encountered, the system will display a detailed message about the problem. Fix these issues in your file and re-upload it.
5. **Successful Upload**: Upon a successful upload, a confirmation message will be displayed, and you can proceed with data analysis.

### 4. Element Matching with OSNACA Database

#### Automatic Matching:

1. Once your data is uploaded, **Geodesk** automatically matches your assay elements with the **OSNACA** database.
2. The successfully matched elements will be listed and aligned with the **OSNACA** reference data.
3. Any unmatched elements will be flagged, and you will have options to:
   * Ignore unmatched elements
   * Adjust your input data manually

### 5. Handling Missing and Detection Limit Values

Geodesk offers flexibility when dealing with missing values or values that are below detection limits in your data.

**Options for Handling Missing Data:**

1. **Replace with Zero**: Use this option to substitute missing values with zeros.
2. **Average Crustal Abundance**: Replace missing values with the average crustal abundance for the corresponding element.
3. **Half Detection Limit**: Use half the detection limit for values below the detection threshold.

Choose the option that best suits your dataset, and Geodesk will apply it consistently across your data.

### 6. Visualising Your Data

Visualising your data is crucial for identifying patterns and trends. Geodesk provides several options for creating graphs and charts.

Available Visualisations:

Steps to Generate Visualisations:

### 7. Machine Learning for Insights

Geodesk incorporates machine learning models to provide insights based on your uploaded data. These models can help you predict trends and classify elements in your assay data.

**Using the Machine Learning Models:**

1. **Select Analysis Type**: Choose the machine learning model suited for your data analysis (e.g., classification or regression).
2. **Train the Model**: Geodesk automatically trains the model using your data.
3. **View Results**: Once the training is completed, the model results will be displayed, including key metrics like accuracy and error rates.

#### Customising Machine Learning Parameters:

For advanced users, Geodesk allows adjustments to the machine learning model parameters:

* Change settings like learning rate, regularisation, or the number of epochs.
* Save custom configurations for future use.

### 8. Session Saving and Loading

#### Save Your Progress:

You can save your session at any point during analysis. This saves your uploaded data, visualisations, and any machine learning model settings you have applied.

#### Load a Previous Session:

To resume work, simply navigate to the **“Load Session”** tab, where you can select a previously saved session. Geodesk will restore your data and settings exactly as you left them.

### 9. Error Handling and Troubleshooting

Geodesk provides robust error handling to ensure a smooth user experience.

#### Error Messages:

* **Upload Errors**: Incorrect data formats or missing fields will trigger error messages with guidance on how to resolve the issues.
* **Analysis Errors**: Any issues found during analysis (e.g., invalid data input) will be flagged, with instructions provided for fixing them.

#### Support Resources:

If you encounter issues that you cannot resolve through the provided error messages, you can access:

* The **Help Guide**: Located in the **“Support”** section of the platform.
* **Contact Support**: Reach out to the support team via the **“Contact Us”** form or email.

### 10. User Support and Updates

Geodesk is constantly being updated with new features, enhancements, and data from the OSNACA database.

#### User Support:

* **Guides and Tutorials**: Access a library of tutorials to help you navigate and use different features of the tool.

#### System Updates:

Regular updates to Geodesk will introduce new features and improved functionality. Users will be notified about major updates, including how they will benefit from the new features.

### 11. Conclusion

Geodesk offers a comprehensive platform for geologists and researchers to analyse assay data, compare it with the OSNACA database, and gain insights using advanced machine learning models. With its intuitive interface, powerful analysis capabilities, and reliable support, Geodesk streamlines the process of turning data into actionable insights.

For more information, refer to the detailed help guides within the application or contact our support team for assistance.

## PLATFORM SETUP INSTRUCTIONS

To understand the Company Programming Guidelines, click [here](https://drive.google.com/drive/folders/1zdl1Sj5JfqQgwdTPyQeEQtGngYgkfSun?usp=drive_link).

### Install PostGIS Database

#### Installing PostGIS:

{% stepper %}
{% step %}
### 1. Install PostgreSQL

Navigate to [PostgreSQL](https://www.postgresql.org/download/). Install the latest version of **PostgreSQL**.

Open the downloaded setup file. Next, proceed with the default settings but, make sure to select the **“ADD TO PYTHON PATH”** checkbox or some other option similar to it.

_Note: If you were asked to create a password during the installation, use the password as **“pass”** (you can change this password later if you wish to)._

During the installation, under **Spatial Extensions**, select **PostGIS**.

_Note: If you encounter a checkbox to create a spatial database, avoid selecting it._
{% endstep %}

{% step %}
### 2. Continue the installation

Click **Next** to proceed with the installation process.
{% endstep %}

{% step %}
### 3. Finish setup

Once the installation finishes, the **SQL Shell** and **pgAdmin4** will be installed automatically.
{% endstep %}
{% endstepper %}

### pgAdmin4

#### Creating a New Database (Django):

{% stepper %}
{% step %}
### 1. Open pgAdmin4

Open **“pgAdmin4”** and log in with the password setup during the installation.
{% endstep %}

{% step %}
### 2. Create the extension

Go to **Servers** > **PostgreSQL 15** > **Databases** > **django** > **Extensions** and right-click on **Extensions** > hover on **Create** > select **Extension…**\
A Create - Extension dialog box is displayed.
{% endstep %}

{% step %}
### 3. Search for PostGIS

In the **Name** field, search for **“postgis”** extension from the options.
{% endstep %}
{% endstepper %}

### SQL Shell

**Opening SQL Shell:**

{% stepper %}
{% step %}
### 1. Open SQL Shell

Open **“SQL Shell”**.

_Note: Everything in square brackets is the default value. Hit enter to keep the default values. Only change the default value of Database to **django** and Password to **pass** (installation password)._
{% endstep %}
{% endstepper %}

### Using Terminal

{% stepper %}
{% step %}
### 1. Clone the repository and install Python

Clone this repo and change directory in the terminal to where the repo is stored.

Install **Python** version **3.8**.
{% endstep %}

{% step %}
### 2. Check Python and create the virtual environment

Execute the code in a terminal (use command prompt for Windows users):

1. Check if **Python version 3.8** is installed using **`py -0`**.
2. Create and activate the virtual environment using the below code:

```shell
py -3.8 -m venv venv
.\venv\Scripts\activate.bat
```
{% endstep %}

{% step %}
### 3. Install the required packages

Install all the required packages using the below code:

```shell
py -m pip install --upgrade pip setuptools wheel
pip install GDAL-3.3.3-cp38-cp38-win_amd64.whl
pip install -r requirements.txt
```
{% endstep %}

{% step %}
### 4. Verify installation

Check if the requirements were installed using **`pip list`**.
{% endstep %}
{% endstepper %}

### VS CODE EXPLORER

#### Navigating to Project Folder:

{% stepper %}
{% step %}
### 1. Copy the environment file

Navigate to the project's web folder and copy the contents of **`.env_defaults`** onto a new **`.env`** file.
{% endstep %}

{% step %}
### 2. Update `.env`

Make these changes in `.env` (use the installation password here).
{% endstep %}

{% step %}
### 3. Edit `admin.py`

Then, navigate to your virtual environment folder (**venv**) outside the web folder. Move to **venv** > **Lib** > **djconfig** > **admin.py** and edit **line 29**.

Change

**`from django.conf.urls import url`**

to

**`from django.urls import re_path as url`**
{% endstep %}
{% endstepper %}

### Final Steps

{% stepper %}
{% step %}
### 1. Run migrations

Make sure the directory is changed to `**web**` before executing the following (use the command prompt for Windows users):

```shell
cd web
python delete_migrations.py & python manage.py makemigrations & python manage.py migrate
```
{% endstep %}

{% step %}
### 2. Install Firefox

Install `**Firefox**` web browser (contains drivers needed for the platform).
{% endstep %}

{% step %}
### 3. Start the development server

Within the same terminal, execute: `**python manage.py runserver**`.
{% endstep %}

{% step %}
### 4. Open the application

Visit this link [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

Register an account and you are ready to use the application.
{% endstep %}
{% endstepper %}

### MacOS GDAL Installation

#### Installing Brew:

{% stepper %}
{% step %}
### 1. Install Brew

Install **Brew**.
{% endstep %}

{% step %}
### 2. Install GDAL

Run the following command in your terminal: `**brew install gdal**`.
{% endstep %}

{% step %}
### 3. Update `settings.py`

Open **web/main/settings.py** and add the following lines at the end of the file:

**`GDAL_LIBRARY_PATH = '/opt/homebrew/Cellar/gdal/3.5.3/lib/libgdal.31.dylib'`**

**`GEOS_LIBRARY_PATH = '/opt/homebrew/Cellar/geos/3.11.0/lib/libgeos_c.1.dylib'`**

Replace the version numbers with the versions you have installed.
{% endstep %}
{% endstepper %}

### Installation Errors

The following are solutions to the most common problems that are encountered during the setup. In case you are still unable to set up the platform, email [sahaj@orefox.com](mailto:sahaj@orefox.com) with a screenshot of the issue to help you out.

### Errors installing requirements.txt

{% stepper %}
{% step %}
### 1. Identify the package

Get the name of the package from the error displayed in the terminal.
{% endstep %}

{% step %}
### 2. Confirm it in `requirements.txt`

Confirm the package name in the **requirements.txt file**.
{% endstep %}

{% step %}
### 3. Comment it out

Add `**#**` to the left of the package name (this comments the package out of the installation process).
{% endstep %}

{% step %}
### 4. Save the file

Save the **requirements.txt file** using `**ctrl + s**`.
{% endstep %}

{% step %}
### 5. Run the installation again

Install the requirements file again `**pip install -r requirements.txt**`.
{% endstep %}

{% step %}
### 6. Repeat for all failing packages

Repeat the process for all packages that gave errors.
{% endstep %}

{% step %}
### 7. Install the commented-out packages

Install the packages that have been commented out using `**pip install <package name and version from the requirements.txt file**`, e.g. `**pip install Pillow==8.4.0**`.
{% endstep %}
{% endstepper %}

### MacOS Installation Issues

**In case you face an issue while installing gssapi:**

{% stepper %}
{% step %}
### 1. Fix the missing GSSAPI\_MAIN\_LIB variable

Fix the missing GSSAPI\_MAIN\_LIB variable using the command: `**export GSSAPI_MAIN_LIB=/System/Library/Frameworks/GSS.framework/Versions/Current/GSS**`.
{% endstep %}

{% step %}
### 2. Install Pillow

Install the Pillow package: `**pip install Pillow==8.4.0**`.
{% endstep %}
{% endstepper %}

### Windows GDAL Installation Issue

**If installing GDAL via pip does not work or is not recognized, do the following on both Windows 10 and 11:**

{% stepper %}
{% step %}
### 1. Check compatible tags

Run `**pip debug --verbose**` and search for compatible tags, e.g., **cp38-cp38-win\_amd64**.
{% endstep %}

{% step %}
### 2. Download the GDAL wheel

Download the GDAL wheel from Christoph Gohlke's Unofficial Windows Binaries for Python Extension Packages.
{% endstep %}

{% step %}
### 3. Match the wheel to the tags

Use the tags found above to determine which wheel you have downloaded.
{% endstep %}

{% step %}
### 4. Install the wheel via pip

Install via pip install `**/path/to/GDAL-3.3.3‑cp38-cp38-win_amd64.whl**` (or whatever wheel you have downloaded).
{% endstep %}

{% step %}
### 5. Find the DLL name

Navigate to `**/path/to/venv/Lib/site-packages/osgeo/**` and take note of the `**gdalXXX.dll**` file name e.g., `**gdal304.dll**`.
{% endstep %}

{% step %}
### 6. Add the DLL name to `libgdal.py`

Add the version name of the dll found above to the file here: `**/path/to/venv/lib/site-packages/django/contrib/gis/gdal/libgdal.py**`

```python
elif os.name == 'nt':

# Windows NT shared libraries
lib_names = ['gdal304', 'gdal300', 'gdal204', 'gdal203', 'gdal202', 'gdal201', 'gdal20']

# ^ add dll name to this array if its not there
```
{% endstep %}

{% step %}
### 7. Add the settings block if needed

If the following code does not exist (within the main folder project folder (not site-packages)), then add the following code block to your django settings.py before the initialization of any packages:

```python
if os.name == 'nt':
    VENV_BASE = os.environ['VIRTUAL_ENV']
    os.environ['PATH'] = os.path.join(VENV_BASE, 'Lib\\site-packages\\osgeo') + ';' + os.environ['PATH']
    os.environ['PROJ_LIB'] = os.path.join(VENV_BASE, 'Lib\\site-packages\\osgeo\\data\\proj') + ';' + os.environ['PATH']
```
{% endstep %}
{% endstepper %}

Finished! Now, continue with the regular setup of django.

_Note: If you are still encountering issues, you may need to install GDAL on Windows. Since there are no binaries available on the GDAL website and you have to build them yourself, the easiest way to install them is by using the network installer for OSGeo4W. Simply perform an express installation, ensuring that you select GDAL as an additional package._

### User Stories

**Below are the user stories:**

1. **User Story**: As a geologist, I want to upload my assay data to compare it with the OSNACA database.
   * **Acceptance Criteria**:
     * The system accepts multiple formats for data upload (CSV, Excel, etc).
     * Uploaded data is validated and any errors are communicated to the user.
     * Successful uploads are confirmed to the user.
2. **User Story**: As a user, I want the system to match my assay elements with the OSNACA database, so the data aligns correctly.
   * **Acceptance Criteria**:
     * The system identifies matching elements between user data and the OSNACA database.
     * Users are informed of successfully matched and unmatched elements.
     * The matched data is integrated for further processing.
3. **User Story**: As a user, I want to handle missing values and those below detection limits according to my preference, so that the data remains consistent.
   * **Acceptance Criteria**:
     * The system prompts users to decide how to handle missing or below detection limit values.
     * Users can choose among the average crustal abundance, or using half the detection limit.
     * The chosen option is applied correctly across the dataset.
4. **User Story**: As a user, I want to visualise my data to see patterns and trends.
   * **Acceptance Criteria**:
     * The system provides a range of visualisation options.
     * Users can select the type of visualisation they want.
     * The chosen visualisation is generated correctly with the cleaned and prepared data.
5. **User Story**: As a user, I want the system to train machine learning models on my data to make predictions and identify patterns.
   * **Acceptance Criteria**:
     * Machine learning models are trained on the user's data.
     * Users are informed when model training is complete.
     * The system provides results from the machine learning models in a user-friendly format.
6. **User Story**: As a user, I want a tool that handles errors robustly and offers comprehensive user support to navigate any issues or questions that arise.
   * **Acceptance Criteria**:
     * The system provides clear error messages when something goes wrong.
     * The system includes guides, documentation, or a chatbot to assist users.
     * Users can easily find and understand support resources.
7. **User Story**: As a user, I want a tool that is updated and improved continuously to benefit from the latest features and the most current data.
   * **Acceptance Criteria**:
     * The system is updated regularly with new features and improvements.
     * The machine learning models are updated as more data becomes available or as models improve over time.
     * Users are informed of updates and how they benefit from them.
8. **User Story**: As a user, I want to be able to save and load previous analysis settings and results, so that I can resume my work at a later time.
   * **Acceptance Criteria**:
     * The system allows users to save their current session, including uploaded data and analysis settings.
     * Users can load previously saved sessions.
     * Loaded sessions accurately restore the user's data and analysis settings.
9. **User Story**: As a geologist, I want to have access to interpretation tools to understand the output, so that I can make informed decisions.
   * **Acceptance Criteria**:
     * The system includes explanatory tooltips, guides, or tutorials.
     * These resources provide clear explanations of the analyses, visualisations, and machine learning outputs.
     * Users report increased understanding after using these tools.
10. **User Story**: As a user, I want the tool to normalise and standardise data, so that the scales are consistent across different datasets.
    * **Acceptance Criteria**:
      * The system applies normalisation and standardisation to the datasets as part of the data cleaning and preparation process.
      * This step improves the accuracy of visualisations and machine learning models.
      * Users can opt out of this step if they choose.
11. **User Story**: As a user, I want to validate the performance of the trained machine learning models to trust their predictions.
    * **Acceptance Criteria**:
      * The system provides validation measures (such as cross-validation scores, confusion matrices, or ROC curves) for the machine learning models.
      * Users can understand and interpret these validation measures.
      * Validation results show the models are performing reliably.
12. **User Story**: As a geologist, I want to be able to adjust and customise the parameters of machine learning models, so that I can tailor the models to my specific needs.
    * **Acceptance Criteria**:
      * The system allows users to change key parameters of the machine learning models.
      * Changes to parameters significantly alter the model's performance, allowing users to optimise the models for their data.
      * Users can save and reuse custom configurations for future analysis.

In conclusion, this user manual provides a comprehensive guide to help users get started, set up the platform, and understand the User Stories along with the acceptance criteria necessary for configuration in Geodesk.
