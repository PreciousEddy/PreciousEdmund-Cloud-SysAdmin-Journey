# Adding a Domain to Microsoft 365

## This guide walks you through the process of adding a custom domain to Microsoft 365 (M365) for managing email, Teams, SharePoint, and other services. Follow the steps carefully to ensure a seamless setup.

---

## **Step 1: Prerequisites**

Before starting, ensure the following:

1. **Microsoft 365 Subscription:**
   - Ensure you have an active Microsoft 365 subscription with admin access.

2. **Domain Name:**
   - Purchase a domain from a registrar (e.g., GoDaddy, Namecheap).

3. **Access to DNS Settings:**
   - Ensure you can log into your domain registrar to update DNS records.

---

## **Step 2: Add Your Domain to Microsoft 365**

1. **Log into the Microsoft 365 Admin Center:**
   - Go to [Microsoft 365 Admin Center](https://admin.microsoft.com/) and log in as a Global Admin.

2. **Navigate to Setup:**
   - On the left-hand menu, click **Setup** > **Domains**.

3. **Add Your Domain:**
   - Click **Add Domain** and enter your domain name (e.g., `yourcompany.com`).
   - Click **Next** to proceed.

---

## **Step 3: Verify Your Domain**

Microsoft needs to verify ownership of your domain. You’ll need to add a TXT or MX record to your domain’s DNS settings.

1. **Choose a Verification Method:**
   - Select either **Add a TXT Record** (recommended) or **Add an MX Record**.

2. **Add the Record to Your DNS:**
   - Log into your domain registrar’s DNS management portal.
   - Create a new record with the following details:
     - **Type:** TXT or MX
     - **Host/Name:** `@` (or leave blank, depending on your registrar)
     - **Value/Data:** Copy the value provided by Microsoft (e.g., `MS=ms12345678`).
     - **TTL:** Set to 3600 (or default).

3. **Verify the Domain in Microsoft 365:**
   - Return to the Microsoft 365 Admin Center and click **Verify**.
   - It may take up to 30 minutes for DNS changes to propagate.

---

## **Step 4: Update DNS Records for Microsoft 365 Services**

To enable email and other services, you need to update DNS records. Microsoft provides the required records during setup.

1. **Retrieve DNS Records:**
   - After verifying your domain, Microsoft will display a list of DNS records.

2. **Add DNS Records to Your Registrar:**
   - Log into your domain registrar’s DNS management.
   - Add the following records:
     
     ### **Required Records**
     - **MX Record** (Email Routing):
       - **Host/Name:** `@`
       - **Points to:** `yourdomain-com.mail.protection.outlook.com`
       - **Priority:** 0
     
     - **CNAME Records** (Autodiscover & Services):
       - `autodiscover` > `autodiscover.outlook.com`
       - `sip` > `sipdir.online.lync.com`
       - `lyncdiscover` > `webdir.online.lync.com`
       - `enterpriseregistration` > `enterpriseregistration.windows.net`
       - `enterpriseenrollment` > `enterpriseenrollment.manage.microsoft.com`

     - **TXT Record** (SPF):
       - **Host/Name:** `@`
       - **Value/Data:** `v=spf1 include:spf.protection.outlook.com -all`

     - **SRV Records** (Skype for Business/Teams):
       - **Service:** `_sip`  
         **Protocol:** `_tls`  
         **Priority:** `100`  
         **Weight:** `1`  
         **Port:** `443`  
         **Target:** `sipdir.online.lync.com`

       - **Service:** `_sipfederationtls`  
         **Protocol:** `_tcp`  
         **Priority:** `100`  
         **Weight:** `1`  
         **Port:** `5061`  
         **Target:** `sipfed.online.lync.com`

3. **Save DNS Changes:**
   - Save the records in your DNS portal.

4. **Wait for Propagation:**
   - DNS changes may take up to 24 hours to propagate globally.

---

## **Step 5: Test Your Setup**

1. **Check Email Flow:**
   - Send a test email to ensure that Microsoft 365 is handling email properly.

2. **Use Diagnostic Tools:**
   - Use the **[Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/)** to verify DNS settings and troubleshoot.

3. **Confirm Services:**
   - Log into Microsoft 365 apps (Outlook, Teams, etc.) to confirm they’re working as expected.

---

## **Step 6: Additional Configuration (Optional)**

1. **Set Up Multi-Factor Authentication (MFA):**
   - Enhance security by enabling MFA for all users. 
   - Guide: [Set Up MFA in Microsoft 365](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-mfa-getstarted).

2. **Configure Policies:**
   - Set up conditional access, data loss prevention, and email retention policies.

3. **Migrate Existing Email:**
   - If needed, migrate email from cPanel or other services using tools like **BitTitan MigrationWiz** or manual IMAP migration.

---

## **Resources and Links**

1. **Microsoft 365 Admin Center:** [https://admin.microsoft.com/](https://admin.microsoft.com/)
2. **DNS Records for Microsoft 365:** [https://learn.microsoft.com/en-us/microsoft-365/admin/dns/create-dns-records-at-any-dns-hosting-provider](https://learn.microsoft.com/en-us/microsoft-365/admin/dns/create-dns-records-at-any-dns-hosting-provider)
3. **Remote Connectivity Analyzer:** [https://testconnectivity.microsoft.com/](https://testconnectivity.microsoft.com/)
4. **Microsoft 365 Setup Guides:** [https://learn.microsoft.com/en-us/microsoft-365/admin/setup/](https://learn.microsoft.com/en-us/microsoft-365/admin/setup/)

---

This guide covers the complete process of adding a domain to Microsoft 365. 