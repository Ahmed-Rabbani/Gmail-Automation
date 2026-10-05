# Gmail Automation & Gmail AI Agent

A powerful **n8n-based Gmail automation and AI agent** for managing Gmail tasks through an easy-to-use frontend. It supports sending and managing emails, drafts, labels, searching, read/unread status, bulk operations, and more.

Built with **n8n 2.41.6** and currently powered by **Google Gemini** for AI capabilities.

## Features

### Email Management

* Send emails
* Send multiple emails at once
* Search emails
* Retrieve emails
* Delete emails
* Mark emails as read
* Mark emails as unread
* Search only read emails
* Search only unread emails
* Get detailed email information

### Draft Management

* Create email drafts
* Retrieve drafts
* Delete drafts
* Manage drafts through the frontend

### Label Management

* Get Gmail labels
* Create new labels
* Add labels to emails
* Remove labels from emails
* Delete Gmail labels

### Bulk Email Support

The automation can process multiple emails in a single operation. You can provide recipient data through the frontend or upload a spreadsheet containing the required email information.

You can use your own spreadsheet data to provide multiple recipients and email details.

### Frontend Integration

The automation is designed to work with a custom frontend.

Users can fill out a form and select the required operation instead of manually writing commands.

The frontend can:

* Send requests to n8n
* Provide email information
* Select the required Gmail action
* Choose between sending an email or creating a draft
* Upload spreadsheet data
* Receive responses from n8n
* Display returned Gmail data in a user-friendly interface

The frontend and n8n workflow work together to provide a complete Gmail management system.

## Supported Gmail Operations

Currently supported operations include:

* Send email
* Send multiple emails
* Create draft
* Get drafts
* Delete drafts
* Search emails
* Get emails
* Delete emails
* Mark as read
* Mark as unread
* Get labels
* Create labels
* Add labels
* Remove labels
* Delete labels
* Search read emails
* Search unread emails

## AI Agent

The project also includes Gmail AI Agent functionality.

The current AI integration uses **Google Gemini**.

The AI functionality can be expanded in the future to support additional AI providers and models.

## Requirements

Before using this project, you need:

* n8n **2.41.6** or compatible version
* A Gmail account
* Gmail API / Google Cloud configuration
* Gmail OAuth2 credentials
* Google Gemini API key
* A frontend connected to the n8n webhook
* Optional spreadsheet data for bulk operations

This project can be used with both:

* Regular Gmail accounts
* Google Workspace accounts

## Installation

### 1. Download the Workflow

Clone the repository:

```bash
git clone https://github.com/Ahmed-Rabbani/Gmail-Automation.git
```

Or download the repository as a ZIP file from GitHub.

### 2. Open n8n

Open your n8n instance.

Go to:

**Workflows → Import from File**

Import the Gmail automation workflow JSON file from this repository.

### 3. Configure Gmail Credentials

This repository does **not** contain the creator's Gmail credentials.

After importing the workflow, you must configure your own Gmail credentials.

Create/configure your Gmail OAuth2 credentials and connect them to the required Gmail nodes.

Do not use someone else's credentials.

### 4. Configure Google Gemini

The AI Agent currently uses Google Gemini.

Add your own Gemini API key to the appropriate n8n credential/node configuration.

Never upload your API key to GitHub.

### 5. Configure the Frontend

Connect your frontend to the n8n webhook used by the workflow.

The frontend should send the required form data to n8n and display the response returned by the workflow.

### 6. Activate the Workflow

After configuring your credentials and frontend connection:

1. Test the workflow.
2. Verify Gmail operations.
3. Verify the frontend response.
4. Activate the workflow.

## Example Operations

### Send an Email

Select:

```text
Action: Send Email
```

Provide the required recipient, subject, message, and other information through the frontend.

### Create a Draft

Select:

```text
Action: Draft
```

The workflow creates the draft in Gmail and can return the draft information to the frontend.

### Search Emails

Select:

```text
Action: Search Emails
```

Provide the required search information and the workflow returns matching emails.

### Search Unread Emails

Select:

```text
Action: Search Unread
```

The workflow returns emails that have not been read.

### Mark Email as Read

Select:

```text
Action: Mark as Read
```

The selected email will be marked as read.

### Create a Label

Select:

```text
Action: Create Label
```

Provide the label name and the workflow creates it in Gmail.

### Bulk Email

Multiple recipient/email records can be provided at once, including through an uploaded spreadsheet.

The workflow processes the provided data and sends the emails accordingly.

