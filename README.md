# Multimodal-RAG-Chatbot-System
This project is an intelligent chatbot system capable of answering questions based on both text and image inputs. By combining document understanding with retrieval-augmented generation (RAG), it delivers accurate and context-aware responses in real time. Designed to enhance information access from complex visual and textual data.

## Key Features and Technologies

### 1. Multimodal Input Handling 

1. The system processes both text and image inputs, enabling users to ask questions based on documents or visual content.
2. For image-based inputs, PaddleOCR is utilized to extract textual information from images, making it possible to analyze and retrieve relevant data embedded within visuals.

### 2. Retrieval-Augmented Generation (RAG)

1. A RAG pipeline is implemented which combines retrieval with generative models to enhance contextual understanding.
2. Sentence-BERT embeddings are generated for text data, while CLIP embeddings are used for images, allowing for efficient semantic matching and retrieval.
3. FAISS is employed as the vector database to store and retrieve these embeddings, ensuring fast and accurate information retrieval.

### 3. Advanced Language Model Integration

1. Llama 3:8b Meta Instruct serves as the core language model, providing robust capabilities for generating coherent and contextually relevant responses.
2. Advanced prompting techniques, such as few-shot learning and chain-of-thought reasoning, are applied to further refine the model's understanding and response accuracy.

### 4. Real-Time Interaction

1. The chatbot is deployed via a Streamlit interface, offering a user-friendly platform for real-time interaction.
2. Users can input queries and receive immediate, context-aware responses based on the retrieved information.

##  How to Run the Chatbot

###  1. Install Dependencies

Install poppler-utils (for PDF processing):

!apt-get install -y poppler-utils

### 2. Install Python dependencies:

!pip install -r requirements.txt

This will install all the required packages listed in the requirements.txt file, including PaddleOCR, LangChain, FAISS, and others.

### 3. Upload and Process Documents

Step 1: Upload Documents

1. Use the first notebook cell to upload the desired PDF documents.
2. The system will automatically perform OCR on the uploaded files using PaddleOCR to extract text.

Step 2: Create Text Chunks

1. Once the OCR is complete, the extracted text will be split into manageable chunks.
2. These chunks are stored for further processing.

### 4. Generate Embeddings and Store in FAISS

Step 1: Generate Embeddings

1. Run the second notebook cell to generate Sentence-BERT embeddings for the text chunks.
2. Similarly, if there are images, CLIP embeddings will be generated.

Step 2: Store in FAISS

1. The embeddings are stored in a FAISS index for fast similarity search.

### 5. Set Up the Language Model with LM Studio

Step 1: Download LM Studio

1. Visit https://lmstudio.ai/ and download the latest version.

Step 2: Download the Model

1. Open LM Studio and search for the Meta-Llama-3-8b-instruct model in the Discover Section.
2. Download the Llama Model to make it available for usage.

Step 3: Get the Local Server Address

1. Once the model is downloaded, go to the Developer section and find the local server address (e.g., http://127.0.0.1:1234)
2. This is where the model will be served locally.

### 6. Configure Ngrok for External Access

Ngrok is used to expose your local server to the internet so that the chatbot can communicate with the language model.

Step 1: Install Ngrok

1. Visit https://ngrok.com/downloads/windows and download the ngrok executable file.

Step 2: Start Ngrok

1. Open a terminal or command prompt and run:
   ngrok http 1234
   Replace 1234 with the port number of your local server (from LM Studio).

Step 3: Copy the Forwarding URL

1. Ngrok will provide a public URL (e.g., https://abcdef.ngrok-free.app).
2. Copy this URL and append /v1/chat/completions to it in the LM_API_URL variable.
3. for e.g., LM_API_URL = "https://abcdef.ngrok-free.app/v1/chat/completions"

Step 4: Add Ngrok Authentication Token

1. Sign up for a free Ngrok account at ngrok.com.
2. Get your authentication token and add it to Ngrok in the notebook cell.
   !ngrok config add-authtoken "YOUR_TOKEN"
   Replace "YOUR_TOKEN" with your actual Ngrok token.

### 7. Launch the Streamlit Interface

Step 1: Run the Streamlit Cell

1. Run the cells underneath the label "Streamlit App Code" and "Launch the Interface".
2. Open your web browser and navigate to the URL provided by Streamlit (usually http://localhost:8501).
3. You can now interact with the chatbot in real time.

You’ve successfully set up and launched the Multimodal RAG Chatbot. Enjoy experimenting with it.

## Technologies Used

### 1. Tools & Libraries

PaddleOCR : For extracting text from images and scanned documents.

Sentence-BERT : To generate high-quality embeddings for text chunks.

CLIP : For generating image embeddings and enabling cross-modal understanding.

FAISS : Facebook AI Similarity Search library — used for fast and efficient vector retrieval.

LangChain : Provides the framework for building the RAG pipeline and managing prompts.

Streamlit : Powers the interactive web interface for real-time user interaction.

### 2. Document Processing

poppler-utils : Enables PDF parsing and page extraction for document processing.

### 3. Language Model

Llama 3:8b Meta Instruct (via LM Studio) : The backbone of response generation — a state-of-the-art open-source language model.
Ngrok : Used to expose the local LLM server to the internet for integration with the chatbot interface.

