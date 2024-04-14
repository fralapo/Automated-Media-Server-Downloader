# Setup Guide

This comprehensive guide will help you set up a media server environment using qBittorrent, Sonarr, Radarr, and Prowlarr on a Windows system. This guide covers both the Winget installation and manual installation methods.

## Prerequisites

Before beginning, if you prefer to install software using Winget, ensure that Winget is installed on your system. Follow these instructions to install Winget: [Winget Installation](https://github.com/microsoft/winget-cli). If you cannot or choose not to use Winget, manual installation links are provided.

## Installation

### Using Winget

If you are using Winget, open your command prompt or PowerShell and execute the following commands to install the necessary software:

```sh
winget install -e --id TeamSonarr.Sonarr
winget install -e --id TeamRadarr.Radarr
winget install -e --id TeamProwlarr.Prowlarr
winget install -e --id qBittorrent.qBittorrent
```

### Manual Installation

For manual installation, download and install each program from their respective official websites:

- [Sonarr](https://sonarr.tv/)
- [Radarr](https://radarr.video/)
- [Prowlarr](https://prowlarr.com/)
- [qBittorrent](https://www.qbittorrent.org/)

Follow the installation instructions provided on their websites.

## Auto-Startup Configuration

To have these programs start automatically with Windows:
- Open the Startup folder by typing `start shell:startup` in PowerShell or navigate to `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup` in File Explorer.
- Place shortcuts to the executable files of the installed programs in this directory.

## Create Media Directories

Use the following commands in Command Prompt or PowerShell to create directories for your media files:

- Command Prompt:
  ```cmd
  mkdir "%SystemDrive%\Media\Downloads" "%SystemDrive%\Media\TV Shows" "%SystemDrive%\Media\Movies"
  ```

- PowerShell:
  ```powershell
  New-Item -ItemType Directory -Path "$env:SystemDrive\Media\Downloads", "$env:SystemDrive\Media\TV Shows", "$env:SystemDrive\Media\Movies" -Force
  ```

## Configuration of Applications

- **qBittorrent:**
  Open qBittorrent, go to `Tools > Options`. Under the `Downloads` section, set the default save path to `%SystemDrive%\Media\Downloads`. Enable the Web UI in the `Web UI` section and set up a username and password.

- **Prowlarr:**
  Set up your preferred indexers in Prowlarr, then link Radarr and Sonarr by navigating to the `Apps` menu and inputting the API key found in `Settings > General` of each program.

- **Radarr and Sonarr:**
  Go to `Settings > Download Clients` and add qBittorrent as a client. Then use `Radarr > Movies > Library > Import` and `Sonarr > Series > Library > Import` to set up directories for automatic file management and renaming according to your settings in `Settings > Media Management`.

## Usage

Simply search for a movie or TV show via the respective portals of Sonarr and Radarr. These applications will automatically handle the downloading and importing of media files into your pre-configured library directories. This seamless integration facilitates the management of your digital media collection without manual intervention.

## Media Server Setup

Choose a media server like Plex, Jellyfin, or Emby to import and manage your TV shows and movies library. Configuration for automatic downloads via watchlists will vary depending on the media server or third-party tracking service used.

## Final Notes

This setup enables you to efficiently manage and streamline your digital media management process, allowing for easy search and automatic handling of media files through the specified applications.
