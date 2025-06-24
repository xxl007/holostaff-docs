# Deploying Your AI Staff Member

The "Deployment" tab is the final step before your AI Staff Member goes live and starts interacting with your users. Here, you manage where and how your AI is integrated into your existing platforms, and you control its operational status.

Access this tab by navigating to a specific AI Staff Member's detail page and selecting the "Deployment" tab.

## 1. Deployment Status

Your AI Staff Member's overall operational state is managed here:

*   **Status Indicators:** The status (e.g., Active, Inactive, Pending) reflects whether your AI is currently live and interacting with users.
*   **Activate/Pause Controls:** You can activate a pending deployment to bring your AI live or pause an active deployment to temporarily take it offline. These actions initiate processes that update the AI's availability.

## 2. Active Deployments

This section provides a table listing all the configured deployment points for your AI Staff Member.

*   **Website:** The base URL of the website where the AI is deployed.
*   **Page:** The specific path (or just '/') on the website where the AI widget is embedded.
*   **Status:** The current status of that particular deployment (e.g., active, inactive, pending).
*   **Configured At:** The date when this deployment was first set up.
*   **Actions:**
    *   **Activate:** For pending or inactive deployments, this button brings the AI live on that specific page.
    *   **Pause:** For active deployments, this button temporarily takes the AI offline for that specific page.
    *   **Update/Redeploy:** After making any changes to the AI's Style, Widget, or Instructions tabs, use this action to push the latest configurations to the live deployment.
    *   **Remove:** Permanently deletes this deployment configuration. This action cannot be undone.

*   **New Deployment:**
    *   Clicking the "New Deployment" button will open a dialog to configure an additional deployment point for your AI. You'll typically specify the website URL and the exact page path where the AI should appear.

## 3. Embed Code

The embed code is a small snippet of JavaScript that you will paste into your website's HTML. This code initializes and displays your AI staff member's chat widget.

*   **Getting the Code:** The "Embed Code" text area will display the unique script for your AI staff member.
*   **Copying the Code:** Click the "Copy Code" button to easily copy the entire snippet to your clipboard.
*   **Pasting the Code:**
    1.  Access your website's HTML code (e.g., through your website's content management system (CMS), your web developer, or direct file access).
    2.  Paste the copied code just **before the closing `</body>` tag** in your website's HTML. It is recommended to include it on every page where you want the AI staff to appear.

## 4. CMS Integrations

Holostaff AI offers direct integration options for popular Content Management Systems (CMS) to simplify the deployment process.

*   **Platform-Specific Guides:** This section provides links or high-level instructions for integrating with various CMS platforms like:
    *   WordPress
    *   Shopify
    *   Wix
    *   Webflow
    *   HubSpot
    *   Salesforce
*   For detailed step-by-step instructions for each platform, refer to the specific documentation provided within the platform's module or a dedicated documentation page linked from here.

## 5. Preview with Chrome Extension

To test your AI staff member on any webpage before making permanent changes to your website, you can use our dedicated Chrome Extension:

*   **Install Extension:** Follow the instructions to install the "Holostaff AI Tester" extension from the Chrome Web Store.
*   **Copy Embed Code:** Use the "Copy Embed Code" button from the Deployment tab.
*   **Open Target Page:** Navigate to the specific webpage where you want to test the AI.
*   **Use Extension:** Click the Holostaff AI Tester extension icon in your Chrome toolbar. Paste the copied embed code into the extension's popup textarea, and click "Inject AI Staff".
*   **Verify:** If successful, the AI staff widget should appear on the webpage, allowing you to test its functionality in real-time. Ensure your AI's deployment status is "active" for it to function correctly during testing.

## Saving Changes

Any changes made within the "Deployment" tab, especially related to the status of deployments or creation of new ones, are automatically updated in the system. Clicking "Activate" or "Pause" on a deployment will also trigger the necessary updates.
