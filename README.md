# IBAN Offline Validator

This is a single-page offline web application for validating International Bank Account Numbers (IBANs) without any server or internet connection.

## Features
- **Offline validation**: All logic and IBAN registry data are embedded in the HTML file. No network requests are needed.
- **User-friendly interface**: Enter an IBAN and click Validate (or press Enter).
- **Detailed IBAN info**: On successful validation, the app displays:
  - Country name
  - Country code (2 chars)
  - SEPA membership (Yes/No)
  - IBAN length
  - "Account check" checkbox (checked if valid)
- **Modern, responsive design**

## Usage
1. Open `iban_offline_validator_v2.html` in any modern web browser (Chrome, Firefox, Edge, etc.).
2. Enter an IBAN in the input field.
3. Click the **Validate** button or press **Enter**.
4. If the IBAN is valid, details about the IBAN and its country will be shown below the form.

## Data Source
- The IBAN registry data is based on the official IBAN Registry (`iban-registry_1.txt`), converted to a JavaScript array and embedded in the HTML file.
- No external files or APIs are required.

## How it works
- The app checks the IBAN format, length, and checksum according to the official IBAN validation algorithm.
- It matches the IBAN's country code and length against the embedded registry data.

## Requirements
- Any modern web browser.
- No installation or server required.

## License
This project is provided for educational and demonstration purposes. Please check the official IBAN registry for the most up-to-date information if using for production or compliance purposes.
