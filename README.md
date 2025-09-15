### **Project Title: Automated Meeting Minutes Generator with n8n and Gemini**

### **Summary**
This project is an n8n workflow that automates the creation and distribution of formal "Minutes of Meeting" (MoM). It reads raw meeting notes from a Google Doc, uses Google's Gemini Pro AI model to generate a structured summary, and then automatically emails the final minutes to specified recipients.

### **Key Features**
* **Automated Data Retrieval**: Fetches raw text directly from a specified Google Document.
* **AI-Powered Summarization**: Leverages the Google Gemini Pro model (`gemini-1.5-pro-latest`) to intelligently process the notes.
* **Structured Output**: The AI is prompted to generate a professional summary including key discussion points, action items, and decisions made.
* **Automatic Distribution**: The final, formatted minutes are automatically sent out via Gmail.
* **Low-Code**: Built entirely within the n8n platform, demonstrating skills in modern automation tools.

### **How It Works (Workflow Breakdown)**
The workflow is composed of four main steps connected in a sequence:

1.  **Manual Trigger**: The process begins when the workflow is manually executed in the n8n interface.
2.  **Get a Document**: The workflow's first action is to connect to the Google Docs API and retrieve all the text content from a predefined document URL.
3.  **Message a Model (Gemini AI)**: The raw text is then passed to a Google Gemini node. A specific prompt instructs the model to act as a "professional meeting assistant" and transform the text into structured Minutes of Meeting.
4.  **Send a Message**: The final output text from the Gemini model is embedded into an HTML email and sent through the Gmail API to a recipient (`prerna.40.sharma@gmail.com`) with the subject "Minutes of Meeting".

### **Technologies Used**
* **n8n**: The core platform for workflow automation.
* **Google Gemini API**: For Natural Language Processing and text generation.
* **Google Docs API**: For reading the source meeting notes.
* **Gmail API**: For distributing the final output.
* **JSON**: The format for the n8n workflow file.

### **Setup & Configuration**
To use this workflow, you would need to:
1.  Import this JSON file into an n8n instance.
2.  Configure credentials for Google Docs, Google Gemini, and Gmail.
3.  Update the URL in the "Get a document" node to your own Google Doc containing meeting notes.
4.  Modify the email recipient in the "Send a message" node.
