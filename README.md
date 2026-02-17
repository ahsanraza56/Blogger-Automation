# 🤖 Autonomous AI Blogger Workflow (n8n)

**Automate your content pipeline from Idea to Published Blog Post.**

This n8n workflow creates a fully automated "Programmatic SEO" engine. It takes a tool name and URL, scrapes the content, uses **Google Gemini 2.5** to write a full HTML-formatted blog post, generates a unique feature image using **Stable Diffusion XL**, and publishes it directly to **Blogger**.
<img width="942" height="319" alt="image" src="https://github.com/user-attachments/assets/7e6d40a2-1651-428c-97c6-bde5348a200c" />


## 🚀 Features

* **🔍 Content Scraping:** Extracts core information from any given URL to ensure factual accuracy.
* **🧠 Advanced LLM Writing:** Uses **Google Gemini 2.5 Flash** to write 1,500+ word posts with proper HTML formatting (Lists, Tables, H2/H3 tags).
* **🎨 AI Art Generation:** Generates context-aware, futuristic feature images using **Stable Diffusion XL** (via HuggingFace).
* **☁️ Google Drive Integration:** Automatically uploads generated images to Drive for hosting.
* **db Blogger API:** Publishes the final article with the image embedded and SEO metadata applied.

## 🛠️ Prerequisites

To use this workflow, you need:
1.  **n8n** (Self-hosted or Cloud version).
2.  **Google Cloud Console Project** with the following APIs enabled:
    * Blogger API v3
    * Google Drive API
    * Vertex AI API (or Google PaLM API)
3.  **Hugging Face Account** (Access Token for Inference API).

## ⚙️ Setup & Configuration

1.  **Import the Workflow:**
    * Download the `blogger_automation.json` file from this repo.
    * In n8n, go to **Workflows** -> **Import from File**.

2.  **Configure Credentials:**
    * **Google Gemini:** Set up your Google PaLM/Gemini credentials.
    * **Google Drive:** Authenticate your Google Drive account.
    * **Blogger:** Authenticate your Blogger account (OAuth2).
    * **Hugging Face:** Add your API token in the `Image Generator` node headers (`Authorization: Bearer YOUR_TOKEN`).

3.  **Update Hardcoded IDs:**
    * **Upload File Node:** Change the `Folder ID` to the specific Google Drive folder where you want images stored.
    * **Blogger Post Node:** Change the `Blog ID` in the URL (currently set to a placeholder) to your specific Blogger ID.

## 🏃 How to Run

1.  Open the workflow.
2.  Click **Execute Workflow** (or use the Production URL).
3.  The workflow expects a **Form Submission** or manual input with the following JSON fields:
    ```json
    {
      "tool_name": "Name of the Tool",
      "tool_url": "[https://tool-website.com](https://tool-website.com)",
      "affiliate_link": "[https://your-affiliate-link.com](https://your-affiliate-link.com)"
    }
    ```

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

---
*Created by [Your Name]*
