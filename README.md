
# Machine Round Task – CSV Upload, Validation & Reporting System

## Overview

Build a **Full-Stack Web Application** that supports:

1. Uploading a CSV file (10,000+ rows)
2. Backend parsing and validating each record
3. Frontend displaying:

   * Total records
   * Total success records
   * Total failed records
   * List of failed records in a table

This round evaluates your skills in **frontend**, **backend**, **file handling**, **validation**, **performance**, and **UI implementation**.

---

# Functional Requirements

## Frontend

(React / Next.js / Vue — choose any framework)

### Page 1 — CSV Upload

A clean UI with:

* File input (accept only `.csv`)
* Upload button
* Loader while uploading

On submit:

* Send file to backend: `POST /api/upload`
* Show processing animation until backend responds

### Page 2 — Results Dashboard

Display:

```
Total Records: 10000
Valid (Success) Records: 8700
Invalid (Failed) Records: 1300
```

### Failed Records Table

Show each failed row with:

* Row number
* Original values
* Error messages

#### Example Table

| Row | Name | Email         | Phone      | Errors               |
| --- | ---- | ------------- | ---------- | -------------------- |
| 2   | Raj  | invalid-email | 987654321  | Invalid email format |
| 3   | Sam  | (empty)       | 9876543210 | Name is required     |

### Pagination

If failed records exceed 50 entries, implement pagination.

### Optional Features (Bonus)

* Search failed records
* Filter by error type (email errors, phone errors, etc.)
* Download failed records as CSV
* Upload progress bar

---

# Backend

(Node.js Express / Laravel / Django — choose any framework)

## Required API

### POST /api/upload

Handles:

1. Accepting the CSV file
2. Streaming CSV parsing (recommended for performance)
3. Row-by-row validation
4. Responding with processed results

---

# Validation Rules

### Name

* Required
* Minimum 2 characters

### Email

* Required
* Must be valid format (`example@domain.com`)

### Phone

* Required
* Must be exactly 10 digits
* Must contain only numbers

### Additional Custom Validation (at least one)

Examples:

* Phone must start with 6, 7, 8, or 9
* Email domain must not be disposable
* Name must not contain special characters

---

# Performance Requirements

* Must handle **10,000+ rows** efficiently
* Use streaming / chunk-based parsing
* Must not block the event loop
* No server crashes for large files

---

# Submission Requirements

### GitHub Repository

Submit with the following structure:

```
/frontend
/backend
README.md
```

### README Must Include

* Tech stack
* Setup instructions

  * How to run backend
  * How to run frontend
* API documentation
* Example responses

---
