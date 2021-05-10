# Aras CM2 Community Project

The Aras CM2 Community Project package adds to and modifies the base PLM application to provide 4 Star Certified CM2 capabilities:

* ECR and ECN relabeled to CR and CN, with updated forms and several new relationships per the CM2 standard
* New Identities for Change Leader, Change Implementation Leader, and Audit Release Analyst used revised permissions for the change items and change controlled items
* The CR can be used as a combined CR/CN for fast-track changes if desired
* New CM2 CR and CM2 CN workflow maps per the CM2 standard
* The Affected Item relationships are labelled Impact Matrix can be used to specify the Planned Release and Effective dates for change affected items
* The CR and CN can link to a detailed implementation plan (Aras Project)
* New CM2 IR "Investigation Request" itemtype and workflow 
* Parts are relabeled as Physical Items and Documents are relabeled as Datasets
* Document to Document and Document to Child Document relationships are available to specify reference documents and sub-documents respectively
* A new Document Part relationship allows Parts classified as Tools to be specified on a document (generally used for Process Plan documents/datasets) 
* Baseline reports for Physical Items (Parts) of D&P, ILS, Facility, IS, and Enterprise classifications providing the As-Planned/As-Released Baseline for a given date
* Support for Physical Item Model classifications, supporting serial number assignment
* Planning Bill report for a specified effective date, showing the BOM for that date plus changes for a given Physical Item
* CM2 Order Bill itemtype to define the BOM for a specified part and effective date on an order, generated through a “Derive Order Bill” action to derive the order bill from the effective planning bill for that part
* Work Authorization with action to derive Work Authorization BOM
* Combined CR/CN capability on CR form and workflow map
* [ECR Impact Matrix](https://github.com/ArasLabs/ecr-impact-matrix) - a simplified version of the Express ECO Impact Matrix
* ECR to ECN conversion action

## History

Release | Notes
--------|--------
[v2.0.0](https://github.com/ArasLabs/CM2/releases/tag/v2.0.0) | Updated to support 12.0
[v1.2.0](https://github.com/ArasLabs/CM2/releases/tag/v1.2.0) | Adds a simplified version of the Express ECO Impact Matrix onto the ECR, and adds an item action to convert an ECR to an ECN.
[v1.1.0](https://github.com/ArasLabs/CM2/releases/tag/v1.1.0) | This release adds a Work Authorization, with an action to derive Work Authorization BOM. It also combines CR/CN capability on the CR form and workflow map.
[v1.0.1](https://github.com/ArasLabs/CM2/releases/tag/v1.0.1) | Typo fix in readme.
[v1.0.0](https://github.com/ArasLabs/CM2/releases/tag/v1.0.0) | First release.

#### Supported Aras Versions

Project | Aras
--------|------
[v2.0.0](https://github.com/ArasLabs/CM2/releases/tag/v2.0.0) | 12.0 SPX
[v1.2.0](https://github.com/ArasLabs/CM2/releases/tag/v1.2.0) | 11.0 SP12+
[v1.1.0](https://github.com/ArasLabs/CM2/releases/tag/v1.1.0) | 11.0 SP12+
[v1.0.1](https://github.com/ArasLabs/CM2/releases/tag/v1.0.1) | 11.0 SP12+
[v1.0.0](https://github.com/ArasLabs/CM2/releases/tag/v1.0.0) | 11.0 SP12+

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed
2. PE 12.0 R1 installed
3. Aras Package Import Utility
4. CM2 Community Project package
5. Code Tree overlay

### Install Steps

#### The Code Tree
1. Backup your code tree and store the backup in a safe place.
2. Copy the `Innovator` folder from `\CodeTree` in your local repository.
3. Paste this folder to the root install directory of your code tree.
	* This should be the same folder that contains the `InnovatorServerConfig.xml`.

#### The Database
1. Back up your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
    * _Note: You must log in as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
    * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\cm2\Import\1-Pre\imports.mf` file in the Manifest File field.
6. Select the following in the Available for Import field.
    * **com.aras.innovator.solution.PLM**
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Enter the path to your local `..\cm2\Import\2-Post\imports.mf` file in the Manifest File field.
10. Select the following in the Available for Import field.
    * **com.aras.innovator.solution.PLM**
11. Click **Import** in the top left corner.
12. Close the Aras Package Import tool.

You are now ready to login to Aras and use the new CM2 capabilities.

<!-- ## Usage  -->

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request.

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Created by Mike Gavlak and Eli Donahue for Aras Corporation.

## License

Aras Community projects are published to GitHub under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.