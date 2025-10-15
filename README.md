# 3-Sentence Text Summarizer

## Overview
A lightweight, client-side web app that fetches plain text from a URL and produces a concise 3-sentence summary. It also:
- Accepts a source via the query string: `?url=https://.../article.txt`
- Displays the passed URL on the page
- Shows the fetched “source text” and the computed 3-sentence summary (the “solved” text)
- Falls back to an embedded sample article if no URL is provided or network/CORS issues occur

The summarizer ranks sentences by word frequency (excluding stopwords) and selects the top three while preserving their original order. Everything runs in the browser—no server or external AI API is required.

License: MIT

## Setup
No build required.

- Option 1: Double-click `index.html` to open it in your browser.
- Option 2: Serve statically with any HTTP server (recommended for best cross-origin behavior), for example:
  - Python: `python3 -m http.server 8080`
  - Node (http-server): `npx http-server -p 8080`

## Usage
- Open the app and paste a direct text URL (e.g., a `.txt` file) into the input, then click “Summarize”.
- Or pass it directly via query string:
  - `index.html?url=https://example.com/article.txt`
- The page will:
  - Display the detected URL parameter (“captcha URL”).
  - Fetch and display the source text (usually within a couple of seconds).
  - Show a 3-sentence summary.
- If fetching fails (e.g., due to CORS), the app automatically tries several CORS-friendly fallbacks. If all fail, it uses the included sample text.

Notes:
- The app aims to display the detected URL and the “solved” text (summary) quickly, typically well under 15 seconds.
- For best results, provide a URL that serves plain text.

## License (MIT)
Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.