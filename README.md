# ETL Script for Extracting Data from `/etc/passwd`

This script performs an **ETL (Extract, Transform, Load)** process using the `/etc/passwd` file and a PostgreSQL database.

## Steps Overview:

1. **Extract**: Extracts the user name, user ID, and home directory from the `/etc/passwd` file.
2. **Transform**: Transforms the extracted data by replacing `:` with `,`.
3. **Load**: Loads the transformed data into a PostgreSQL database table.

### Extract Phase

- The script extracts the following columns from `/etc/passwd`:
  - **User Name** (Column 1)
  - **User ID** (Column 3)
  - **Home Directory** (Column 6)
  
```bash
cut -d":" -f1,3,6 /etc/passwd > extracted-data.txt
