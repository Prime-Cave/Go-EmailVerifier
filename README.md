# Go-EmailVerifier

Go-EmailVerifier is a lightweight and efficient CLI tool written in Go for verifying email domain configurations. It checks for the presence of MX, SPF, and DMARC records for a given domain and outputs the results in a structured format.

## Features

- **MX Record Check**: Verifies if the domain has valid MX (Mail Exchange) records.
- **SPF Record Check**: Checks for the presence of SPF (Sender Policy Framework) records and retrieves the SPF record.
- **DMARC Record Check**: Checks for the presence of DMARC (Domain-based Message Authentication, Reporting, and Conformance) records and retrieves the DMARC record.

## Installation

1. Clone the repository:

   ```sh
   git clone https://github.com/tomisin/emailVerifier.git
   cd emailVerifier
   ```

2. Build the project:
   ```sh
   go build -o emailVerifier
   ```

## Usage

1. Run the program:

   ```sh
   ./emailVerifier
   ```

2. Enter domain names (one per line) to check their email configurations. Press `Ctrl+D` (Linux/Mac) or `Ctrl+Z` (Windows) to stop input.

3. The output will be displayed in the following format:
   ```
   domain, hasMX, hasSPF, spfRecord, hasDMARC, dmarcRecord
   ```

### Example

Input:

```
example.com
gmail.com
```

Output:

```
domain, hasMX, hasSPF, spfRecord, hasDMARC, dmarcRecord
example.com, true, true, v=spf1 include:_spf.google.com ~all, true, v=DMARC1; p=none; rua=mailto:dmarc-reports@example.com
gmail.com, true, true, v=spf1 include:_spf.google.com ~all, true, v=DMARC1; p=quarantine; rua=mailto:dmarc-reports@gmail.com
```

## Error Handling

- If the program encounters an error while looking up records, it logs the error and continues execution for other domains.

## Prerequisites

- Go 1.24.1 or later.

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.