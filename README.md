# PDF RAG Chatbot

A command-line chatbot application that answers questions based on the content of PDF documents using Retrieval-Augmented Generation (RAG).

[![Demo Video](https://placeholder-for-your-demo-video.mp4)](https://placeholder-for-your-demo-video.mp4)

## Features

- Loads and processes PDF documents using Rig's PDF loader
- Chunks documents into manageable text segments
- Generates embeddings using OpenAI-compatible APIs
- Creates an in-memory vector store for efficient retrieval
- Provides an interactive command-line interface for questions
- Uses RAG to provide contextually relevant answers

## Prerequisites

- Rust toolchain (cargo, rustc)
- Ollama running locally on port 11434
- PDF documents to query

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/pdf-rag-chatbot.git
   cd pdf-rag-chatbot
   ```

2. Build the application:
   ```bash
   cargo build --release
   ```

## Usage

1. Place your PDF document as `doc.pdf` in the application directory

2. Run the application:
   ```bash
   cargo run --release
   ```

3. Once the application starts, you can ask questions about the content of the PDF documents:
   ```
   You: What is the main topic of the document?
   Assistant: [Response based on the PDF content]
   ```

## Configuration

- The application uses the `bge-m3` model for embeddings
- The language model used is `qwen3:0.6b`
- Document chunk size is set to 2000 characters

## Technical Details

The application:
1. Loads PDF documents from the specified directory
2. Splits the content into chunks of approximately 2000 characters
3. Generates embeddings for each chunk using the `bge-m3` model
4. Creates an in-memory vector store to index these embeddings
5. Initializes a RAG agent using the `qwen3:0.6b` model
6. Starts an interactive CLI for question answering

## Dependencies

- `rig`: Framework for building RAG applications
- `anyhow`: Error handling
- `serde`: Serialization/deserialization
- `tokio`: Async runtime

## Future Improvements

- Support for multiple PDF files
- Configuration via command-line arguments or config file
- Web interface
- Integration with more vector stores (Pinecone, Qdrant, etc.)
- Support for additional document formats (DOCX, TXT, etc.)

## License

[Your License Here]

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
