# Technical Docs

### Frontend Technology Stack

#### SharePoint Framework

SharePoint Framework (SPFx) is a development model provided by Microsoft for building web parts, extensions, and other customizations for SharePoint Online and SharePoint Server. SPFx enables extending SharePoint's functionality and integrating with other services.

#### TypeScript

TypeScript is a superset of JavaScript that adds static typing and other features for large-scale application development. It helps catch errors early and improves code maintainability and scalability.

#### React

React is a JavaScript library for building user interfaces. We use it to build the UI on top of SharePoint Framework.

#### Chart.Js

Chart.js is a JavaScript library for creating interactive and visually appealing charts and graphs on web pages. It's simple to use, customizable, and supports various chart types like line, bar, and pie. We use it as the primary data visualization library.

#### Mapbox-gl

Mapbox GL JS is a JavaScript library for embedding interactive, customizable maps into web applications. It utilizes WebGL for fast rendering, providing smooth, vector-based maps with various styling and data visualization options. Used for creating data visualizations that require maps.

#### Tailwind CSS

Tailwind CSS is a utility-first CSS framework that streamlines web development by providing pre-designed utility classes. It allows for rapid prototyping and customization, facilitating the creation of modern and responsive user interfaces.

#### Headless UI

A set of completely unstyled, fully accessible UI components, designed to integrate with Tailwind CSS.

#### SCSS

Used as a CSS framework to write styling in some UI components.

#### Fluent UI

UI library from Microsoft used in some components for tooltips and loading screens.

### Dependencies

Dependencies are external software packages or libraries that UNDP Performance leverages to function. These external dependencies provide reusable code, functionality, or resources that help us build and maintain the platform more efficiently.

* @fluentui/example-data
* @fluentui/react
* @headlessui/react
* @heroicons/react
* @microsoft/microsoft-graph-types
* @microsoft/sp-component-base
* @microsoft/sp-core-library
* @microsoft/sp-lodash-subset
* @microsoft/sp-office-ui-fabric-core
* @microsoft/sp-property-pane
* @microsoft/sp-webpart-base
* axios
* chart.js
* chartjs-funnel
* chartjs-gauge
* chartjs-plugin-annotation
* chartjs-plugin-datalabels
* classnames
* jszip
* mapbox-gl
* office-ui-fabric-react
* react
* react-chartjs-2
* react-country-flag
* react-dom
* react-gauge-component
* react-heatmap-grid
* react-hotkeys-hook
* react-router-dom
* tslib

### Backend Technology Stack

#### Azure Services

Used the following Azure services for deployments and data storage:

* Azure HTTP trigger functions
* Azure time trigger functions
* Azure blob storage
* Azure SQL database

#### Python

Used for data cleaning and testing.

#### Dotnet

Read data from data cube and data warehouse and upload this data to Azure storages. This is the only use of dotnet.

### Dependencies

* @actions/exec
* @azure/functions
* @babel/core
* @babel/preset-env
* @babel/preset-typescript
* @fluffy-spoon/substitute
* @types/jest
* @types/node
* @typescript-eslint/eslint-plugin
* @typescript-eslint/parser
* babel-jest
* copyfiles
* cross-env
* eslint
* eslint-config-prettier
* eslint-plugin-prettier
* eslint-plugin-react
* jest
* jest-junit
* prettier
* rimraf
* ts-jest
* ts-node
* typescript
* @azure/storage-blob
* arquero
* axios
* data-forge
* data-forge-fs
* dotenv
* js-xlsx
* xlsx

### System Architecture

<figure><img src="../.gitbook/assets/technical diagram.png" alt=""><figcaption></figcaption></figure>

#### Data Sources

**Data Warehouse**

* A Microsoft SQL database containing a set of UNDP data.
* Read data using SQL queries.

**Data Cube (Azure Analysis Services Data)**

* Azure Analysis Services is a fully managed platform as a service (PaaS) that provides enterprise-grade data models in the cloud.
* Read data using MDX queries.

**Power BI Semantic Models**

* Read data from PowerBI dataset using DAX queries via PowerBI REST API.

**Manual Files**

* Manually upload files to Azure Blob storage raw folder.

#### Data Extraction

* A time-triggered Azure function is used to extract data from a Data Warehouse, Data Cube, and PowerBI.
* It periodically triggers to pull data, saving it in Azure Blob Storage and an Azure SQL database.
* Manual raw files are directly uploaded to Azure Blob Storage.

#### Data Cleaning and Pre-Processing

* Once the files are saved in the raw folder of Azure Blob Storage, an Azure function will be triggered for each file.
* This will clean the data and save it in a new folder in a common format:
  * `country,countrycode,bureau,year,<Other values columns (Value 1 Col, Value 2 Col)>`

**Additional Tasks**

* Transform all country names into a common format using the `country_lookup.xlsx` mapping file.
* Calculate individual indicator scores.
* Add new columns if required.
* Remove data columns if not required for visualizations.
* Transform data based on the requirements.

#### Data Visualization

* Data is served to the frontend via an Azure HTTP trigger function.
* Utilizes CSV files from Azure Blob Storage and data from the Azure SQL database.
