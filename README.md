# LinkedIn Post and Image Generator – n8n Automation Workflow

This repository contains a workflow built in **n8n**, designed to automate the creation of LinkedIn post drafts and generate matching images using AI technologies. The project is developed for **Vivadrive**, an AI-powered fleet management company, and aims to streamline the content production process by integrating data sources, generative models, and cloud storage.

---

## Overview

The automation retrieves content ideas from Google Sheets, processes them through an AI agent to generate professional LinkedIn content, and creates AI-generated images that align with each post. The final output is stored in Google Drive, and stakeholders are notified via Discord.

---

## Key Features

- **Automated Content Generation**  
  Utilizes OpenAI’s GPT model to create three LinkedIn post drafts in distinct tones (professional, approachable, visionary) based on defined topics and references.

- **Visual Asset Creation**  
  Generates corresponding image descriptions and realistic, corporate-aligned visuals using the Hugging Face inference API.

- **Integrated Workflow Management**  
  Syncs with Google Sheets for input/output, Google Drive for storage, and Discord for notification—ensuring a seamless end-to-end content cycle.

- **Structured Prompting and Format Enforcement**  
  Applies strict character limits and formatting rules according to content type, ensuring consistency and brand alignment.

---

## Technologies Used

| Technology       | Role                                                                 |
|------------------|----------------------------------------------------------------------|
| `n8n`            | Workflow orchestration                                               |
| `OpenAI (GPT-4)` | Generates LinkedIn post drafts and image descriptions                |
| `Hugging Face`   | Generates AI-based visual assets based on descriptive prompts        |
| `Google Sheets`  | Serves as a dynamic content database (input and output)              |
| `Google Drive`   | Stores generated image files and makes them accessible via links     |
| `Discord`        | Sends alerts when new content drafts are ready for review            |

---

## Workflow Summary

1. **Trigger**: Executes daily to fetch content ideas from Google Sheets where the status is marked as "concept review".
2. **Data Merge**: Combines topic metadata with a predefined prompt template.
3. **Post Generation**: Uses OpenAI to generate three versions of a LinkedIn post per topic, each adhering to defined tone and character count.
4. **Image Generation**: Produces a visual description for each post and generates images using Hugging Face models.
5. **Storage**: Saves generated images to Google Drive and records links back into the sheet.
6. **Notification**: Sends a message via Discord to indicate that the content is ready for review.

---

## Setup Instructions

1. **Import the Workflow**  
   Upload the `LinkedIn_Posts___Image_Generator.json` file into your n8n environment.

2. **Configure Credentials**  
   Set up the following integrations within n8n:
   - OpenAI API (for GPT content generation)
   - Hugging Face API (for image generation)
   - Google Sheets API (read/write access)
   - Google Drive API (file storage)
   - Discord Webhook (notifications)

3. **Prepare the Google Sheet**  
   Ensure the Google Sheet has the following columns:  
   `Topic`, `Language`, `Type`, `References`, `Status`, and matching output fields for drafts and graphics.

4. **Activate the Workflow**  
   Enable the schedule trigger and allow the automation to process incoming ideas.

---

## Example Use Case

A content manager enters a new topic into the Google Sheet and marks it as "concept review." The system automatically generates three post drafts with tailored messaging and supporting images, saves them to the cloud, updates the sheet with results, and notifies the team via Discord.



