# Sales-Data-Ingestion-and-Cleaning-Pipeline
Project Description:
The Automated Daily Sales Data Processing and Logging System is designed to automate the daily ingestion, transformation, and logging of sales data from mock online JSON files into Azure Blob Storage. This project leverages Azure Data Factory (ADF) and associated services to ensure efficient data handling and proactive monitoring through automated alerts and logging mechanisms.

Key Activities and Components:
API Integration for Mock Online JSON Data:

Developed a custom API to fetch mock online JSON files from a mockaroo API endpoint securely.
Data Transformation with Azure Data Factory Data Flow:

Web Activity: Used a web activity in ADF to retrieve JSON data from the mockaroo API.
Flattening and Selection: Flattened complex fields like phone numbers and areas and selected required fields using the Select transformation.
Dynamic Parameterization: Employed dynamic parameters to store files in Blob storage with yesterday's date, ensuring organized data storage.
Metadata and Error Handling:

Metadata Activity: Implemented a metadata activity to verify successful data storage in the sales container.
Error Handling: If data is not loaded successfully, an email alert is triggered at 8 am to notify the relevant team, and a pipeline log file is generated for further analysis.
Data Quality and Filtering:

Error Detection: Checked and logged records with null values for critical fields such as customer_id and product_id.
Duplicate Removal: Removed duplicate rows using aggregate activities to maintain data integrity.
Transaction Filtering: Filtered out transactions labeled as "cancelled" using a Filter activity to focus on valid sales data.
Logging and Monitoring:

Logging Pipeline: Executed a log pipeline at 8 am to capture detailed logging information, stored in a designated log folder for audit and troubleshooting purposes.
Tools and Technologies Used:
Azure Data Factory: Orchestrated data workflows, integrating API calls, data transformation, and error handling.
Azure Blob Storage: Stored and organized JSON-to-CSV converted data with dynamic date-based naming.
Azure Logic Apps: Managed email alerts for error notifications to ensure prompt action by the operations team.
Mockaroo API: Provided mock online JSON data for testing and development purposes.
Outcomes and Benefits:
Automation and Efficiency: Scheduled daily data processing tasks at 8 am, reducing manual intervention and ensuring data consistency.
Data Quality Assurance: Implemented checks and filters to maintain high data quality and reliability.
Proactive Monitoring: Established email alerts and logging mechanisms for proactive issue detection and resolution.
This project exemplifies a robust approach to handling and processing daily sales data, leveraging cloud-based technologies to optimize operations and enhance data-driven decision-making capabilities.
