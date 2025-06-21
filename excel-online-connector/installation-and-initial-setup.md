---
description: >-
  The complete process of installing the Odoo Excel Online Connector module and
  performing the initial configuration to connect Odoo with Microsoft Excel
  Online via OneDrive
---

# Installation & Initial Setup

## Module Installation <a href="#id-1-module-installation" id="id-1-module-installation"></a>

### Step 1: Access Odoo Apps

* Log in to your Odoo instance with administrative privileges.
* Navigate to the **Apps** menu from the main dashboard.

### Step 2: Search for the Connector Module

* In the search bar, type **"Excel Online Connector"** or the specific name of your module.
* Locate the module in the search results.

### Step 3: Install the Module

* Click the **Install** button.
* Wait for the installation process to complete.
* Once installed, the module will add a new app icon named **"Excel Online Connector"** in the Odoo app launcher (nine dots menu).

***

## 2. Initial Configuration <a href="#id-2-initial-configuration" id="id-2-initial-configuration"></a>

### Step 1: Open Connector Settings

* Go to **Settings** → **Excel Online Connector** (or the specific settings menu your module provides).

### Step 2: Enter Azure AD Credentials

You will need to provide the following information, which you can find as described in the **Required IDs and Credentials** section:

* **Tenant ID:** Your Azure Active Directory tenant identifier.
* **Client ID:** The Application (client) ID from your Azure app registration.
* **Client Secret:** The secret key generated for your Azure app.
* **User UPN:** The email address of the Microsoft 365 user whose OneDrive will be used for Excel exports.

### Step 3: Save Configuration

* After entering all required fields, click **Save**.
* The connector will attempt to validate your credentials and establish a connection.
* If successful, it will automatically retrieve the **Drive ID** and generate the necessary **Access Token**.

***

### 3. Verify Connection <a href="#id-3-verify-connection" id="id-3-verify-connection"></a>

* Once saved, check for any error messages.
* If no errors appear, your connector is ready to use.
* You can now proceed to create export tasks and send data from Odoo to Excel Online.

***

### 4. Troubleshooting Tips <a href="#id-4-troubleshooting-tips" id="id-4-troubleshooting-tips"></a>

* **Invalid Credentials:** Double-check all entered IDs and secrets for typos.
* **Permission Issues:** Ensure your Azure app has the required Microsoft Graph API permissions.
* **Network Access:** Confirm your Odoo server can access the internet and Microsoft Graph API endpoints.
* **Token Expiry:** The connector automatically refreshes tokens, but if you face issues, try re-saving the configuration.

<table data-full-width="false"><thead><tr><th>Issue</th><th>Solution</th></tr></thead><tbody><tr><td>Invalid credentials/token</td><td>Double-check Tenant ID, Client ID, Client Secret, and User UPN. Save settings to refresh.</td></tr><tr><td>Drive/File not found</td><td>Ensure the Excel file exists in the specified user's OneDrive.</td></tr><tr><td>Permission denied</td><td>Ensure your Azure app has correct Microsoft Graph API permissions (Files.ReadWrite, etc.).</td></tr><tr><td>Export fails on binary field</td><td>Deselect binary/image fields when exporting.</td></tr></tbody></table>

***

### 5. Next Steps <a href="#id-5-next-steps" id="id-5-next-steps"></a>

* After successful setup, navigate to the **Excel Online Connector** app.
* Create your first export task by selecting the Odoo model, fields, and target Excel file.
* Export data and enjoy seamless integration between Odoo and Excel Online.
* When creating an export task in the Odoo Excel Online Connector, you’ll be asked to enter the **Workbook File ID**. This ID uniquely identifies your Excel file in OneDrive or SharePoint and is required for the connector to write data to the correct file.

### **Where to Find the Workbook File ID**

1.  **Open your Excel file in OneDrive or SharePoint.**\
    For example, your file might have a URL like this:

    ```
    texthttps://niyulabs-my.sharepoint.com/:x:/r/personal/rohitdhiman_niyulabs_onmicrosoft_com/_layouts/15/doc.aspx?sourcedoc=%7B0d563bab-6865-4bea-934e-fb2516578f81%7D&action=edit
    ```
2. **Locate the `sourcedoc` parameter in the URL.**
   *   In your example, the parameter is:

       ```
       textsourcedoc=%7B0d563bab-6865-4bea-934e-fb2516578f81%7D
       ```
   * The value between `%7B` and `%7D` (which are URL-encoded curly braces `{}`) is your Workbook File ID.
3. **Decode the File ID.**
   * `%7B` = `{` and `%7D` = `}`
   *   The actual File ID is:

       ```
       text0d563bab-6865-4bea-934e-fb2516578f81
       ```
4. **Copy only the GUID (without the curly braces or percent signs).**
   *   **Workbook File ID:**

       ```
       text0d563bab-6865-4bea-934e-fb2516578f81
       ```

### **How to Recognize the Workbook File ID in the URL**

* It is the long string of letters and numbers (a GUID) found in the `sourcedoc` parameter of the URL.
*   It always looks like:

    ```
    textsourcedoc=%7Bxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx%7D
    ```

    or

    ```
    textsourcedoc={xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}
    ```
* The part inside the curly braces `{}` is your File ID.

### **Where to Enter the Workbook File ID**

* When creating or editing an export task in Odoo, paste this File ID into the **Workbook File ID** field.

***

### **Visual Example**

**URL Example:**

```
texthttps://niyulabs-my.sharepoint.com/:x:/r/personal/rohitdhiman_niyulabs_onmicrosoft_com/_layouts/15/doc.aspx?sourcedoc=%7B0d563bab-6865-4bea-934e-fb2516578f81%7D&action=edit
```

**Extracted Workbook File ID:**

```
text0d563bab-6865-4bea-934e-fb2516578f81
```

***

**Tip:**\
If your URL has `%7B` and `%7D`, just copy the part in between and ignore the percent signs and curly braces.

***

**Note:** For detailed instructions on creating export tasks and managing exports, refer to the **Contact Us on info@niyulabs.com.**
