---
description: >-
  Setting up the Odoo Excel Online Connector requires several pieces of
  information from your Microsoft Azure and OneDrive environment. Below is a
  guide on how to locate each required value
---

# Setup

### **1. Tenant ID**

* **Where to Find:**
  * Log in to the [Azure Portal](https://portal.azure.com/).
  * Navigate to **Azure Active Directory** from the left sidebar.
  * Under **Overview**, you will see the **Tenant ID** (a GUID format, e.g., `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`).
  * Click the copy icon to copy it to your clipboard[1](https://www.odoo.com/documentation/18.0/applications/general/users/azure.html)[6](https://apps.odoo.com/apps/modules/13.0/odoo_microsoft_azure_sso).

<figure><img src="../.gitbook/assets/Screenshot from 2025-06-21 12-47-44.png" alt=""><figcaption></figcaption></figure>

### **2. Client ID (Application ID)**

* **Where to Find:**
  * In the Azure Portal, go to **Azure Active Directory**.
  * Select **App registrations**.
  * Click on the application you registered for Odoo integration.
  * Under the **Overview** section, you’ll find the **Application (client) ID**. Copy this value[2](https://www.odoo.com/documentation/18.0/applications/general/email_communication/azure_oauth.html)[3](https://apps.odoo.com/apps/modules/14.0/microsoft_office_365_integration)[4](https://apps.odoo.com/apps/modules/17.0/sh_office365_connector)[6](https://apps.odoo.com/apps/modules/13.0/odoo_microsoft_azure_sso).

<figure><img src="../.gitbook/assets/Screenshot from 2025-06-21 13-01-12.png" alt=""><figcaption></figcaption></figure>

***

### **3. Client Secret**

* **Where to Find:**
  * In your application’s page in **App registrations**, click on **Certificates & secrets**.
  * Under **Client secrets**, click **New client secret**.
  * Add a description and select an expiry period, then click **Add**.
  * Copy the **Value** immediately after creation (you won’t be able to see it again). This is your **Client Secret**[2](https://www.odoo.com/documentation/18.0/applications/general/email_communication/azure_oauth.html)[3](https://apps.odoo.com/apps/modules/14.0/microsoft_office_365_integration)[4](https://apps.odoo.com/apps/modules/17.0/sh_office365_connector)[6](https://apps.odoo.com/apps/modules/13.0/odoo_microsoft_azure_sso).

<figure><img src="../.gitbook/assets/Screenshot from 2025-06-21 13-02-01.png" alt=""><figcaption></figcaption></figure>

***

### **4. User UPN (User Principal Name)**

* **Where to Find:**
  * Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com/) or Azure Portal.
  * Navigate to **Users** > **Active users**.
  * Locate the user whose OneDrive will be used for Excel exports.
  * The **User Principal Name** is their login email address (e.g., `user@yourcompany.com`)[6](https://apps.odoo.com/apps/modules/13.0/odoo_microsoft_azure_sso).

<figure><img src="../.gitbook/assets/Screenshot from 2025-06-21 12-55-35.png" alt=""><figcaption></figcaption></figure>

***

### **5. Drive ID**

* **Where to Find:**
  * The Drive ID is a unique identifier for the user’s OneDrive.
  * You can obtain it using the [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer):
    * Make a GET request to:\
      `https://graph.microsoft.com/v1.0/users/{user-upn}/drive`
    * The response will include `"id": "drive-id-here"`.
  * Some connectors fetch this automatically after you enter the User UPN and credentials[3](https://apps.odoo.com/apps/modules/14.0/microsoft_office_365_integration).

***

### **6. Workbook File ID**

* **Where to Find:**
  * Open the target Excel file in OneDrive.
  *   Check the URL in your browser. The **File ID** is usually the long string after `id=` or `/file/` in the URL, for example:

      ```
      texthttps://onedrive.live.com/edit.aspx?cid=XXXXXXX&id=YYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYY
      ```

      The value after `id=` is your **Workbook File ID**.

***

### **7. Access Token**

* **Where to Find:**
  * The access token is generated automatically by the connector using your Tenant ID, Client ID, Client Secret, and User UPN.
  * You do **not** need to manually obtain or enter this; the connector manages token generation and refresh[1](https://www.odoo.com/documentation/18.0/applications/general/users/azure.html)[2](https://www.odoo.com/documentation/18.0/applications/general/email_communication/azure_oauth.html).

***

### Quick Reference Table <a href="#quick-reference-table" id="quick-reference-table"></a>

| Credential       | Where to Find / How to Obtain                                  |
| ---------------- | -------------------------------------------------------------- |
| Tenant ID        | Azure Portal → Azure Active Directory → Overview               |
| Client ID        | Azure Portal → App registrations → Your App → Overview         |
| Client Secret    | Azure Portal → App registrations → Certificates & secrets      |
| User UPN         | Microsoft 365 Admin Center → Users → Active users              |
| Drive ID         | Microsoft Graph API: `/users/{user-upn}/drive` or auto-fetched |
| Workbook File ID | In OneDrive Excel file URL (`id=` parameter)                   |
| Access Token     | Auto-generated by connector                                    |

***

### Support & Resources <a href="#id-12-support--resources" id="id-12-support--resources"></a>

* [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)
* [Odoo Documentation](https://www.odoo.com/documentation/18.0/)
* [Azure Portal](https://portal.azure.com/)
* Your module provider’s support channels

**Tip:** If you are unsure about any of these steps, contact your Azure/Microsoft 365 administrator for assistance—they can help you retrieve or generate the necessary values.

\
