***Project Content***

1) **Sales Folder**
   This folder contains sales data in various files for the years 2014, 2015, 2016, and 2017, organized by different locations. Specifically, this folder holds factual data.

2) **Dimensions**
   This folder includes dimensional data for the project, such as Categories, Geography, Product, Sales Representatives, and Subcategories.

3) **Business/Functional Requirement Document**
    This document outlines the business requirements specified by the client, detailing their expectations for the report.

4) **Power BI Report (.pbix)**
   This is the final Power BI report.


*****Project Descriptions*****

***Data Overview:***

1) Review the Business/Functional Requirement Document (BRD/FRD).
2) Examine the data to determine the appropriate approach.
3) There is one fact Table (Sales) and five Dimension Tables.

***Load Data:***

1) Load the data files from the Dimensions folder, available in Excel and CSV formats.
2) While loading data from the Sales folder, note that it contains separate yearly files, indicating volatile data. Therefore, instead of loading individual files, we load the entire folder through the folder location (Get Data → More → Folder → Update Folder Location → Combine & Load). This approach automates the process of updating data whenever a new file is added, avoiding the need for manual merging/appending of individual files.

***Transformation:***

**Categories:** Promoted headers.

**Geography:** Promoted headers and added an index as GeoKey, as requested by the client in the BRD.

**Product:** Promoted headers and removed duplicates, ensuring no duplicates in the dimension table.

**Sales Rep:** Promoted headers and replaced 'ID' in the SalesRepID column by removing the prefix 'ID', aligning it with the Sales table where the ID is without the prefix.

**Subcategory:** Promoted headers and replaced 'ID' in CategoryKey, aligning it with the CategoryKey column in the Categories table.

**Sales:** 
* Performed column profiling.
* Removed unnecessary columns, such as Source.Name.
* Split the Location column into Country and Town.
* Merged Sales with Geography based on 'Country' and 'Town' to derive GeoKey.
* Removed Country and Town columns, as GeoKey now identifies these.

**Updated step descriptions** in 'Applied Steps' section to enhance clarity and understanding.

***Data Modelling:***

1) Following data transformation, some automatic mapping was performed.
2) Created the data model based on the established relationships.
3) Developed a DateMaster (Calendar Table) as requested in the BRD, facilitating time intelligence functions.

***Report Creation:***

For the final report, new columns and measures were created, including:
* Total Revenue
* Total Cost
* Gross Profit
* Tot Rev
* Prev Qtr
* QoQ Growth
* MoM Growth
To enhance the visual appeal of the report, a background template and page button appearances were designed in PowerPoint and integrated into Power BI.
