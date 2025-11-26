# Song Ratings

A simple web app for tracking and rating songs submitted by multiple people.

## Features

- 🎵 Display song ratings from multiple raters (E, M, P)
- 📊 Statistics including averages and perfect songs
- 🔄 Sortable columns (click headers to sort)
- 🔍 Filter by submitter or perfect songs
- 📱 Mobile responsive design
- 🎬 Automatic YouTube video title fetching

## How to Use

1. Clone the repository
2. Start a local server (e.g., `python3 -m http.server 8000`)
3. Open `http://localhost:8000` in your browser

## Data Format

Songs are stored in `songs.json` with the following structure:
- `id`: Unique song identifier
- `date`: Submission date (DD/MM/YYYY)
- `link`: YouTube link to the song
- `submitter`: Who submitted the song (E, M, or P)
- `E`, `M`, `P`: Ratings from each person (0-10 or null)
- `sum`: Total of all ratings
- `both_8_plus`: Whether both non-submitters rated 8 or higher

## Technologies

- Pure HTML, CSS, and JavaScript
- YouTube oEmbed API for fetching video titles
- No frameworks or dependencies required
