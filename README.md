# IITM Assignment API

An API designed to automatically solve graded assignment questions for the IIT Madras Online Degree in Data Science.

## Getting Started

Follow these steps to set up and run the API:

1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```
2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   ```
3. **Activate the virtual environment**:
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - MacOS/Linux:
     ```bash
     source venv/bin/activate
     ```
4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
5. **Set up authentication**:
   - Create a `.env` file in the project root and add your API Proxy token:
     ```
     AIPROXY_TOKEN=your_token_here
     ```
6. **Run the API server**:
   ```bash
   uvicorn app.main:app --reload
   ```

## How to Use

The API provides a simple way to submit assignment questions and receive answers. You can send a POST request to the `/api/` endpoint with the following parameters:

- **`question`** (required): The assignment question
- **`file`** (optional): A file attachment if needed to solve the question

### Example Request

Using `curl`:
```bash
curl -X POST "http://localhost:8000/api/" \
  -H "Content-Type: multipart/form-data" \
  -F "question=Download and unzip file abcd.zip which has a single extract.csv file inside. What is the value in the 'answer' column of the CSV file?" \
  -F "file=@abcd.zip"
```

### Example Response
```json
{
  "answer": "1234567890"
}
```

## License

This project is open-source and licensed under the MIT License. See the `LICENSE` file for more details.


