# Cumulocity Digital Twin Manager

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
	- [Installation of Web application](#for-installation-of-web-application)
	- [Installation of Microservice](#for-installation-of-microservice)
	- [Configure a role for Bulk Import](#configure-a-role-to-use-the-bulk-import-feature)
	- [Subscribing for Feature Branding](#subscribing-for-feature-branding)
- [Features](#features)
	- [Overview](#overview-of-features)
   	- [Assets](#assets)
   	  	- [Asset hierarchy](#asset-hierarchy)
   	  	- [Creating assets via UI](#creating-assets-via-ui)
   	  	- [Creating assets via bulk import](#bulk-import)
   	  	- [Viewing assets](#view-assets)
	- [Asset properties](#asset-properties)
	- [Asset models](#asset-models)
	- [Localization](#localization)

## Overview

The `Digital Twin Manager` enables you to create and manage assets around your physical connected devices in Cumulocity IoT. Assets can be used to structure and describe devices in logical hierarchies as encountered in the real world environment. In addition, assets in Cumulocity IoT can be extended and enriched with addtional information using the `Asset properties`.

The home screen of the DTM application gives an overview of the application. You can see the number of asset models, asset properties and assets available at a glance. You can add asset properties, asset models and assets using the quick links.

 **You cannot create asset models, properties and assets if you dont have inventory admin permission.**

`Note: Digital Twin Manager is supported on Cumulocity UI and microservice version of 10.14 and above`

## Installation

The `Digital Twin Manager` is shipped as a standalone application for now. This means it will be installed as a separate application, which provides all the features of the
`Digital Twin Manager` as described in the [features](#features) section. The standalone application is available in the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
and can be downloaded.

### For installation of web application:

1. Download dtm-ui.zip from the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
2. Open the `Administration` application in your Cumulocity tenant
3. Navigate to `Ecosystem` --> `Applications`
4. Click on `Add application`
5. Select `Upload web application` in the modal dialog
6. Select the zip archive, which you downloaded from the release section, to upload it to the tenant

![DTM installation gif](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/cd1016a3-f52b-407c-b8e0-f5f5deb6a834)

After following these instructions, the application will be deployed on the tenant and is ready for use. In the application switcher on the top right you can now select the `Digital Twin Manager` application.

If you want to use `Import assets` functionality, then the microservice needs to be installed.

### For installation of microservice:

1. Download dtm-ms.zip from the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
2. Open the `Administration` application in your Cumulocity tenant
3. Navigate to `Ecosystem` --> `Microservice`
4. Click on `Add microservice`
5. Select Upload microservice in the modal dialog
6. Select the zip archive of microservice, which you downloaded from the release section, to upload it to the tenant
7. When prompted Subscribe to microservice select Subscribe

After following these instructions, the microservice will be deployed on the tenant. Once the microservice is deployed you can use `Import Assets` feature.

`Note: If the microservice is deployed but not subscribed, then the Import Assets button will not visible in assets page.`

### Configure a role to use the bulk import feature

1. Navigate to the `Administration` application via the application switcher in the top right corner.

2. Under **Quick links** click **Roles**.

3. In the **Global roles** tab, select a role to which the permission has to be provided.

4. Set **Admin** permission level for **Digital Twin** type in the "Permissions" section.

5. Click **Save**.

Once the permission is assigned, the bulk import feature can be used.

`Note: If the permission is not assigned, then the CSV template will not be downloaded correctly.`

### Subscribing for Feature branding

To use Localization feature, you must have public-options web application installed on the tenant.  One of the ways you can get the public-options web application is by subscribing to **Feature Branding**.  The following are the steps:

Log in to the corresponding management tenant as an administrator
1. Navigate to **Tenants > Subtenants**
2. Select the subtenant for which you want to add this feature.
3. Under **Applications** subscribe for **Feature branding**.

Complete the setup by following the below steps on the tenant where you want to use Localization feature

1. Log in as an administrator of the tenant.
2. Navigate to **Administration > Ecosystem > Applications**. Under **Features**, make sure **Feature Branding** is subscribed.
3. Navigate to **Settings > Branding**, and click on Apply. Once done, make sure you can see public-options web application under **Ecosystem > Applications**.

`Note: If you don't have the access for the tenants, please contact your administrator.`

## Features

### Overview of features

The `Digital Twin Manager` consists of the following features:

* `Assets` - Lists all the available assets and its hierarchy which are created using asset models and properties.
* `Asset properties` - Create your own asset properties (simple or complex) to define how data should be stored on an asset
* `Asset models` - Define asset models to describe the blueprint of your assets
* `Localization` - Dynamically translate asset model and asset property descriptions to multiple languages.

### Assets

Assets are the digital representation of physical assets. An asset in DTM application can contain subassets and devices. Initially, no assets are displayed in the `Assets` page by default. If you have already created assets, you find them listed with its hierarchy.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/0a761daf-64c7-4bf7-a4e0-9fef4403e430)

<div align="center"><i>Assets screen displaying the list of assets and an option to add asset or import assets.</i></div>

### Asset hierarchy

An asset hierarchy is a structure that organizes multiple assets and devices into a hierarchy, allowing for the visualization and management of complex systems.

The asset hierarchy is displayed in the Assets page. An asset hierarchy consists of a root asset and all its subsequent subassets. Click Add asset to create the entire hierarchy of an asset in the New asset page. For details, see [To create an asset](#creating-assets-via-ui).

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/b9076853-0d05-41e5-bb1c-71b917241321)

<div align="center"><i>Asset hierarchy screen displaying the subassets of the root asset.</i></div>

### Creating assets via UI

You have two options for creating assets in the DTM application. The following section describes how to create an asset via the UI. Alternatively, see [Creating assets via bulk import](#bulk-import) on how to import assets in bulk into the DTM application.

You can create assets based on the asset models and properties you have defined previously.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/d9ca99a9-62d7-443b-8c54-ed1a56b56f03)

<div align="center"><i>Asset creation screen displaying the asset hierarchy of the selected asset model.</i></div>

### Bulk import

To import all the assets of a particular asset hierarchy at once, use the bulk import feature. Microservice is being used to download the template and import the assets. To use the Bulk import feature, user must be part of a role that has `Admin` permission level for **Digital twin** type.
[Configure a role for Bulk Import](#configure-a-role-to-use-the-bulk-import-feature)

`Note: Import assets button is disbaled if user doesn't have permission to create a group.`

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/94d1b02e-8a25-4906-a707-439ff8d882a9)

<div align="center"><i>Import Assets screen displaying the modal box where you can upload and download the template.</i></div><br>

You can find more information about how to download the template, import the assets [here](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/blob/main/README.bk.md)

### View assets

Select an asset in the Assets page to view the asset details in Subassets tab. It shows all the subassets, child devices and asset properties.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/813dd29c-ca61-4542-b912-5d354b60b44b)

<div align="center"><i>Sub assets tab displaying the details of the selected asset.</i></div><br>

You can view the hierarchy of the asset in the Asset tree tab. Initially the asset hierarchy is collapsed. Click the expand icon to view the next level of subassets.

Click Add asset to add more subassets or click Import assets to add [child assets in bulk](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/blob/main/README.bk.md).

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/5bb11509-4681-4d97-a3a5-4426089f6641)

<div align="center"><i>Asset tree tab displaying the child asset hierarchy of the selected asset.</i></div><br>

#### Asset search

You can search for assets through the Search button at the right of the top bar. Enter a search term into the textbox at the top of the Search window to see all assets matching the search criteria in the section Search results.

To see more details click Go to the asset data table at the bottom. This will show the entire search results in a table format.

The Search page only shows a limited number of matches. In case of more matches, switch to the asset data table to see the complete results.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/6c05fc0e-b79f-4712-a14c-1c611ef9c653)

<div align="center"><i>Asset search screen displaying the results based on the text entered.</i></div><br>

### Asset properties

The Asset properties can be used to create your own properties to define how data should be stored on an asset. These asset properties can be either complex (nested object) or simple (key-value pair). Furthermore, you can choose a specific data type for each property you define. As of now, the Asset properties supports following data types: Text, Number,File Upload Date Picker, Enumeration, Boolean.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/9ccb90fe-4514-4af0-93cb-cf331599c739)

<div align="center"><i>Asset properties screen displaying the list of properties and an option to add or edit the property.</i></div>

### Asset models

Asset models serve as a blueprint for your assets and define how they are structured. An Asset model defines what asset properties an asset should have. Additionally, you can specify relationships between multiple Asset models, which will be respected when you create your actual asset hierarchies. Once the Asset model is created, it can be used to create various assets.

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/5711f9d5-ce3d-4fa9-acf5-99e0fd38595f)

<div align="center"><i>Edit Asset model screen displaying the details of the selected asset model.</i></div>

### Localization

You can use the Localization component to define translations for your asset models and asset properties. These translations can be provided for all supported languages in Cumulocity IoT. This component requires to have the `feature-branding` feature subscribed for your Cumulocity tenant.

[Subscribing for Feature-branding](#subscribing-for-feature-branding)

![image](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/assets/107403521/a1769673-119b-4fcb-a71f-110cd53de945)

<div align="center"><i>Localization screen displaying the list of translated terms for your asset models and asset properties.</i></div>

## Any comments, suggestions or ideas?

Let us know, if the current way for setting up and maintaining an asset hierarchy meets your needs and expectations. For any suggestions, please navigate to [Issues](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/issues) and open a new issue with all the relevant details. Once you have created your issue, we will make sure to assign the correct label to it, which will help us to categorize your issue:

* 🐞 use "bug" for something that is not working
* 📖 use "documentation" for any feedback about the documentation
* 💡 use "idea" for every new idea, feature request or suggestion
* ❓ use "support" for questions or anything that needs further assistance

**Thanks for your contribution!**

_________________

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
