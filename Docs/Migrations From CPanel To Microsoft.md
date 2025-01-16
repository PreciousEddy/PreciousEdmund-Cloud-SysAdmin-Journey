## Introduction:

CPanel is a control panel from web hosting solutions that enables you to manage your Webmail and other services from a single interface. You can set up and add a cPanel account with your favorite email client such as Outlook, Thunderbird through an IMAP connection or directly access the web email client Roundcube or Horde. cPanel also includes some additional features such as Autoresponders, Forwarders, Email Routing, Global Email Filters, Track Email Deliverability and so on.

----------------
Migrating from cPanel to Microsoft Office (Microsoft 365 or Exchange Online) involves transferring email, contacts, and calendar data from cPanel-hosted accounts to Microsoft Office's email platform. 

# Below are the steps to achieve this:

### **Step 1: Prepare for Migration**


1. **Plan Migration:**
   - Identify the email accounts to be migrated.
   - Notify users about the migration schedule to avoid disruptions.

2. **Backup Email Data:**
   - Log in to **cPanel** and back up email accounts using webmail (Roundcube or Horde) or download email via an email client (e.g., Thunderbird) using IMAP.

3. **Obtain Microsoft 365 Admin Access:**
   - Ensure you have admin access to your Microsoft 365 tenant to create and configure user accounts.

---

### **Step 2: Set Up Microsoft 365 Mailboxes**


1. Log in to the **Microsoft 365 Admin Center**.
2. Create new user accounts for each email address being migrated.
   - Assign licenses that include Exchange Online.

---

### **Step 3: Configure DNS Records**


1. Update your **DNS Records** to point to Microsoft 365:
   - Update **MX Records**, **Autodiscover**, **SPF**, and **CNAME** for email.
   - This ensures that new emails are routed to Microsoft 365.
2. Verify the domain in the Microsoft 365 Admin Center under **Setup > Domains**.

---

### **Step 4: Migrate Emails**


You can migrate emails using **IMAP Migration** or third-party tools.  

#### **Option 1: IMAP Migration**


1. Log in to the **Microsoft 365 Admin Center**.
2. Navigate to **Setup > Data Migration**.
3. Choose **IMAP** as the migration type.
4. Enter your cPanel server details:
   - **IMAP Server**: `mail.yourdomain.com`  
   - **Port**: `993`  
   - **Encryption**: SSL
5. Upload a CSV file with the following details:
   - Email address
   - Username (full email address)
   - Password
6. Start the migration process and monitor its progress.

#### **Option 2: Use Third-Party Tools**


For more advanced migrations, tools like **BitTitan MigrationWiz** or **CodeTwo Office 365 Migration** can handle complex data transfers, including contacts and calendars.

------------------------------

### **Step 5: Import Contacts and Calendar (Optional)**


1. Export contacts and calendar data from cPanel webmail:
   - **Contacts:** Export as CSV.
   - **Calendar:** Export as ICS.
2. Import into Microsoft 365:
   - **Outlook Web App**: Go to **Settings > People** to import contacts.
   - Use the **Import/Export** option to import calendars.

---

### **Step 6: Test and Verify**


1. Verify that all emails, contacts, and calendar entries have migrated.
2. Test sending and receiving emails from Microsoft 365.
3. Update users' email clients (Outlook, mobile devices) with their Microsoft 365 credentials.

---

### **Step 7: Decommission cPanel Email**


1. After confirming that all data has been migrated and users are fully transitioned to Microsoft 365, decommission the email services in cPanel.
2. Keep the cPanel account accessible for a short period as a fallback.

---

