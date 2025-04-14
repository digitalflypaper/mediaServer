# mediaServer

A standalone HTTP server that serves media files and provides an MRSS feed.

## Features

- Serves media files (videos, audio, images, documents) via HTTP
- Provides a Media RSS (MRSS) feed for integration with media players and podcatchers
- Simple web interface for browsing, viewing, uploading, and deleting files
- Cross-platform: runs on Linux, macOS, and Windows
- Single executable file for easy distribution and installation
- No external dependencies required

## Quick Start

1. Download the executable for your platform from the releases page
2. Create a directory to store your media files (or use an existing one)
3. Run the executable:

```
# Linux/macOS
./media-server --port 8080 --dir /path/to/media

# Windows
media-server.exe --port 8080 --dir C:\path\to\media
```

4. Open a web browser and navigate to `http://localhost:8080`





# Digital Flypaper Media Server - User Guide

This guide provides step-by-step instructions for setting up and using the Digital Flypaper Media Server, designed to be accessible for non-technical users.

## Setup Guide

### Step 1: Download the Server

1. Download the correct version for your operating system:
   - **Windows**: Download `media-server-windows-amd64.exe`
   - **macOS Intel**: Download `media-server-darwin-amd64`
   - **macOS Apple Silicon (M1/M2)**: Download `media-server-darwin-arm64`
   - **Linux**: Download `media-server-linux-amd64`

### Step 2: Create a Media Folder

1. Create a new folder where you want to store your media files.
   - **Windows**: Example: `C:\MediaServer\media`
   - **macOS/Linux**: Example: `/Users/yourname/MediaServer/media`

### Step 3: Start the Server

#### Windows:

1. Create a new text file in the same folder as the downloaded executable.
2. Open the text file and type:
   ```
   media-server-windows-amd64.exe --port 8080 --dir media
   ```
3. Save the file as `start-server.bat`
4. Double-click `start-server.bat` to start the server.

#### macOS:

1. Open Terminal (find it in Applications > Utilities > Terminal)
2. Navigate to the folder where you downloaded the server:
   ```
   cd /path/to/folder
   ```
3. Make the server executable:
   ```
   chmod +x media-server-darwin-amd64
   ```
4. Start the server:
   ```
   ./media-server-darwin-amd64 --port 8080 --dir /path/to/media/folder
   ```

#### Linux:

1. Open Terminal
2. Navigate to the folder where you downloaded the server:
   ```
   cd /path/to/folder
   ```
3. Make the server executable:
   ```
   chmod +x media-server-linux-amd64
   ```
4. Start the server:
   ```
   ./media-server-linux-amd64 --port 8080 --dir /path/to/media/folder
   ```

### Step 4: Access the Web Interface

1. Open your web browser (Chrome, Firefox, Safari, Edge, etc.)
2. Enter the following address in the address bar:
   ```
   http://localhost:8080
   ```
3. You should now see the Go Media Server web interface!

## Using the Media Server

### Uploading Files

1. From the main page, click the "Choose File" button in the upload form.
2. Navigate to and select the file you want to upload.
3. Click the "Upload File" button.
4. The file will be uploaded and appear in the file list.

### Viewing Files

1. Find the file you want to view in the file list.
2. Click the "View" button next to the file.
3. The file will open in the viewer:
   - Videos and audio will have playback controls
   - Images will be displayed
   - Other file types will have a download link

### Downloading Files

1. Find the file you want to download in the file list.
2. Click the "Download" button next to the file.
3. The file will download to your computer.

### Deleting Files

1. Find the file you want to delete in the file list.
2. Click the "Delete" button next to the file.
3. Confirm the deletion when prompted.
4. The file will be removed from the server.

### Accessing the RSS Feed

The RSS feed is available at:

```
http://localhost:8080/feed.xml
```

You can add this URL to media players that support RSS feeds, such as:
- VLC Media Player
- iTunes
- Podcast apps
- RSS readers

## Troubleshooting

### The server won't start

- Make sure you have permission to run the executable.
- Check if another program is already using port 8080. If so, choose a different port by using `--port 8081` (or any other number).
- Make sure the media directory exists and is accessible.

### Can't access the web interface

- Make sure the server is running (there should be a command window/terminal open).
- Try using `http://127.0.0.1:8080` instead of `http://localhost:8080`.
- Check if a firewall is blocking access to the port.

### Upload issues

- Check that the file you're uploading isn't too large. The default maximum size is 500MB.
- Make sure the media directory is writable.

### Sharing with other devices on your network

To access the server from other devices on your local network:

1. Find your computer's IP address:
   - **Windows**: Open Command Prompt and type `ipconfig`
   - **macOS/Linux**: Open Terminal and type `ifconfig` or `ip addr`
2. Look for your IP address (usually starts with 192.168.x.x or 10.0.x.x)
3. Start the server with your IP address:
   ```
   ./media-server --port 8080 --dir /path/to/media --url http://YOUR.IP.ADDRESS:8080
   ```
4. On other devices, open a browser and navigate to:
   ```
   http://YOUR.IP.ADDRESS:8080
   ```

## Advanced Options

When starting the server, you can use these additional options:

- `--title "My Media Collection"`: Set a custom title for the RSS feed
- `--desc "Personal collection of videos and podcasts"`: Set a custom description for the RSS feed
- `--maxsize 1000`: Set maximum upload file size to 1000MB (1GB)

Example with all options:

```
./media-server --port 8080 --dir /path/to/media --url http://example.com:8080 --title "My Media" --desc "My personal media server" --maxsize 1000
```
