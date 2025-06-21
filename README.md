---
description: >-
  Whether you’re a business analyst, finance manager, or IT administrator, this
  tool simplifies complex data workflows and brings the power of Odoo and Excel
  together—no manual downloads, no data silos.
---

# Excel Online Connector

The **Odoo Excel Online Connector** empowers you to seamlessly integrate your Odoo ERP data with Microsoft Excel Online, enabling real-time reporting, advanced analytics, and streamlined collaboration. Built for security and efficiency, this connector leverages Azure Active Directory authentication and Microsoft Graph API to ensure safe, automated, and customizable data exports from Odoo to your Excel workbooks in OneDrive.

### Get Started <a href="#get-started" id="get-started"></a>

* **Introduction:** Understand what the connector is and how it benefits your business.
* **Key Features:** Explore the main capabilities and advantages of the connector.
* **Setup & Installation:** Step-by-step instructions to install the module in Odoo.
* **Initial Setup:** Guidance on configuring Azure credentials and verifying your connection.

***

### Why Use the Excel Online Connector? <a href="#why-use-the-excel-online-connector" id="why-use-the-excel-online-connector"></a>

* **Real-Time Data Sync:** Always have the latest Odoo data in Excel for decision-making.
* **Secure Integration:** Enterprise-grade security with Azure AD1.
* **Customizable Exports:** Export exactly the data you need, when you need it.
* **No More Manual Work:** Automate your reporting and analytics workflows.

***

### Quick Navigation <a href="#quick-navigation" id="quick-navigation"></a>

* [Introduction](https://niyulabs.gitbook.io/doc/excel-online-connector/introduction)
* [Key Features](https://niyulabs.gitbook.io/doc/excel-online-connector/key-features)
* [Setup ](https://niyulabs.gitbook.io/doc/excel-online-connector/setup)
* [Installation & Initial Setup](https://niyulabs.gitbook.io/doc/excel-online-connector/installation-and-initial-setup)

***

### Visual Overview <a href="#visual-overview" id="visual-overview"></a>

```
text +----------------+           Secure API Calls         +---------------------+
     |                |  ------------------------------->  |                     |
     |    Odoo ERP    |                                    |    Microsoft Graph  |
     |  (Your Data)   |  <-------------------------------  |    API & OneDrive   |
     |                |           Authentication & Data    |                     |
     +----------------+                                    +---------------------+
          |                                                       |
          |                                                       |
          |                                                       |
          v                                                       v
     +---------------------------------------------------------------+
     |                                                               |
     |                  Excel Online Workbook                        |
     |                (Stored in OneDrive)                           |
     |                                                               |
     +--------------------------------------------------------------
```

### How It Works:

* **Real-Time Data Access:** No manual exports or imports; data flows automatically.
* **Enterprise Security:** Uses Microsoft’s secure authentication protocols.
* **Customizable:** Export only the data you need to the exact sheet and file you want.
* **Collaboration-Ready:** Excel files can be shared and edited by multiple users simultaneously.

### Benefits of This Integration:

***

1. **Data Selection in Odoo:**\
   Users select the Odoo models and fields they want to export via the connector’s export tasks.
2. **Secure Authentication:**\
   The connector uses Azure AD credentials (Tenant ID, Client ID, Client Secret, User UPN) to authenticate with Microsoft Graph API securely.
3. **Token and Drive Management:**\
   Access tokens and OneDrive Drive IDs are automatically managed by the connector to maintain uninterrupted access.
4. **Data Export:**\
   Data is pushed from Odoo directly into the specified Excel workbook and sheet on OneDrive.
5. **Excel Online Access:**\
   Users can open the Excel file online or via desktop Excel, with the latest Odoo data available for analysis, reporting, and collaboration.\


***

**Ready to get started?**\
Jump to the [Setup & Installation](https://www.perplexity.ai/search/rpc-error-odoo-server-error-oc-WgAnDunBQpKhtPBPMVV0gg) section or explore the [Key Features](https://www.perplexity.ai/search/rpc-error-odoo-server-error-oc-WgAnDunBQpKhtPBPMVV0gg) to see what this connector can do for you.
