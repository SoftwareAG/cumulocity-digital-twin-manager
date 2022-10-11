# Cumulocity Digital Twin Manager

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
	- [Installation of Web application](#for-installation-of-web-application)
	- [Installation of Microservice](#for-installation-of-microservice)
	- [Configure a role for Bulk Import](#configure-a-role-to-use-the-bulk-import-feature)
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

This is the sub assets page which includes [Asset Navigator](#assets-navigator), name of the parent asset and its properties, list of child assets.

`Note: Digital Twin Manager supports Cumulocity UI and microservice version of 10.15 and above`

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

After following these instructions, the application will be deployed on the tenant and is ready for use. In the application switcher on the top right you can now select the
`Digital Twin Manager` application.

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

`Note: If the permissions are not assigned, then the CSV template will not be downloaded correctly.`

![GIF for DTM Installation](https://user-images.githubusercontent.com/107403521/194924558-bbe7800b-077d-4422-bc3a-535d6671c0b0.gif)

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

This is the **Property Library** screen which includes the list of properties and an option to add or edit the property.

### Asset Types

Asset Types serve as a blueprint for your assets and define how they are structured. An Asset Type defines what custom properties an asset should have. Additionally, you can specify relationships between multiple Asset Types, which will be respected when you create your actual asset hierarchies. Once the Asset Type is created, it can be used to create various assets.

![asset_type_creation](https://user-images.githubusercontent.com/57527184/173009509-9f945459-08c0-4421-8caa-09c428b25a68.png)

This is **Edit Asset Type** screen which includes the label, key, description, child assets and custom properties of the selected asset type.

### Localization

You can use the Localization component to define translations for your asset types and custom properties. These translations can be provided for all supported languages in Cumulocity IoT. This component requires to have the `feature-branding` feature subscribed for your Cumulocity tenant.

![localization](https://user-images.githubusercontent.com/57527184/173009548-0552a022-491d-461d-9530-f4bef9d01d23.png)

This is **Localization** screen which includes the list of translated terms for your asset types and custom properties.

### Assets Navigator

The Assets Navigator is the starting point to create your asset hierarchies based on the asset types and custom properties, you have defined previously. Once you have created your asset hierarchies you can use the Assets Navigator to view and manage them.

![asset_creation](https://user-images.githubusercontent.com/57527184/173009586-50212b91-64b8-46ec-b376-3228ce5e1f0e.png)

This is **Asset Navigator** screen which includes the asset hierarchy of the selected asset type.

### Bulk import
To import all the assets of a particular asset hierarchy at once, use the bulk import feature. Microservice is being used to download the template and import the assets. To use the Bulk import feature, user must be part of a role that has `Admin` permission level for **Digital twin** type.
[Configure a role for Bulk Import](#configure-a-role-to-use-the-bulk-import-feature)

![Bulk Import](https://user-images.githubusercontent.com/107403521/191242984-ff5174ca-1a02-454e-9cd6-7aa7444635b0.PNG)

This is **Bulk Import** screen where you can upload and download the template.

#### Download template

1. On click of Import assets button in the assets page, a dialog box appears with an option to **Choose asset type**.
	* If no asset types are created yet, only the asset type "Group" is listed in the dropdown.
	* If you have added the asset types, all the root asset types are listed in the dropdown.
2. Select the asset type for which you want to create the asset hierarchy.
3. On selection, two additional options appear.
	* **Drop file here** - upload the CSV template as a file, for importing assets in bulk.
	* **Download Template** - download the CSV template for the selected asset type.
4. Click **Download Template** to download the CSV template.

The CSV template has the following fields:

<table>
<col width="20">
<col width="50">
<col width="30">
<thead>
<tr>
<th style="text-align:left">Field</th>
<th style="text-align:left">Description</th>
<th style="text-align:left">Mandatory / Optional</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left"><b>AssetType / DeviceType </b></td>
<td style="text-align:left">Enter the key of the asset type.</td>
<td style="text-align:left">Mandatory</td>
</tr>
<tr>
<td style="text-align:left"><b>AssetName</b></td>
<td style="text-align:left">Provide the name of the asset you want to create.</td>
<td style="text-align:left">Mandatory</td>
</tr>
<tr>
<td style="text-align:left"><b>Path</b></td>
<td style="text-align:left">Remains blank when you create a root asset. For a child asset, provide a path up to the root asset.<br><br>
<b>Example:</b><br>
For an asset called "Room1" in the hierarchy "Building > Floor > Room" the path value is "Building 1/Floor 1", where "Building 1" and "Floor 1" represent the respective asset types.</td>
<td style="text-align:left">Mandatory (for child assets)</td>
</tr>
<tr>
<td style="text-align:left"><b>Device ID / External ID</b></td>
<td style="text-align:left">If the asset being created has a device associated with it, then provide the Device ID of the device here</td>
<td style="text-align:left">Optional</td>
</tr>
<tr>
<td style="text-align:left"><b>Description</b></td>
<td style="text-align:left">briefly describes the asset being created.</td>
<td style="text-align:left">Optional</td>
</tr>
<tr>
<td style="text-align:left"><b>Custom properties for the asset type</b></td>
<td style="text-align:left">6th column onwards (in the CSV template), all the custom properties for the root asset types and all its subsequent child asset types are listed.<br><br>
<b>Info:</b><br>The <a href="/dtm/asset-types/#custom-property-types" class="no-ajaxy">Custom property type</a> is also mentioned as a label, for better understanding.
</td>
<td style="text-align:left">Mandatory</td>
</tr>
</tbody>
</table>

`Note: Modify the excel settings to provide the date in a YYYY-MM-DD format. This prevents an auto-correct of the date on input.`

To provide a file input as a custom property value, the file must first be uploaded to a Cumulocity IoT tenant using the API.

Refer to the Binaries API https://cumulocity.com/api/10.13.0/#operation/postBinariesCollectionResource in the openapi for details on how to upload a file.

The binary ID in the API response must be provided as input for the custom property field with type "file" in the CSV template.

If the type is "Boolean", the input field must be either "true" or "false".
If the type is "enumeration", then the input field must be in the list of values specified during creation of the custom property.
If the type is "text" or "number" and custom criteria were provided during custom property creation, then the input value in CSV template must fulfill all the custom property criteria.

#### Upload template

`Note: Before uploading the CSV template make sure that the asset types which are being used in the template should be newly created.`

1. Upload the previously filled and saved CSV template in the **Drop file here** section.

2. If all the inputs are provided correctly, the bulk import is successful, resulting in a success notification. The asset hierarchy and its assets are created successfully.

3. View the newly created assets in the **Assets** page.

If the inputs are not provided in the correct format, the bulk import fails with validation errors, resulting in a **Failed asset imports** notification, showing the issue types. For example, an invalid template or an incorrect asset hierarchy will not create the assets.

If the bulk import fails, review the reported issues and try again.

#### Partial import

If the asset hierarchy already exists, and you want to import more assets, it can be achieved by a partial import.

To import the child asset hierarchy or the child assets:

1. Fill in the details for the child asset hierarchy in the CSV template.

	`Note: From any hierarchy level, the template will be downloaded only for its child hierarchy. Assets must only be imported for the child hierarchy.`

2. Enter the details for the child assets in the CSV template.

3. Upload the CSV template in the **Drop file here** section in the **Import assets** dialog.

If all details are mentioned correctly in the CSV template, the child asset hierarchy is created successfully.

An unsuccessful partial import will result in a **Failed asset imports** notification, showing the validation issues.
Review the reported issues and try again.

## Any comments, suggestions or ideas?

Let us know, if the current way for setting up and maintaining an asset hierarchy meets your needs and expectations. For any suggestions, please navigate to [Issues](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/issues) and open a new issue with all the relevant details. Once you have created your issue, we will make sure to assign the correct label to it, which will help us to categorize your issue:

* 🐞 use "bug" for something that is not working
* 📖 use "documentation" for any feedback about the documentation
* 💡 use "idea" for every new idea, feature request or suggestion
* ❓ use "support" for questions or anything that needs further assistance

**Thanks for your contribution!**

_________________

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
