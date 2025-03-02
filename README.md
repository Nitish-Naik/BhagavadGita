
# Bhagavad Gita Verse Scraper

This project scrapes verses from any chapter of the Bhagavad Gita from [vedabase.io](https://vedabase.io). By setting the chapter number in the `url` variable, the script will extract information for each verse in the specified chapter, including the title, Devanagari text, English translation, and synonyms. The extracted information is saved in a JSON format to a text file.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Data Structure](#data-structure)
- [File Output](#file-output)
- [Error Handling](#error-handling)
- [License](#license)

## Overview

The script uses `Selenium` to automate web scraping. It navigates through each verse in a given chapter of the Bhagavad Gita, extracts relevant details, and saves them in JSON format in a file named according to the chapter.

## Prerequisites

- Python 3.6 or higher
- Google Chrome Browser
- ChromeDriver compatible with your Chrome version
- Internet connection

## Installation

1. **Clone this repository:**
   
   git clone <repo_url>
   
2. **Install dependencies:**
   
   pip install selenium
   
3. **Download ChromeDriver:**
   - Download the [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) that matches your Chrome version.
   - Place the `chromedriver` executable in a directory included in your system PATH or in the same directory as the script.

## Usage

1. **Set the Chapter Number:**
   - Modify the `url` variable at the beginning of the script to target the desired chapter. For example, to scrape Chapter 2, set:
     python
     url = 'https://vedabase.io/en/library/bg/2/1/'
     

2. **Run the Script:**
   
   python <script_name>.py
   
3. **Extracted Data:**
   - The script will save the extracted data in a file named `Chapter-<chapter_number>.txt`.

## Data Structure

The script extracts data in the following JSON format:

json
{
    "chapter": "<chapter_number>",
    "verse": "<verse_number or verse_range>",
    "verse_text_devnagari": "<Devanagari text>",
    "verse_text_english": "<English verse text>",
    "Translation": "<English translation>",
    "Synonyms": ["<Synonym1>", "<Synonym2>", "..."]
}


## File Output

- The file `Chapter-<chapter_number>.txt` is saved in the project directory.
- Each verse is saved as a separate JSON entry, making it easier to process for further analysis or display.

## Error Handling

The script includes error handling mechanisms to manage potential issues:
- If the page structure changes or elements are not found, the script logs an error and stops further execution.
- If the "Next" button is not found on the last verse page, the script logs the error and terminates gracefully.

## Notes

- **Wait Times:** The script uses `time.sleep()` and `WebDriverWait` to ensure elements load properly before interaction. If the site is slow, you may need to adjust these wait times.
- **Flexibility:** By changing the `url` variable to reflect any chapter number, the script can be used to scrape data from any chapter.

## License

This project is licensed under the MIT License.
