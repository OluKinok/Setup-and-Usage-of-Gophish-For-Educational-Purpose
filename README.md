# Setup-and-Usage-of-Gophish-For-Educational-Purpose
This project demostrates the setting up and usage of Gophish in a controlled, authorised phishing simulation lab environment FOR EDUCATIONAL PURPOSE ONLY. This is explicitly intended for defensive security training, awareness campaigns.
PROJECT OBJECTIVES

1. Installing Gophish in a lab environment
2. Configuring secure access (TLS, admin credentials)
3. Creating test groups and email templates 
3. Running and monitoring a controlled phishing simulation
4. Post-campaign analysis


TOOLS

-Gophish (official release)
-Kali Linux
- VirtualBox
- Web browser for the Gophish Admin UI
- SMTP relay (local/test), MailHog/SMTP4DEV for capture, or a dedicated test SMTP server
- Analysis tools: spreadsheets, SIEM, or ELK stack for logs


LAB TOPOGRAPHY

[internal network]--->Kali Linux ----> [Gophish] ----> [email address (targets) I own and control]
         |
   SMTP (MailHog / SMTP4DEV)

- Keep the whole setup isolated from production and the public internet.


INSTALLATION

1. Download the official Gophish website.
2. Verify the binary checksum (when provided) to ensure authenticity.
3. Place the binary on the lab host (Kali Linux) and mark it executable.
4. Configure the config.json (Gophish configuration file) to set:
      -Admin listener address & port (e.g., 127.0.0.1:3333 in the lab)
        -Phishing server listener (where Gophish serves landing pages)
        -TLS certificate paths (recommended for admin UI)
         -Database path (default SQLite)
4. Protect the admin account with a strong password


CONFIGURATION

1. Groups (Targets): This is an email address I own and control
2. Email Templates: Use placeholder content. 
   e.g:
   Subject: [Lab] Security Awareness Test
   Body: 
This message is part of a simulated training campaign. If you received this by mistake, notify the lab admin.
3. Landing Pages: This is a page that collect campaign feedback (e.g., a “You’ve completed the training” page).


RUNNING A CAMPAIGN (SAFE AND AUTHROISED)


1. Create a new Group and upload the approved test account.
2. Create an Email Template.
3. Create a Landing Page with an informational/educational message.
4. Launch the Campaign.
5. Monitor delivery status and results from the Gophish Admin UI.


MONITORING AND ANALYSIS

1. Use Gophish reporting to capture:
      - Email delivery and click stats
       -Landing page visits
       -SMTP responses and bounce messages
2. Export the results (CSV/JSON) and analyze in spreadsheets or a SIEM. Focus on metrics such as click rate, interaction time, and follow-up remediation training needs.
3. Correlate campaign data with other telemetry (web logs, endpoint logs) in a lab to practice detection and incident response playbooks.


AUTHOR:
Name: Olumide Akinokun
Role:  Cybersecurity Analyst
LinkedIn: www.linkedin.com/in/akinokun-olumide
