# 🎥 yt-dlp CLI Cheatsheet

A personal reference guide for using [`yt-dlp`](https://github.com/yt-dlp/yt-dlp), a powerful YouTube downloader that works from the command line. Below are commonly used commands for downloading videos, audio, playlists, and more.

## 🎧 Audio Only (MP3)

```bash
yt-dlp -x --audio-format mp3 "https://www.youtube.com/watch?v=VIDEO_ID"

	• -x: Extract audio
	• --audio-format mp3: Convert to MP3 (requires ffmpeg)


💾 Custom File Name

yt-dlp -o "%(title)s.%(ext)s" "https://www.youtube.com/watch?v=VIDEO_ID"

	• -o: Output template
	• %(title)s.%(ext)s: Saves as “Video Title.mp4”


📺 Specific Resolution (e.g. 720p Max)

yt-dlp -f "bestvideo[height<=720]+bestaudio/best[height<=720]" "https://www.youtube.com/watch?v=VIDEO_ID"

	• -f: Format selector
	• Combines best video and best audio under 720p

📁 Save to Specific Directory

yt-dlp -P ~/Downloads/videos "https://www.youtube.com/watch?v=VIDEO_ID"

	• -P: Output path
	• Saves to the specified folder


📜 Download Full Playlist

yt-dlp -i --yes-playlist "https://www.youtube.com/playlist?list=YOUR_PLAYLIST_ID"

	• -i: Ignore download errors
	• --yes-playlist: Confirms full playlist download


✅ Default: Download Best Quality

yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"

	• Downloads the best available video + audio
	• Merges automatically

⚙️ Bash Script Notes
	• Save commands in a .sh file, e.g. download.sh
	• Add this to the top of your script:
		#!/usr/bin/env bash
	• Make it executable:
		chmod +x download.sh
	• Run it with:
		./download.sh

📦 Requirements
	• yt-dlp
	• ffmpeg (for audio conversion and merging)


🔒 Disclaimer

Use yt-dlp responsibly. Respect content creators’ rights and YouTube’s Terms of Service.

