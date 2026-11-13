# Automated Email Enquiry Tracking System (n8n)

## Business Problem
Manually tracking incoming customer enquiries across a busy inbox is time-consuming, prone to human error, and often leads to delayed responses. Businesses need an automated way to log every inquiry into a central tracker and immediately reassure customers that their message was received.

## Workflow Overview
This n8n workflow automates inquiry logging and acknowledgment in four steps:
1. **Gmail Trigger**: Monitors the inbox for new incoming inquiry emails.
2. **Edit Fields**: Extracts and cleans key details (Sender, Subject, Message, Date, and Message ID).
3. **Google Sheets (Append Row)**: Logs the structured inquiry data into a central tracking spreadsheet.
4. **Gmail (Send Message)**: Sends a standardized acknowledgment email back to the sender.

## Workflow Architecture
![Workflow Screenshot](<./Screenshot 2026-11-13 054909.png>)

## Sample Test Results
- **Logged Entry**: Tested with a fictional service inquiry (`Roger Johnson <roger95johnson@gmail.com>`), successfully creating a new row in Google Sheets.
- **Auto-Reply**: Confirmed delivery of the fixed acknowledgment message to the sender.

![Test Result 1](<./Screenshot 2026-11-13 055050.png>)
![Test Result 2](<./Screenshot 2026-11-13 055126.png>)
![Test Result 3](<./Screenshot 2026-11-13 055231.png>)

## What I Learned
- How to map dynamic data between nodes using n8n expressions (e.g., `{{ $json.Sender }}`).
- The difference between **Fixed** and **Expression** fields, as well as **HTML** vs. **Text** email formatting.
- Best practices for testing email automations safely to avoid infinite loops and `noreply` bounces.
