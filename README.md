
# PEW-Retail_Dashboard

### Dashboard Link : https://app.powerbi.com/reportEmbed?reportId=7455157d-5e62-4ba6-b037-c3806cd0001e&autoAuth=true&ctid=7a95ad65-55ee-41e3-ba46-acbdf605ee3d

## Problem Statement

PEW Retail Inc. Ltd. has subsidiaries across the globe, and they are selling products to various customers scattered across different geographies. They are looking to have a consolidated dashboard with the following requirements:

1. How much Tax do they pay based on the various region they do business in?
2. Number of orders received by various product categories.
3. Who are their top five customers in consuming their products?
4. Order received by various regions to various product categories and products.
5. All this data is restricted as per the region. For example, a business user who owns an Australian subsidiary is restricted only to see the Australian data.
6. Any changes or additions to the sales data should automatically get reflected to the Dashboard without any manual intervention.
7. Export the reports to a Power BI Presentation.



### Task / Steps followed

Step 1: Load/Import the data from all the below CSV files using the Power BI desktop.

▪ FactInternetSales.csv

▪ DimProduct.csv

▪ DimProductCategory.csv

▪ DimProductSubCategory.csv

▪ DimGeography.csv

▪ DimCustomer.csv


Step 2: After loading the data, make sure you create the relationship between
DimProduct and DimProductSubCategory as shown below:


<img width="655" height="532" alt="Image" src="https://github.com/user-attachments/assets/1edd0af9-859b-4e72-852c-772710fcc135" />

Step 3: Tax amount they are paying based on the various region they do business:

▪ Drag and drop TaxAmt from FactInternetSales and
EnglishCountryRegionName from DimGeography as shown below: 

<img width="890" height="399" alt="Image" src="https://github.com/user-attachments/assets/479a2fe0-5a41-4733-8037-6929574f4c83" />


Step 4: Number of orders received by various product categories.

▪ Drag and drop EnglishProductCategoryName from DimProductCategory
and OrderQuantity from FactInternetSales.

▪ You can change the colors formatting as per your choice as shown below:

<img width="915" height="416" alt="Image" src="https://github.com/user-attachments/assets/349c122c-9094-43b8-a02d-ec35456a7a4c" />


Step 5: Their top 5 customers

Create Measure Total Orders under DimCustomer using below DAX:

Total Orders = SUM(FactInternetSales[OrderQuantity])

Under FactInternetSales, create a Measure top 5 customers using below DAX:

Top5 Customers = CALCULATE([Total Orders],
 FILTER(VALUES(DimCustomer[FirstName]),
 IF(RANKX(ALL(DimCustomer[FirstName]),[Total
Orders],,DESC)<=5,[Total Orders],BLANK())))


<img width="738" height="384" alt="Image" src="https://github.com/user-attachments/assets/6e3044e5-f8a5-4a64-9515-4d027fd16631" />


Step 6: Orders received by various regions by to various product categories and products:

▪ Drag fields EnglishCountryRegionName, EnglishProductCategoryName and EnglishProductName on Axis. Drag OrderQuantity in Value as shown below. 

<img width="1089" height="509" alt="Image" src="https://github.com/user-attachments/assets/c142d867-3b23-44f0-b7b6-e6db89212a74" />

Step 7: All this data is restricted as per the region.

▪ Under Modeling, click on Manage Roles and Create New as RegionRoles with the below DAX:

[EnglishCountryRegionName] = "United States" 

<img width="1097" height="498" alt="Image" src="https://github.com/user-attachments/assets/5c8e1546-b9e9-4e7e-9362-7817d67072f2" />

▪ You can even view as Roles using View as Role to test the role.

<img width="1083" height="517" alt="Image" src="https://github.com/user-attachments/assets/2da7aec3-b29d-4124-8ae0-d1e709185fb5" />

Step 8: Any changes or addition to the sales data should automatically get reflected to the Dashboard without any manual intervention.

▪ For this, install and configure the Power BI Data Gateway (personal mode) from here https://powerbi.microsoft.com/en-us/gateway/

<img width="1149" height="355" alt="Image" src="https://github.com/user-attachments/assets/47930827-db97-4388-a376-e14e9c20334d" />

Step 9: Publish the report on the Power BI service by clicking on Publish option.

<img width="1093" height="136" alt="Image" src="https://github.com/user-attachments/assets/41e1cd99-f98d-408d-abe7-586cb0422e9d" />

Step 10: After publishing the report, we users can export the Reports to a Power BI Presentation.

▪ In Power BI Service, select the Report, then File, Export to PowerPoint, and select Embed an image.

<img width="1079" height="476" alt="Image" src="https://github.com/user-attachments/assets/dc1e50e0-1691-43a6-aa28-2775954f4e60" />


▪ After successful export, we can open the PowerPoint file with embedded report.

<img width="1149" height="481" alt="Image" src="https://github.com/user-attachments/assets/70c02fe8-135f-41b3-a577-1718ced20967" />



### Output

The final report should contain the following two pages:

(Most of the time, you would have sample designs, mock-ups, and wireframes of the visuals/reports)

1. Home Page

<img width="1073" height="614" alt="Image" src="https://github.com/user-attachments/assets/a8ec10f3-9f1e-43ac-93d5-4850994ea42f" />

2. Summery

<img width="1078" height="618" alt="Image" src="https://github.com/user-attachments/assets/bf635660-bd03-40f9-b59d-b1bf0e4cdc4b" />




        
