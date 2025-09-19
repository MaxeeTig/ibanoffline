# IBAN & SWIFT Offline Validators

This repository contains single-page offline web applications for validating International Bank Account Numbers (IBANs) and SWIFT/BIC codes without any server or internet connection.

## Available Validators

### IBAN Validator (`iban_offline_validator.html`)
- **Offline validation**: All logic and IBAN registry data are embedded in the HTML file. No network requests are needed.
- **User-friendly interface**: Enter an IBAN and click Validate (or press Enter).
- **Detailed IBAN info**: On successful validation, the app displays:
  - Country name
  - Country code (2 chars)
  - SEPA membership (Yes/No)
  - IBAN length
  - "Account check" checkbox (checked if valid)
- **Modern, responsive design**

### SWIFT/BIC Validator (`swift_offline_validator.html`)
- **Offline validation**: All validation logic and SWIFT code database are embedded in the HTML file.
- **Format validation**: Ensures SWIFT codes follow the correct AAAA-BB-CC-DDD format
- **Database lookup**: Validates against a built-in database of SWIFT codes
- **Code details**: Shows bank code, country code, location code, and branch information
- **Auto-formatting**: Input automatically converts to uppercase and validates format
- **Modern, responsive design** with professional blue color scheme

## Usage

### IBAN Validator
1. Open `iban_offline_validator.html` in any modern web browser (Chrome, Firefox, Edge, etc.).
2. Enter an IBAN in the input field.
3. Click the **Validate** button or press **Enter**.
4. If the IBAN is valid, details about the IBAN and its country will be shown below the form.

### SWIFT/BIC Validator
1. Open `swift_offline_validator.html` in any modern web browser.
2. Enter a SWIFT/BIC code in the input field (8 or 11 characters).
3. Click the **Validate** button or press **Enter**.
4. If the code is valid, detailed information about the bank and branch will be displayed.

#### SWIFT Code Format
- **Bank Code**: 4 letters (e.g., DEUT)
- **Country Code**: 2 letters (e.g., DE)
- **Location Code**: 2 characters (letters/digits)
- **Branch Code**: 3 characters (optional, letters/digits)

#### Example SWIFT Codes
- `DEUTDEFF500` - Deutsche Bank, Germany
- `COBADEFXXX` - Commerzbank, Germany
- `CHASUS33XXX` - Chase Bank, USA
- `HSBCGB2LXXX` - HSBC, UK

## Data Sources
- **IBAN**: The IBAN registry data is based on the official IBAN Registry (`iban-registry_1.txt`), converted to a JavaScript array and embedded in the HTML file.
- **SWIFT/BIC**: The SWIFT code database contains sample codes for major banks and can be easily extended with additional codes.
- No external files or APIs are required for either validator.

## How it works

### IBAN Validation
- The app checks the IBAN format, length, and checksum according to the official IBAN validation algorithm.
- It matches the IBAN's country code and length against the embedded registry data.

### SWIFT/BIC Validation
- Validates the format using regex pattern matching for the AAAA-BB-CC-DDD structure.
- Performs database lookup against embedded SWIFT code registry.
- Validates country codes against a list of supported countries.
- Provides detailed breakdown of code components for valid entries.

## Requirements
- Any modern web browser (Chrome, Firefox, Edge, Safari, etc.)
- No installation or server required
- Works completely offline

## Files
- `iban_offline_validator.html` - IBAN validation tool
- `swift_offline_validator.html` - SWIFT/BIC validation tool
- `iban_data/` - Directory containing IBAN registry data
- `sort_codes/` - Directory containing bank sorting code data

## License
This project is provided for educational and demonstration purposes. Please check the official IBAN registry and SWIFT directory for the most up-to-date information if using for production or compliance purposes.
