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
	- [Property library](#property-library)
	- [Asset types](#asset-types)
	- [localization](#localization)
	- [Asset Navigation](#assets-navigator)
	- [Bulk import](#bulk-import)
	  - [Download Template](#download-template)
	  - [Upload Template](#upload-template)
	  - [Partial Import](#partial-import)
## Overview

The `Digital Twin Manager` enables you to create and manage assets around your physical connected devices in Cumulocity IoT. Assets can be used to structure and describe devices in logical hierarchies as encountered in the real world environment. In addition, assets in Cumulocity IoT can be extended and enriched with addtional information using the `Properties Library`.

![digital_twin_manager](https://user-images.githubusercontent.com/57527184/173009445-1bff54b7-3a80-4d3e-8ace-84ca9371debc.png)

<div align="center"><i>Sub assets screen displaying the details of an asset selected in Asset Navigator on the left.</i></div><br>

`Note: Digital Twin Manager is supported on Cumulocity UI and microservice version of 10.14 and above`

## Installation

The `Digital Twin Manager` is shipped as a standalone application for now. This means it will be installed as a separate application, which provides all the features of the
`Digital Twin Manager` as described in the features section. The standalone application is available in the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
and can be downloaded.

### For installation of web application:

1. Download dtm-ui-10xx.x.x.zip from the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
2. Open the `Administration` application in your Cumulocity tenant
3. Navigate to `Ecosystem` --> `Applications`
4. Click on `Add application`
5. Select `Upload web application` in the modal dialog
6. Select the zip archive, which you downloaded from the release section, to upload it to the tenant

![GIF for DTM Installation](https://user-images.githubusercontent.com/107403521/194924558-bbe7800b-077d-4422-bc3a-535d6671c0b0.gif)

After following these instructions, the application will be deployed on the tenant and is ready for use. In the application switcher on the top right you can now select the `Digital Twin Manager` application.

If you want to use `Import assets` functionality, then the microservice needs to be installed.

### For installation of microservice:

1. Download dtm-ms-10xx.x.x.zip from the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases)
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

To use Localization feature, you need to subscribe for `Feature Branding`. The following are the steps:-

If you are an administrator for `Management tenant`, then

1) Navigate to tenants -> subtenants
2) Select the subtenant for which you want to use this feature.
3) Under applications, subscribe for Feature branding.

If you are an administrator of the tenant in which localization needs to be enabled, then

1) Navigate to Administration -> Ecosystem -> Applications. Under features, make sure you have subscribed for Feature Branding.
2) Navigate to Settings -> Branding, and click on Apply. Once it is applied make sure you can see `public options` under Ecosystem -> Applications.

`Note: If you don't have the access for the tenants, please contact your administrator.`

## Features

### Overview of features

The `Digital Twin Manager` consists of the following features, which support you to create your assets and asset hierarchies:

* `Property library` - Create your own custom properties (simple or complex) to define how data should be stored on an asset
* `Asset types` - Define asset types to describe the blueprint of your assets
* `Localization` - Dynamically translate asset type and custom property descriptions to multiple languages
* `Assets navigator` - Manage your asset hierarchies
* `Bulk import` - To import the entire asset hierarchy with all the assets at once.

### Property Library

The Property Library can be used to create your own custom properties to define how data should be stored on an asset. These custom properties can be either complex (nested object) or simple (key-value pair). Furthermore, you can choose a specific data type for each property you define. As of now, the Property Library supports following data types: Text, Number, Date Picker, Enumeration, Boolean.

![property_library](https://user-images.githubusercontent.com/57527184/173009481-76937af9-11b5-430f-8f59-24a9cdf60e11.png)

<div align="center"><i>Property Library screen displaying the list of properties and an option to add or edit the property.</i></div>

### Asset Types

Asset Types serve as a blueprint for your assets and define how they are structured. An Asset Type defines what custom properties an asset should have. Additionally, you can specify relationships between multiple Asset Types, which will be respected when you create your actual asset hierarchies. Once the Asset Type is created, it can be used to create various assets.

![asset_type_creation](https://user-images.githubusercontent.com/57527184/173009509-9f945459-08c0-4421-8caa-09c428b25a68.png)

<div align="center"><i>Edit Asset Type screen displaying the details of the selected asset type.</i></div>

### Localization

You can use the Localization component to define translations for your asset types and custom properties. These translations can be provided for all supported languages in Cumulocity IoT. This component requires to have the `feature-branding` feature subscribed for your Cumulocity tenant.

![localization](https://user-images.githubusercontent.com/57527184/173009548-0552a022-491d-461d-9530-f4bef9d01d23.png)

<div align="center"><i>Localization screen displaying the list of translated terms for your asset types and custom properties.</i></div>

### Assets Navigator

The Assets Navigator is the starting point to create your asset hierarchies based on the asset types and custom properties, you have defined previously. Once you have created your asset hierarchies you can use the Assets Navigator to view and manage them.

![asset_creation](https://user-images.githubusercontent.com/57527184/173009586-50212b91-64b8-46ec-b376-3228ce5e1f0e.png)

<div align="center"><i>Asset Navigator screen displaying the asset hierarchy of the selected asset type.</i></div>

### Bulk import
To import all the assets of a particular asset hierarchy at once, use the bulk import feature. Microservice is being used to download the template and import the assets. To use the Bulk import feature, user must be part of a role that has `Admin` permission level for **Digital twin** type.
[Configure a role for Bulk Import](#configure-a-role-to-use-the-bulk-import-feature)

![Bulk Import](https://user-images.githubusercontent.com/107403521/191242984-ff5174ca-1a02-454e-9cd6-7aa7444635b0.PNG)

<div align="center"><i>Import Assets screen displaying the modal box where you can upload and download the template.</i></div><br>

You can find more information about how to download the template, import the assets [here](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/blob/main/README.bk.md)

## Any comments, suggestions or ideas?

Let us know, if the current way for setting up and maintaining an asset hierarchy meets your needs and expectations. For any suggestions, please navigate to [Issues](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/issues) and open a new issue with all the relevant details. Once you have created your issue, we will make sure to assign the correct label to it, which will help us to categorize your issue:

* 🐞 use "bug" for something that is not working
* 📖 use "documentation" for any feedback about the documentation
* 💡 use "idea" for every new idea, feature request or suggestion
* ❓ use "support" for questions or anything that needs further assistance

**Thanks for your contribution!**

_________________

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
