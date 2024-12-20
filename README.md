# InsightAI chatbot
*Full-stack  Retrieval-Augmented Generation (RAG) based chatbot enabling URL submission, real-time content extraction, and context-aware responses from LLMs with OpenAI, Flask, React, and Pinecone*

<img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExczdhcjIyZTd1YWZmdDdsem1rbTd3c2VjYnR6YmtmcTF5bjFuajAzciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/oolHrmHDE9XtZtSLG8/giphy.gif" width="800">

## Architecture
<img src="https://i.imgur.com/FqOr8t8.png" witdth="800">

### Components of the full application:
* **Backend (Flask):** This handles the logic to scrape the website and call OpenAI's Embeddings API to create embeddings from the website's text. It also stores these embeddings in the vector database (Pinecone) and retrieves relevant text to help the LLM answer the user's question.
* **OpenAI:** We'll call two different API's from OpenAI: (1) the Embeddings API to embed the text of the website as well as the user's question, and (2) the ChatCompletions API to get an answer from GPT-4 to send back to the user.
* **Pinecone:** This is the vector database that we'll use to (1) send the embeddings of the website's text to, and (2) retrieve the most similar text chunks for constructing the prompt to send to the LLM in step 3.
* **Frontend (React):** This is the interface that the user interacts with to input a URL and ask questions about the webpage.


## Setup

**Install Python dependencies**

```sh
pip install -r requirements.txt
```
**Install React dependencies**
```sh
cd client
npm install
```

**Create .env file**
```sh
OPENAI_API_KEY=<YOUR_API_KEY>
PINECONE_API_KEY=<YOUR_API_KEY>
```

**Start the Flask server**
```sh
# In root directory
python run.py
```

**Start the React app**
```sh
cd client
npm start
```
