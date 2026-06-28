# Deloitte Australia Tech Consulting Forage Simulation

This repository contains my work from the Deloitte Australia Tech Consulting Forage virtual experience program.

## Project Overview

In this task, I worked with JSON data transformation using Python. The goal was to take input data from two different formats and convert both into one standardized output format.

This project demonstrates:

- Python scripting
- JSON data handling
- Data transformation
- Working with timestamps
- Basic unit testing
- Problem-solving with structured data

## Task Objective

The objective of this project was to:

- Read JSON files in two different source formats
- Transform each format into a common target structure
- Validate the output against the expected result using tests

## Files in This Repository

- `convert.py` - main Python script for reading and converting the JSON data
- `convert_tests.py` - unit tests for validating the conversion logic
- `data-1.json` - sample input file in format 1
- `data-2.json` - sample input file in format 2
- `data-result.json` - expected output file

## How the Code Works

The script uses two conversion functions:

### `ConvertFormat1(jsonObject)`
This function handles data where the location is stored as a single string separated by `/`.

It:
- splits the location into country, city, area, factory, and section
- maps the status and temperature fields into a nested `data` object
- keeps the original timestamp format

### `ConvertFormat2(jsonObject)`
This function handles data where the location fields are already separated.

It:
- extracts the device information
- converts the ISO timestamp into milliseconds
- maps the location and sensor values into the required output structure

### `main(jsonObject)`
This function decides which conversion logic to use based on the structure of the input JSON object.

- If the `device` field is missing, it uses **format 1**
- Otherwise, it uses **format 2**

## Testing

The project includes basic unit tests for:

- sanity checking the expected result
- converting data from format 1
- converting data from format 2

Run the tests with:

```bash
python convert_tests.py
