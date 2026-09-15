<p align="center">
  <img src="docs/images/logo.svg" alt="MyMaCo Logo" width="180" />
</p>

<h1 align="center">MyMaCo</h1>

<p align="center">
  <strong>Multi-Instance Management & Analytics for n8n</strong>
</p>

> **⚠️ ALPHA RELEASE WARNING:**
> MyMaCo is currently in **ALPHA**. This means the software is in development. Features might break, change unexpectedly, or behave unpredictably**. Please use it with caution and do not rely on it for critical operations without adequate backups.

> At this moment MyMaCo only reads from your n8n instance database, when this changes we will change the Docker tag and make proper announcements to make sure you are aware of the changes before applying.

# What is MyMaCo?
MyMaCo is a centralized management and insight tool designed specifically for users running multiple **n8n** instances.

Managing several n8n environments can quickly become complex, often requiring administrators to manually jump between instances to check workflow statuses, track changes, or gather performance metrics. MyMaCo solves this by bringing all that fragmented data into one unified dashboard.

## How It Works: The SYNC Process

At the core of MyMaCo is its robust **SYNC process**. Rather than relying purely on APIs, MyMaCo connects directly to the underlying PostgreSQL databases of your various n8n instances.

Through this direct database connection, the SYNC process securely and efficiently extracts raw data about your n8n environments and feeds it into the central MyMaCo application.

## Key Features

MyMaCo automates data collection to provide deep, actionable insights into your environments. Below is a breakdown of the core views and capabilities available:

### 📁 Instance & Folder Overview

Get an at-a-glance understanding of everything happening inside a specific n8n instance.

* **Comprehensive Overviews:** See which workflows are active, their triggers, and when they were last executed.

* **Basic Stats:** Instantly view the number of executions, failure rates, average durations, and token usage for your workflows.

* **Flexible Navigation:** Browse through folders with the option to include or exclude workflows located in nested subfolders.

* **Advanced Filtering:** Quickly filter your view to only show workflows that contain errors or utilize AI tokens.

### 🔍 Workflow Detail & Documentation

Deep dive into individual workflows for better documentation and troubleshooting.

* **Custom Descriptions:** Add custom short and long descriptions to workflows for documentation purposes. The short description is automatically surfaced in the general overview.

* **Node & Version Auditing:** See exactly which nodes, versions, and credentials are being used within the workflow.

* **Quick-Access Tabs:** Utilize a dedicated tab to see all triggers and credentials tied to the flow in one simple overview.

### 🔐 Credentials Management

Maintain strict security and clean environments with the global credentials view.

* **Usage Mapping:** See every credential in your environment and trace exactly which workflows—and specifically which *nodes*—are using them.

* **Orphaned Credentials:** Easily identify unused credentials so you can safely revoke and remove them.

### ⚡ Executions Dashboard

Monitor server activity and drill down into performance metrics.

* **Scope & Filtering:** View executions across the entire instance or filter down to specific folders. Filter by status or workflow duration (e.g., hiding short, frequent polling flows that clutter your logs).

* **Smart Aggregation:** View data in two ways:

  1. **Grouped by Parent Flow:** See all information and stats for a parent workflow, including all associated subflows.

  2. **Per Workflow:** View stats specifically isolated to individual workflows.

* **Execution Stats:** Track total executions, failed executions, durations, and token counts.

### 🤖 AI Token & Cost Tracking

For users leveraging n8n's advanced AI capabilities, MyMaCo provides a dedicated analytics view.

* **Cost Breakdowns:** See exact cost distributions and track trends in cost and token consumption over time.
* **Custom Pricing:** Manually set and configure the cost per AI model yourself to accurately reflect your API usage.
* **Model Utilization:** Identify which workflows are using which AI models.
* **Optimization:** Quickly spot which models are used the most and which ones are consuming the largest portion of your budget.

### ⚙️ Workflow Settings Audit

* **Global Settings View:** See the configuration settings for all workflows side-by-side. This makes it incredibly easy to spot configuration gaps, such as workflows where you forgot to assign a global error trigger workflow.

### 🔗 Webhooks View

* **Active Webhooks:** See a centralized list of all active webhooks across the instance, complete with direct links to easily jump to the workflow where they are located.

---

## Development History

MyMaCo is the result of over **4 years of development**. We take pride in our engineering, which is why there is absolutely no "vibecoding" used in the core components of the platform—ensuring a deliberate, stable, and secure architecture. *(Note: While the code is hand-crafted, this documentation is AI-generated)*

## Licensing & Hosting

Please note that MyMaCo is **not** Free or Open Source Software (FOSS).

* **Licenses:** A license must be purchased via an official MyMaCo Partner. Trial licenses are occasionally provided upon request.
* **Hosting:** By default, MyMaCo is designed to be fully self-hosted. However, if you prefer not to manage the infrastructure, our partners can provide managed hosting options for you.

## Community & Support

We'd love to hear from you! 

* **Feature Requests & Bug Reports:** Please submit these via GitHub Issues or in our Discord server.
* **Questions & Conversation:** Have a general question or just want to chat with the community? Join us on Discord!
* **Join the Server:** [MyMaCo Discord](https://discord.gg/JmUc2msrZ)

## Become a Partner

Interested in joining the MyMaCo ecosystem? If you would like to become a partner to sell licenses or provide managed hosting for clients, please reach out to us on Discord or via email at **[mymaco@datafix.nl](mailto:mymaco@datafix.nl)**.
