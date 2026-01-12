Zoning Regulations RAG Assistant

A Retrieval-Augmented Generation (RAG) application designed to assist with queries regarding zoning regulations. This tool leverages a vector database to retrieve relevant legal text and provides AI-generated answers based on the specific context of zoning codes.

📂 Project Structure

app.py: The main application entry point (likely the user interface or API server).

prompt.py: Contains the system prompts and templates used to guide the LLM's responses.

chroma_db/: A persistent directory containing the ChromaDB vector store, where the zoning documents have been embedded and indexed.

test_app.py: Unit tests to ensure the application logic performs as expected.

requirements.txt: List of Python dependencies.

🚀 Features

Semantic Search: Uses a vector database (ChromaDB) to find relevant zoning sections based on the meaning of your query, not just keywords.

Context-Aware Answers: Retrieves the specific text of regulations and feeds it to an LLM to generate accurate, sourced responses.

Persistent Storage: The vector database is saved locally in chroma_db/ so you don't need to re-index documents every time you restart the app.

🛠️ Installation

Clone the repository:

git clone <repository-url>
cd Zoning_Regulations_RAG


Create and activate a virtual environment (optional but recommended):

python -m venv venv
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate


Install dependencies:

pip install -r requirements.txt


Environment Configuration:
If the application requires an OpenAI API key or similar, ensure you have set up your environment variables. You typically need to create a .env file or export the key:

export OPENAI_API_KEY="your-api-key-here"


▶️ Usage

To run the main application:

# If using Streamlit
streamlit run app.py

# OR if it is a standard script
python app.py


🧪 Testing

To run the automated tests included in the project:

python -m pytest test_app.py


🧠 How It Works

Query: The user asks a question (e.g., "What is the maximum height for a residential building in zone R-1?").

Retrieval: The app queries the local chroma_db to find the most relevant chunks of text from the zoning documents.

Augmentation: The retrieved text is combined with the user's question and the instructions in prompt.py.

Generation: The prompt is sent to the LLM, which synthesizes the answer based only on the provided zoning context.
