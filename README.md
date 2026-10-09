# PySelenium-Bandcamp
**A Selenium-based Python script that scrapes track titles and their links from Bandcamp for a given list of artists.**

[![License](https://img.shields.io/github/license/DarkSoulEngineer/PySelenium-Bandcamp)](LICENSE)
[![Python](https://img.shields.io/badge/language-Python-3776AB)](https://www.python.org/)

## Table of Contents

- [Description](#description)
  - [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Output](#output)
- [Notes](#notes)
- [Customizable Settings](#customizable-settings)
- [License](#license)

## Description

PySelenium-Bandcamp automates the collection of track data from Bandcamp. For each artist in a user-supplied list, the script searches Bandcamp, opens album results, clicks through to the album page, and extracts the track title and page link. The collected data is written to a CSV file for later analysis.

### Features

- Scrapes track titles and their links from Bandcamp albums.
- Saves output in CSV format (`albums_data.csv`).
- Customizable list of artists via an `artists.txt` input file.
- Adjustable playback duration to simulate listening behavior.

## Requirements

- **Python 3.x**
- **Google Chrome** (latest version recommended)
- **ChromeDriver** (matching your Chrome version)
- Required Python libraries:
  - `selenium`

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/DarkSoulEngineer/PySelenium-Bandcamp.git
   cd PySelenium-Bandcamp
   ```

2. Install the necessary Python packages:

   ```bash
   pip install selenium
   ```

## Usage

1. **Prepare the input file.** Update `artists.txt` with a comma-separated list of artist names. For example:

   ```
   Radiohead,Coldplay,The Beatles
   ```

2. **Run the script:**

   ```bash
   python bandcamp.py
   ```

The script launches a Chrome browser, searches Bandcamp for each artist, and processes up to `SONGS_LIMIT` albums per artist.

## Output

A CSV file named `albums_data.csv` is generated with the scraped data, containing the artist name, track title, and track link for each processed album.

## Notes

- The script simulates song playback for a defined duration on each album page. Allow it to finish processing all songs before exiting so data is saved properly.

## Customizable Settings

You can modify these parameters at the top of `bandcamp.py`:

- `SONGS_LIMIT`: Number of albums to process per artist.
- `TIME_TO_LISTEN`: Time to "listen" to each song in seconds.
- `ARTISTS_FILE`: Name of the input file listing artists.
- `CSV_FILE`: Name of the output CSV file.

## License

GPL-3.0 — see [LICENSE](LICENSE).
