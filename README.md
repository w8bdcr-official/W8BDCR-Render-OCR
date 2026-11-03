# W8BDCR-Render-OCR

OCR API on Render (free plan). Send a base64 image, get the text back — Bengali + English.

## How it works

Flask server (`server.py`) with OpenCV preprocessing (upscale, grayscale, denoise, threshold, line removal) and Tesseract OCR (`ben+eng`, `--oem 1 --psm 7`).

## API

`POST /ocr`

```json
{ "image": "<base64-encoded image>" }
```

Returns `{"text": "..."}`.

`GET /` returns a health check.

## Deploy

Push to Render — `render.yaml` deploys it as a Docker web service (Singapore, free plan).

## Run locally

```bash
pip install -r requirements.txt
python server.py
```

Runs on port 5000.
