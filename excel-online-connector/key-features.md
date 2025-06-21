# Key Features

The Odoo Excel Online Connector is built to empower organizations with seamless, secure, and customizable data integration between Odoo ERP and Microsoft Excel Online. Below are its standout features:

### Direct Export of Odoo Data to Excel Online

* Instantly export data from any Odoo model (such as Sales Orders, Invoices, Inventory, Projects, etc.) directly to Excel files stored in OneDrive.
* Supports both initial data dumps and incremental updates, making it ideal for reporting, data analysis, and business intelligence.

### Secure Authentication Using Azure AD Credentials

* Ensures all data transfers are protected with enterprise-grade security.
* Utilizes Azure Active Directory (AD) for authentication, requiring Tenant ID, Client ID, Client Secret, and User UPN.
* Prevents unauthorized access by leveraging Microsoft’s robust identity management.

### Automatic Token and Drive Management

* Handles the complexity of OAuth2 token generation and refresh cycles automatically.
* Fetches and manages OneDrive Drive IDs behind the scenes, so users don’t need to perform technical lookups.
* Minimizes downtime and manual intervention, ensuring uninterrupted data exports.

### Flexible Field Selection and Filtering

* Users can choose exactly which fields (columns) to export from Odoo, allowing for lean, relevant spreadsheets.
* Advanced filtering options let you export only the records that matter (e.g., only confirmed sales, products in stock, or invoices from a specific period).
* Reduces clutter and improves usability of exported data in Excel.

### Scheduled or Manual Exports

* Schedule exports to run automatically at set intervals (e.g., daily, weekly) for always up-to-date Excel reports.
* Run ad-hoc/manual exports anytime with a single click for instant data refresh.
* Ideal for teams that rely on the latest figures for meetings, dashboards, or compliance.

### Comprehensive Logs and Access Control

* Every export and access event is logged, providing a clear audit trail.
* Administrators can review logs to monitor usage, spot anomalies, and ensure data security.
* Access tokens can be revoked or rotated as needed for compliance or incident response.

### Additional Benefits

* **No More Manual Downloads:** Eliminate repetitive, error-prone CSV exports and uploads.
* **Real-Time Collaboration:** Empower teams to work in the same Excel file with live Odoo data.
* **Supports Complex Workflows:** Integrate with Excel’s formulas, charts, and pivot tables for advanced analysis.
* **Scalable:** Suitable for small businesses and large enterprises alike.



## Prerequisites

To ensure a smooth setup and optimal use of the Odoo Excel Online Connector, please confirm the following prerequisites are met:

{% stepper %}
{% step %}
Azure Portal Access

You must have administrative access to your organization’s [Azure Portal](https://portal.azure.com/).

This is necessary to register applications, manage permissions, and generate credentials for secure integration.
{% endstep %}

{% step %}
Excel File in OneDrive

* At least one Excel workbook should exist in the OneDrive account of the user (User UPN) whose credentials will be used.
* This Excel file will serve as the destination for Odoo data exports.
* You can create a new Excel file or use an existing one, but you must have edit permissions on the file.
{% endstep %}

{% step %}
Registered Azure AD Application

* An Azure Active Directory (AD) application must be registered specifically for Odoo integration.
* The app must be granted the required Microsoft Graph API permissions, such as:
  * `Files.ReadWrite`
  * `Sites.ReadWrite.All`
  * (Others may be required depending on your organization’s security policies)
* The app registration process will provide you with the Tenant ID, Client ID, and Client Secret.


{% endstep %}

{% step %}
Microsoft 365 User Account (User UPN)

* The connector requires the email address (User Principal Name) of the Microsoft 365 user whose OneDrive will host the Excel file.
* This user must have an active subscription and sufficient permissions to access and edit files in OneDrive.


{% endstep %}

{% step %}
Internet Access and Odoo Server Configuration

* Your Odoo server must be able to reach Microsoft’s Graph API endpoints over the internet.
* Proxy/firewall settings should allow outbound HTTPS connections to `graph.microsoft.com`.


{% endstep %}

{% step %}
Compliance and Security Review

* Ensure that your organization’s IT and compliance teams approve the integration, especially if sensitive data will be exported.
* Regularly rotate credentials and review access logs for security.


{% endstep %}
{% endstepper %}
