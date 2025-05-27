# LinkedIn Post and Image Generator – n8n Automation Workflow

This repository provides an **n8n workflow** that automates the generation of LinkedIn post drafts and corresponding images using AI. It is designed to streamline content creation by integrating data sources, generative models, and cloud storage.

---

## 🔍 Overview

The workflow retrieves topic ideas from Google Sheets, generates post drafts using OpenAI, creates aligned image descriptions, and produces visuals via Hugging Face. The results are saved to Google Drive and the team is notified through Discord.

---

## ✅ Key Features

- **AI-Generated LinkedIn Content**  
  Automatically creates three unique post drafts (professional, approachable, visionary) for each topic.

- **Realistic Image Generation**  
  Produces image descriptions and visuals that complement each post using Hugging Face inference models.

- **End-to-End Integration**  
  Connects Google Sheets, Google Drive, and Discord for seamless workflow automation.

- **Structured Prompting**  
  Enforces tone, character count, and formatting through a robust system prompt.

---

## ⚙️ Technologies Used

| Tool              | Purpose                                                  |
|-------------------|----------------------------------------------------------|
| `n8n`             | Workflow automation                                       |
| `OpenAI (GPT-4)`  | Generates text content and image descriptions            |
| `Hugging Face`    | Creates AI-generated visuals                             |
| `Google Sheets`   | Source and destination for structured content data       |
| `Google Drive`    | Stores generated image assets                            |
| `Discord`         | Notifies users of new content drafts                     |

---

## 🧩 Workflow Summary

1. **Trigger**: Runs daily to fetch new content ideas from Google Sheets (`Status = concept review`).
2. **Merge Input Data**: Combines topic, language, type, and references with a prompt template.
3. **Post Generation**: Creates three LinkedIn post drafts with distinct tones via OpenAI.
4. **Image Generation**: Generates image descriptions and AI-based visuals.
5. **Storage**: Uploads images to Google Drive and records links back to the sheet.
6. **Notification**: Sends a Discord message to indicate content is ready for review.

---

## 🗺️ Visual Overview

The following diagram illustrates the full automation workflow from idea intake to content generation:

![image](https://github.com/user-attachments/assets/604d39d2-d7cb-4174-98ed-c0166368f604)


---

## 🚀 Setup Instructions

1. **Import Workflow**  
   Upload `LinkedIn_Posts___Image_Generator.json` to your n8n instance.

2. **Configure Required Credentials**  
   - OpenAI API (for content generation)  
   - Hugging Face API (for image generation)  
   - Google Sheets (input/output)  
   - Google Drive (image storage)  
   - Discord Webhook (notifications)

3. **Prepare Google Sheet**  
   Ensure it includes the following columns:  
   `Topic`, `Language`, `Type`, `References`, `Status`, plus output fields for drafts and images.

4. **Activate Workflow**  
   Enable the scheduler and run the workflow to begin automation.

---

## 💡 Example Use Case

A content planner submits a new topic to Google Sheets and sets its status to "concept review." The workflow automatically generates three tailored LinkedIn posts, creates matching visuals, updates the sheet with content and image links, and alerts the team via Discord.

---

## 📄 License

This project is shared for demonstration and educational purposes. 
