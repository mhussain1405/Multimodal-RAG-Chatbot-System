### Multimodal-RAG-Chatbot-System
This project is an intelligent chatbot system capable of answering questions based on both text and image inputs. By combining document understanding with retrieval-augmented generation (RAG), it delivers accurate and context-aware responses in real time. Designed to enhance information access from complex visual and textual data.

## Key Features and Technologies

# Multimodal Input Handling 

1. The system processes both text and image inputs, enabling users to ask questions based on documents or visual content.
2. For image-based inputs, PaddleOCR is utilized to extract textual information from images, making it possible to analyze and retrieve relevant data embedded within visuals.

# Retrieval-Augmented Generation (RAG)

1. A RAG pipeline is implemented which combines retrieval with generative models to enhance contextual understanding.
2. Sentence-BERT embeddings are generated for text data, while CLIP embeddings are used for images, allowing for efficient semantic matching and retrieval.
3. FAISS is employed as the vector database to store and retrieve these embeddings, ensuring fast and accurate information retrieval.

# Advanced Language Model Integration

1. Llama 3:8b Instruct serves as the core language model, providing robust capabilities for generating coherent and contextually relevant responses.
2. Advanced prompting techniques, such as few-shot learning and chain-of-thought reasoning, are applied to further refine the model's understanding and response accuracy.

# Real-Time Interaction

1. The chatbot is deployed via a Streamlit interface, offering a user-friendly platform for real-time interaction.
2. Users can input queries and receive immediate, context-aware responses based on the retrieved information.

##  How to Run the Chatbot

#  Install Dependencies

Install poppler-utils (for PDF processing):

!apt-get install -y poppler-utils

# Install Python dependencies:

!pip install -r requirements.txt

This will install all the required packages listed in the requirements.txt file, including PaddleOCR, LangChain, FAISS, and others.
