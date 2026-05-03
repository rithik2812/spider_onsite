# Multi-Project Portfolio - Chess Engine and PDF Data Extraction System

## Overview

This repository contains two independent projects:

1. Chess Game Engine (Web-Based)
2. PDF Data Extraction and Pattern Recognition Tool

Both projects demonstrate backend logic implementation, system design, and practical problem-solving using different technologies.

---

# Project 1: Chess Game Engine

## Description

A web-based chess game implemented using ASP.NET Web Forms with a dynamic frontend.  
The system supports real-time gameplay, piece movement validation, and rule enforcement.

---

## Features

- Interactive chessboard UI using HTML, CSS, and JavaScript
- Drag-and-drop piece movement
- Server-side validation of moves
- Turn-based gameplay (White vs Black)
- Capture handling
- Rule implementation:
  - Pawn movement (including en passant)
  - Castling
  - Knight, Bishop, Rook, Queen, King movement logic
- Session-based game state management

---

## System Architecture

```
Frontend (HTML + jQuery UI)
        |
        v
AJAX Requests
        |
        v
ASP.NET Backend (C#)
        |
        v
Game Logic Engine
        |
        v
Session State Storage
```

---

## Core Logic

### Move Validation

- Each piece type has specific movement rules
- Path clearance is checked for linear pieces
- Special rules implemented:
  - En Passant
  - Castling

### Game State

- Stored in server session
- Includes:
  - Active pieces
  - Captured pieces
  - Current turn

---

## Technology Stack

- ASP.NET Web Forms
- C#
- JavaScript
- jQuery UI
- AJAX

---

## How to Run

1. Open project in Visual Studio
2. Restore NuGet packages
3. Run using IIS Express
4. Open browser:
```
https://localhost:<port>/GameBoard.aspx
```

---

## Limitations

- No AI opponent
- No check/checkmate detection
- No move history
- No multiplayer support

---

# Project 2: PDF Data Extraction and Pattern Recognition

## Description

A Python-based tool that extracts text from PDF documents and identifies structured patterns such as names, phone numbers, and identification numbers using regular expressions.

---

## Features

- Extracts text from PDF files using PyMuPDF
- Pattern-based data detection using regular expressions
- Identifies:
  - Names
  - Phone numbers
  - PAN numbers
  - Date of birth
  - Credit card numbers
  - Address patterns

---

## System Architecture

```
PDF File Input
        |
        v
Text Extraction (PyMuPDF)
        |
        v
Pattern Matching (Regex)
        |
        v
Structured Output (Dictionary)
```

---

## Implementation Approach

### Text Extraction

- Uses PyMuPDF (`fitz`) to read and extract text from each page

### Pattern Matching

Regular expressions are used to identify structured data:

```
Name: [A-Z][a-z]+(?:\s[A-Z][a-z]+)+
Phone: (\+91)?\d{10}
PAN: [A-Z]{5}\d{4}[A-Z]
DOB: \d{2}/\d{2}/\d{4}
```

---

## Example Output

```
{
  "Date of Birth": ["28/12/2005"],
  "Credit Card Numbers": ["6103230310098148"]
}
```

---

## Limitations

- Regex-based approach may produce noisy or repeated results
- No contextual understanding of text
- Accuracy depends on document formatting
- No filtering or post-processing implemented

---

## Future Improvements

- Apply NLP-based entity recognition
- Remove duplicate and irrelevant matches
- Improve name extraction accuracy
- Add confidence scoring
- Build a user interface

---

## Technology Stack

- Python
- PyMuPDF (fitz)
- Regular Expressions (re)

---

## How to Run

1. Install dependencies

```
pip install pymupdf
```

2. Run the script

```
python script.py
```

3. Provide PDF file path when prompted

---

## Project Classification

Chess Game:
- Full-stack web application
- Backend logic implementation
- Rule-based system

PDF Extraction Tool:
- Data processing application
- Text extraction and pattern matching
- Rule-based information retrieval system

