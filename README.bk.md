## Table of Contents
   - [Download template](#download-template)
   - [Upload Template](#upload-template)
   - [Partial Import](#partial-import)

### Download template

1. On click of Import assets button in the assets page, a dialog box appears with an option to **Choose asset model**.
	* If you have added the asset types, all the root asset types are listed in the dropdown.
2. Select the asset model for which you want to create the asset hierarchy.
3. On selection, two additional options appear.
	* **Drop file here** - upload the CSV template as a file, for importing assets in bulk.
	* **Download Template** - download the CSV template for the selected asset model.
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
<td style="text-align:left"><b>AssetModel / DeviceType </b></td>
<td style="text-align:left">Enter the key of the asset model.</td>
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
<td style="text-align:left"><b>Asset properties for the asset type</b></td>
<td style="text-align:left">6th column onwards (in the CSV template), all the asset properties for the root asset models and all its subsequent child asset models are listed.<br><br>
<b>Info:</b><br>The property type is also mentioned as a label, for better understanding.
</td>
<td style="text-align:left">Mandatory</td>
</tr>
</tbody>
</table>

`Note: Modify the excel settings to provide the date in a YYYY-MM-DD format. This prevents an auto-correct of the date on input.`

Asset properties support file, boolean, enumeration, text and number data types. Follow the below instructions while adding them to the CSV template.

<table>
<col width="20">
<col width="80">
<thead>
<tr>
<th>Type</th>
<th>Input value to provide in the CSV template</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left"><b>File</b></td>
<td style="text-align:left">binary ID<br><br>
To provide a file input as a property value, the file must first be uploaded to a Cumulocity IoT tenant using the Binaries API.<br>
The binary ID in the API response must be provided as input for the property field.<br><br>
Refer to the [Binaries API](# https://cumulocity.com/api/10.13.0/#operation/postBinariesCollectionResource) in the openapi for details on how to upload a file.</td>
</tr>
<tr>
<td style="text-align:left"><b>Boolean</b></td>
<td style="text-align:left">true or false</td>
</tr>
<tr>
<td style="text-align:left"><b>Enumeration</b></td>
<td style="text-align:left">One of the values specified while creating the property</td>
</tr>
<tr>
<td style="text-align:left"><b>Text,<br> Number</b></td>
<td style="text-align:left">Any value that fulfils all the custom validation criteria provided while creating the property</td>
</tr>
</tbody>
</table>

### Upload template

`Note: Before uploading the CSV template make sure that the asset mdoels which are being used in the template should be newly created.`

1. Upload the previously filled and saved CSV template in the **Drop file here** section.

2. If all the inputs are provided correctly, the bulk import is successful, resulting in a success notification. The asset hierarchy and its assets are created successfully.

3. View the newly created assets in the **Assets** page.

If the inputs are not provided in the correct format, the bulk import fails with validation errors, resulting in a **Failed asset imports** notification, showing the issue types. For example, an invalid template or an incorrect asset hierarchy will not create the assets.

If the bulk import fails, review the reported issues and try again.

### Partial import

If the asset hierarchy already exists, and you want to import more assets, it can be achieved by a partial import.

To import the child asset hierarchy or the child assets:

1. Fill in the details for the child asset hierarchy in the CSV template.

	`Note: From any hierarchy level, the template will be downloaded only for its child hierarchy. Assets must only be imported for the child hierarchy.`

2. Enter the details for the child assets in the CSV template.

3. Upload the CSV template in the **Drop file here** section in the **Import assets** dialog.

If all details are mentioned correctly in the CSV template, the child asset hierarchy is created successfully.

An unsuccessful partial import will result in a **Failed asset imports** notification, showing the validation issues.
Review the reported issues and try again.
