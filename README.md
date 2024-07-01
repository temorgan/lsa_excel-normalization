LSA Excel Normalization
A Python project using Azure Functions to process and normalize data from Excel files. This project reads Excel files from Azure Blob Storage, normalizes specific text fields using the OpenAI API, and ensures data integrity by adhering to Third Normal Form (3NF) principles.

Features
Read Excel files from Azure Blob Storage
Normalize text fields using the OpenAI API
Fill in missing IDs and handle missing values
Adhere to 3NF principles for data integrity
Iterative normalization process with four stages for progressive refinement
Setup
Clone the repository:

sh
Copy code
git clone https://github.com/temorgan/lsa_excel-normalization.git
cd lsa_excel-normalization
Create a virtual environment and activate it:

sh
Copy code
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
Install the dependencies:

sh
Copy code
pip install -r requirements.txt
Usage
Set the required environment variables:

sh
Copy code
AZURE_STORAGE_CONNECTION_STRING=<Your Azure Storage connection string>
OPENAI_API_KEY=<Your OpenAI API key>
Deploy the Azure Function and upload your Excel file to the specified Azure Blob Storage container.

Send a POST request to the Azure Function endpoint to process the Excel file.

Iterative Normalization Process
The normalization process is divided into four iterative stages, each building upon the previous one. This approach ensures a progressive refinement of the data, addressing various aspects of data normalization and contextual understanding.

Stage 1: Initial Normalization (lsa_normalize1.py)
Purpose: Initial data cleaning and standardization.

Standardize column names and data formats.
Replace null values with a standard placeholder (e.g., 'NULL').
Run the script:

sh
Copy code
python lsa_normalize1.py
Stage 2: Basic Entity Extraction and Keyword Matching (lsa_normalize2.py)
Purpose: Basic entity extraction, capitalization, and handling of NULL values.

Use basic NER to identify names and keywords.
Ensure names are capitalized.
Translate NULL values to 'None'.
Filter out self-references in notes.
Run the script:

sh
Copy code
python lsa_normalize2.py
Stage 3: Contextual Analysis and Refinement (lsa_normalize3.py)
Purpose: Contextual analysis and refinement of extracted entities.

Use advanced NER models for refined entity extraction.
Implement pattern matching and dependency parsing.
Avoid redundant categorization.
Begin analyzing relationships and context.
Run the script:

sh
Copy code
python lsa_normalize3.py
Stage 4: Advanced Contextual Understanding and Final Refinement (lsa_normalize4.py)
Purpose: Advanced contextual understanding and final refinement.

Use transformer models like BERT for deeper context understanding.
Ensure all relevant entities are consistently captured and categorized.
Implement final validation for logical consistency and completeness.
Run the script:

sh
Copy code
python lsa_normalize4.py
Observations and Progressive Refinement
To ensure the iterative process is effective, make observations and adjustments progressively. Document any issues or scenarios as they arise and update the relevant stage accordingly.

Example Workflow:
Make Observations: Identify specific issues or scenarios.
Document Issues: Note which stage the issue pertains to.
Update Code: Adjust the relevant stage to handle the issue.
Validate Changes: Run the code and verify the output.
By following this approach, you can ensure that each stage builds upon a progressively refined dataset, leading to more accurate and consistent results.

Future Work and Improvements
There are always areas for further refinement and enhancement. Some potential areas include:

Fine-tuning NER and contextual models for better accuracy.
Implementing additional pattern matching and dependency parsing techniques.
Ensuring the system can handle a wider variety of edge cases and scenarios.
Contributions and suggestions are welcome!
