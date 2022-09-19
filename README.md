# Cumulocity Digital Twin Manager

## Overview

The `Digital Twin Manager` enables you to create and manage assets around your physical connected devices in Cumulocity IoT. Assets can be used to structure and describe devices in logical hierarchies as encountered in the real world environment. In addition, assets in Cumulocity IoT can be extended and enriched with addtional information using the `Properties Library`.

![digital_twin_manager](https://user-images.githubusercontent.com/57527184/173009445-1bff54b7-3a80-4d3e-8ace-84ca9371debc.png)

## Components

### Overview

The `Digital Twin Manager` consists of several components, which support you to create your assets and asset hierarchies:

* `Property library` - Create your own custom properties (simple or complex) to define how data should be stored on an asset
* `Asset types` - Define asset types to describe the blueprint of your assets
* `Localization` - Dynamically translate asset type and custom property descriptions to multiple languages
* `Assets navigator` - Manage your asset hierarchies
* `Bulk import` - To import the entire asset hierarchy with all the assets at once.

### Property Library

The Property Library can be used to create your own custom properties to define how data should be stored on an asset. These custom properties can be either complex (nested object) or simple (key-value pair). Furthermore, you can choose a specific data type for each property you define. As of now, the Property Library supports following data types: Text, Number, Date Picker, Enumeration, Boolean.

![property_library](https://user-images.githubusercontent.com/57527184/173009481-76937af9-11b5-430f-8f59-24a9cdf60e11.png)

### Asset Types

Asset Types serve as a blueprint for your assets and define how they are structured. An Asset Type defines what custom properties an asset should have. Additionally, you can specify relationships between multiple Asset Types, which will be respected when you create your actual asset hierarchies. Once the Asset Type is created, it can be used to create various assets.

![asset_type_creation](https://user-images.githubusercontent.com/57527184/173009509-9f945459-08c0-4421-8caa-09c428b25a68.png)

### Localization

You can use the Localization component to define translations for your asset types and custom properties. These translations can be provided for all supported languages in Cumulocity IoT. This component requires to have the `feature-branding` feature subscribed for your Cumulocity tenant.

![localization](https://user-images.githubusercontent.com/57527184/173009548-0552a022-491d-461d-9530-f4bef9d01d23.png)

### Assets Navigator

The Assets Navigator is the starting point to create your asset hierarchies based on the asset types and custom properties, you have defined previously. Once you have created your asset hierarchies you can use the Assets Navigator to view and manage them. 

![asset_creation](https://user-images.githubusercontent.com/57527184/173009586-50212b91-64b8-46ec-b376-3228ce5e1f0e.png)

### Bulk import
To import all the assets of a particular asset hierarchy at once, use the bulk import feature. For each asset hierarchy, a CSV template is provided. Fill in the required details in this template and upload the file to create the assets in a bulk for the selected asset type.


## Installation

The `Digital Twin Manager` is shipped as a standalone application for now. This means it will be installed as a separate application, which provides all the features of the `Digital Twin Manager` as described in the component section. The standalone application is available in the [release section](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/releases) and can be downloaded.

For installation:

1. Open the `Administration` application in your Cumulocity tenant
2. Navigate to `Applications` --> `Own applications`
3. Click on `Add application`
4. Select `Upload web application` in the modal dialog
5. Select the zip archive, which you downloaded from the release section, to upload it to the tenant

After following these instructions, the application will be deployed on the tenant and is ready for use. In the application switcher on the top right you can now select the `Digital Twin Manager` application.

## Any comments, suggestions or ideas?

Let us know, if the current way for setting up and maintaining an asset hierarchy meets your needs and expectations. For any suggestions, please navigate to [Issues](https://github.com/SoftwareAG/cumulocity-digital-twin-manager/issues) and open a new issue with all the relevant details. Once you have created your issue, we will make sure to assign the correct label to it, which will help us to categorize your issue: 

* 🐞 use "bug" for something that is not working
* 📖 use "documentation" for any feedback about the documentation
* 💡 use "idea" for every new idea, feature request or suggestion
* ❓ use "support" for questions or anything that needs further assistance

**Thanks for your contribution!**

_________________

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