## Spreadsheet Support

You can provide spreadsheet data to the automation for operations involving multiple emails.

For example:

```text
Name        Email              Subject       Message
Ahmed       ahmed@example.com  Welcome       Welcome to our service
John        john@example.com   Update        Here is your latest update
Sarah       sarah@example.com  Information   Here is the requested information
```

The exact columns can depend on how your frontend and workflow are configured.

## Security

**Your credentials are not included in this repository.**

You must use your own:

* Gmail credentials
* Google OAuth credentials
* Gemini API key

Never commit the following to GitHub:

```text
.env
API keys
OAuth tokens
Refresh tokens
Client secrets
Passwords
Credential JSON files
Private keys
```

Before making changes to the workflow, always check the exported JSON for sensitive information.

If you accidentally expose an API key or OAuth credential, revoke/rotate it immediately.

## Important

This project is provided as an open-source n8n workflow.

You are responsible for configuring your own Google/Gmail credentials and API access.

Gmail and Google API usage may be subject to Google's policies, quotas, and limitations.

## Future Improvements

Planned improvements may include:

* Additional AI providers
* More AI models
* Natural-language Gmail commands
* More advanced email automation
* Additional bulk operations
* More frontend functionality
* Advanced Gmail search capabilities
* Additional spreadsheet integrations

## Built With

* [n8n](https://n8n.io/)
* Google Gmail API
* Google Gemini
* JavaScript
* Custom Web Frontend

## Author

**Ahmed Rabbani**

GitHub:
https://github.com/Ahmed-Rabbani

## Credentials Setup

Before using the workflow, you need to configure your own Gmail OAuth2 credentials and Google Gemini API key.

**Never use or share someone else's credentials.**

### 1. Gmail OAuth2 Credentials

The Gmail nodes require your own Gmail OAuth2 credential.

#### Step 1 — Open Google Cloud Console

Go to:

https://console.cloud.google.com/

Create a new Google Cloud project or select an existing project.

#### Step 2 — Enable Gmail API

Open:

**APIs & Services → Library**

Search for:

**Gmail API**

Click **Enable**.

#### Step 3 — Configure OAuth Consent Screen

Go to:

**APIs & Services → OAuth consent screen**

Configure the application information.

If you are using the workflow for personal testing, you can normally configure it as an external application and add your own Google account as a test user when required.

#### Step 4 — Create OAuth Client

Go to:

**APIs & Services → Credentials**

Click:

**Create Credentials → OAuth client ID**

Select the appropriate application type required by your n8n setup.

Copy the generated:

* Client ID
* Client Secret

Keep these credentials private.

#### Step 5 — Add the Credential in n8n

Open your n8n instance.

Go to the Gmail node used by the workflow.

Under **Credentials**, create or select the appropriate Gmail OAuth2 credential.

Enter the required Google OAuth information and follow the authorization process.

Sign in with the Gmail account that you want this automation to manage.

After authorization, save the credential.

You can now use the Gmail nodes with your own account.

### 2. Google Gemini API Key

The Gmail AI Agent currently uses Google Gemini.

#### Step 1 — Open Google AI Studio

Go to:

https://aistudio.google.com/

Sign in with your Google account.

#### Step 2 — Create an API Key

Open the API key section and create a new API key.

Copy the generated API key.

**Do not publish this key on GitHub or share it publicly.**

#### Step 3 — Add Gemini to n8n

Open your n8n workflow and locate the Gemini/Google Gemini AI node used by the AI Agent.

Create a new Gemini credential and enter your API key.

Save the credential and select it in the relevant AI nodes.

### 3. Important Security Rules

Your credentials are specific to your own Google account.

Never add the following information to this repository:

```text
Gmail OAuth Client Secret
Gmail Access Token
Gmail Refresh Token
Gemini API Key
.env files containing secrets
Credential JSON files
Private keys
Passwords
```

The workflow provided in this repository should be used with **your own credentials**.

If you fork or download this project, configure your own Gmail and Gemini credentials in n8n.

### 4. Credential Summary

| Service       | Required Credential | Purpose                 |
| ------------- | ------------------- | ----------------------- |
| Gmail         | OAuth2              | Access and manage Gmail |
| Google Gemini | API Key             | AI Agent functionality  |

After configuring both credentials, import the workflow into n8n, assign the credentials to the relevant nodes, connect your frontend webhook, and test the workflow.


## License

This project is licensed under the **MIT License**.

You are free to use, modify, distribute, and build upon this project according to the terms of the MIT License.
