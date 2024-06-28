# lsa_excel-normalization
A Python project using Azure Functions to process and normalize data from Excel files. The project reads Excel files from Azure Blob Storage, normalizes specific text fields using the OpenAI API, and ensures data integrity by adhering to Third Normal Form (3NF) principles.
# Excel Normalization

A Python project using Azure Functions to process and normalize data from Excel files. This project reads Excel files from Azure Blob Storage, normalizes specific text fields using the OpenAI API, and ensures data integrity by adhering to Third Normal Form (3NF) principles.

## Features

- Read Excel files from Azure Blob Storage
- Normalize text fields using the OpenAI API
- Fill in missing IDs and handle missing values
- Adhere to 3NF principles for data integrity

## Setup

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/excel-normalization.git
    cd excel-normalization
    ```

2. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Set the required environment variables:
    ```plaintext
    AZURE_STORAGE_CONNECTION_STRING=<Your Azure Storage connection string>
    OPENAI_API_KEY=<Your OpenAI API key>
    ```

2. Deploy the Azure Function and upload your Excel file to the specified Azure Blob Storage container.

3. Send a POST request to the Azure Function endpoint to process the Excel file.

## Contributing

Feel free to open issues or submit pull requests for any improvements or bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
