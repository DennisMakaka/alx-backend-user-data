# 0x00 Personal Data - Authentication Project

## Project Title
**Personal Data Authentication Project**

## Project Description
This project is designed to handle and log Personally Identifiable Information (PII) securely. It implements various functionalities, including data obfuscation, secure password storage, and database connectivity using environment variables. The primary goal is to ensure that sensitive user data is protected while allowing for effective logging and monitoring.

## Learning Objectives
By the end of this project, you will be able to:
- Identify examples of Personally Identifiable Information (PII).
- Implement a log filter to obfuscate sensitive PII fields.
- Encrypt passwords and validate user input.
- Use environment variables for secure database authentication.

## Requirements
- **Operating System**: Ubuntu 18.04 LTS
- **Python Version**: 3.7
- **File Structure**:
  - All files must end with a newline.
  - The first line of all files should be `#!/usr/bin/env python3`.
  - A `README.md` file at the root directory is mandatory.
  - Code must follow `pycodestyle` (version 2.5).
  - All files must be executable.
  - Each module, class, and function should include documentation explaining their purpose and functionality in full sentences.
  - Type annotations are required for all functions.


## Tasks Overview
1. **Regex-ing**
   - Write a function `filter_datum` to obfuscate sensitive data fields in log messages using regex substitutions.
   - Arguments: `fields`, `redaction`, `message`, `separator`.
   - Constraints: Use `re.sub` for substitutions; function length should be under 5 lines.

2. **Log Formatter**
   - Modify the `RedactingFormatter` class to filter specified PII fields in log records.
   - Update the class to accept a list of strings (`fields`) as a constructor argument and implement the `format()` method.

3. **Create Logger**
   - Implement a `get_logger` function that returns a Logger named "user_data."
   - Configuration: Logger should log up to `logging.INFO` and not propagate messages to other loggers. Add a `StreamHandler` with `RedactingFormatter`.

4. **Connect to Secure Database**
   - Implement a `get_db` function that securely connects to a MySQL database using environment variables.
   - Environment Variables: 
     - `PERSONAL_DATA_DB_USERNAME`: default is 'root'.
     - `PERSONAL_DATA_DB_PASSWORD`: default is an empty string.
     - `PERSONAL_DATA_DB_HOST`: default is 'localhost'.
     - `PERSONAL_DATA_DB_NAME`: required.

5. **Read and Filter Data**
   - Create a `main()` function to connect to the database, retrieve data from the users table, and log each entry with filtered PII.

## Installation Instructions
1. Clone the repository.
2. Navigate to the project directory.
3. Ensure all dependencies are installed as specified in your environment setup.

## Usage
To run the application, execute the appropriate command.

## Contributing
Contributions are welcome! Please adhere to the following guidelines:
- Fork the repository and create your branch.
- Ensure your code follows the established coding style.
- Submit a pull request with a clear description of your changes.
