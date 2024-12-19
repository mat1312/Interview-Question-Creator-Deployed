
# Interview Question Creator

An application designed to process PDF files and generate meaningful questions and answers based on the document's content. The project leverages **LangChain** and **OpenAI** models to create a seamless pipeline for document analysis and knowledge extraction.

## Features

- **Upload PDF Files**: Upload your documents for analysis.
- **Question and Answer Generation**: Automatically generates a CSV file with relevant questions and answers based on the PDF content.
- **User-Friendly Interface**: Simple endpoints for uploading and processing files.

## How to Run

1. **Set up the environment**:

    ```bash
    conda create -n interview python=3.10 -y
    conda activate interview
    ```

2. **Install dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Run the application**:

    ```bash
    uvicorn app:app --reload
    ```

    The application will be accessible at `http://127.0.0.1:8000`.

## API Endpoints

- `GET /`: Displays the homepage.
- `POST /upload`: Upload a PDF file for analysis. Returns a confirmation and saves the file.
- `POST /analyze`: Processes the uploaded file and generates a CSV with questions and answers.

## File Structure

- **`app.py`**: Main entry point for the FastAPI application.
- **`src/helper.py`**: Contains the core logic for processing PDFs and generating questions/answers using LangChain.
- **`static/`**: Stores uploaded files and generated outputs (e.g., CSV files).
- **`templates/`**: HTML templates for the web interface.

## Dependencies

- **FastAPI**: Web framework for creating APIs.
- **LangChain**: For document loading, text splitting, and question-answer pipelines.
- **OpenAI API**: For GPT-based language generation.
- **Jinja2**: For rendering HTML templates.
- **FAISS**: For vector similarity search.
- **aiofiles**: Asynchronous file operations.

## Environment Variables

Ensure you have an OpenAI API key set up in a `.env` file:

```
OPENAI_API_KEY=your_openai_api_key_here
```

## Output Example

After analyzing a PDF, the app generates a CSV file (`QA.csv`) with columns:
- **Question**: Relevant questions derived from the document.
- **Answer**: Corresponding answers based on the context.

## Future Enhancements

- Add support for other file formats (e.g., DOCX).
- Implement a graphical user interface (GUI).
- Enable multi-language support for PDFs.

## License

This project is open-source and available under the MIT License.
