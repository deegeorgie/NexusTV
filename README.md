# 📺 NEXUS TV Player

A feature-rich, cross-platform IPTV player built with Python and PyQt5, featuring intelligent channel recommendations, EPG support, recording capabilities, and a modern user interface.

![License](https://img.shields.io/badge/license-Commercial-blue)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)

![nex](https://github.com/user-attachments/assets/0a4f3d29-d794-4b31-9a58-1e847712a1ea)

## ✨ Features

### 🎬 Core Playback
- **VLC-powered streaming** - Robust playback engine supporting multiple protocols (HTTP, HTTPS, RTMP, RTSP, MMS)
- **Adaptive buffering** - Configurable network buffer (500-3000ms) for smooth streaming
- **Multiple decoder modes** - Auto, Hardware, Software decoding options
- **Fullscreen mode** - Immersive viewing experience with auto-hiding controls

### 📺 Channel Management
- **M3U playlist support** - Load channels from local files or remote URLs
- **Channel search** - Fast, intelligent search with fuzzy matching
- **Favorites system** - Star your favorite channels for quick access
- **Recent channels** - Quick access to recently watched content
- **Custom channels** - Add and edit custom channel entries
- **Channel categories** - Automatic categorization (Sports, Movies, News, Kids, etc.)

### 🤖 Smart Recommendations
- **AI-powered suggestions** - Machine learning-based channel recommendations
- **Viewing pattern analysis** - Learns from your watch history
- **Category-aware** - Suggests channels based on your preferences
- **Diversity boost** - Introduces variety to prevent echo chambers

### 📅 Electronic Program Guide (EPG)
- **XML EPG support** - Display current and upcoming programs
- **Real-time updates** - Automatic EPG data refresh
- **Program information** - Show titles, descriptions, and schedules
- **Multi-source support** - Configure custom EPG sources

### 🎥 Recording & DVR
- **Stream recording** - Record live streams to MP4 format
- **VLC transcoding** - Built-in video/audio encoding
- **Scheduled recordings** - DVR functionality for time-shifted viewing
- **Recording management** - Organize and access recorded content

### 🎨 User Interface
- **Modern design** - Clean, intuitive interface with gradient accents
- **Multiple themes** - Dark, Light, and macOS-inspired themes
- **Responsive layout** - Adaptive UI for different screen sizes
- **Toast notifications** - Non-intrusive status messages
- **Loading overlays** - Visual feedback during operations
- **Channel logos** - Automatic logo fetching and caching

### 💳 Licensing & Monetization
- **PayPal integration** - Secure payment processing
- **License management** - HMAC-signed tamper-proof licenses
- **Activation system** - Simple license key activation
- **Backend API** - Flask-based licensing server

## 🏗️ Architecture

```
iptv_app/
├── core/                    # Core business logic
│   ├── channels.py          # Channel data management
│   ├── player.py            # VLC playback engine
│   ├── playcore.py          # Enhanced playback controller
│   ├── epg_manager.py       # EPG data fetching and parsing
│   ├── recommender_new.py   # ML-based recommendation engine
│   ├── search_engine.py     # Intelligent search functionality
│   ├── logo_manager.py      # Channel logo management
│   ├── dvr_manager.py       # Recording and DVR features
│   ├── settings.py          # Settings persistence
│   ├── config.py            # Application configuration
│   └── logger.py            # Logging infrastructure
│
├── ui/                      # User interface components
│   ├── main_window.py       # Main application window
│   ├── video_player.py      # Video playback widget
│   ├── channel_list.py      # Channel list view
│   ├── channel_delegate.py  # Custom channel rendering
│   ├── recommendation_panel.py  # Smart recommendations UI
│   ├── preferences_dialog.py    # Settings dialog
│   ├── search_widget.py     # Search interface
│   ├── overlay.py           # Loading/error overlays
│   ├── toast.py             # Toast notifications
│   ├── theme.py             # Theme management
│   ├── splash_screen.py     # Startup splash screen
│   └── menu_manager.py      # Application menus
│
├── backend/                 # Licensing backend (Flask)
│   ├── app/                 # Flask application
│   ├── scripts/             # Deployment scripts
│   ├── requirements.txt     # Backend dependencies
│   ├── run.py               # Backend entry point
│   └── README.md            # Backend documentation
│
├── assets/                  # Static resources
│   ├── app_icon.png         # Application icon
│   ├── no_signal.png        # Placeholder image
│   └── star_fav.png         # Favorite icon
│
├── themes/                  # UI themes
│   ├── dark.qss             # Dark theme stylesheet
│   ├── light.qss            # Light theme stylesheet
│   └── macos.qss            # macOS-inspired theme
│
├── resources/               # Runtime resources
│   └── logos/               # Cached channel logos
│
├── tools/                   # Utility scripts
│   └── cleanup_logos.py     # Logo cache maintenance
│
├── run.py                   # Application entry point
└── build_exe.bat            # Windows executable builder
```

## 🚀 Installation

### Prerequisites

- **Python 3.8+** - [Download Python](https://www.python.org/downloads/)
- **VLC Media Player** - [Download VLC](https://www.videolan.org/vlc/)
- **Git** (optional) - For cloning the repository

### System Requirements

- **OS**: Windows 10/11, Linux (Ubuntu 20.04+), macOS 10.14+
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 500MB for application + space for recordings
- **Network**: Broadband internet connection for streaming

### Step 1: Clone or Download

```bash
git clone https://github.com/yourusername/iptv_app.git
cd iptv_app
```

Or download and extract the ZIP file.

### Step 2: Install Python Dependencies

```bash
pip install -r requirements.txt
```

**Required packages:**
- PyQt5 >= 5.15.0
- python-vlc >= 3.0.0
- requests >= 2.31.0
- Pillow >= 10.0.0

### Step 3: Install VLC Media Player

**Windows:**
```bash
# Download from https://www.videolan.org/vlc/
# Install to default location (C:\Program Files\VideoLAN\VLC)
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install vlc libvlc-dev
```

**macOS:**
```bash
brew install --cask vlc
```

### Step 4: Run the Application

```bash
python run.py
```

## 🎮 Usage

### First Launch

1. **License Activation** - Enter your license key (or purchase one)
2. **Playlist Setup** - Load an M3U playlist (File → Load Playlist)
3. **EPG Configuration** (Optional) - Set EPG source in Preferences
4. **Theme Selection** - Choose your preferred theme (Dark/Light)

### Basic Operations

#### Playing Channels
- **Double-click** a channel in the list to start playback
- Use **arrow keys** to navigate channels
- Press **Enter** to play selected channel
- Press **F** for fullscreen mode
- Press **Esc** to exit fullscreen

#### Search
- Press **Ctrl+F** or click the search icon
- Type channel name or keywords
- Results update in real-time
- Press **Esc** to clear search

#### Favorites
- Click the **star icon** next to a channel to favorite
- Toggle **Favorites** button to show only favorites
- Favorites persist across sessions

#### Volume Control
- Use **mouse wheel** on volume slider
- Press **M** to mute/unmute
- Volume level saved automatically

#### Recording
- Click **Record** button to start recording current channel
- Recording saved to `~/iptv_recordings/`
- Click **Stop** to end recording
- Recordings in MP4 format with H.264/AAC encoding

### Advanced Features

#### Custom Playlists
```python
# Add custom channels via UI or edit channels.json
{
  "name": "My Channel",
  "url": "https://example.com/stream.m3u8",
  "logo": "https://example.com/logo.png",
  "group": "Entertainment"
}
```

#### EPG Configuration
1. Open **Preferences** (Ctrl+P)
2. Set EPG source URL (XMLTV format)
3. EPG data refreshes automatically
4. View program info in channel list

#### Keyboard Shortcuts
| Shortcut | Action |
|----------|--------|
| `Space` | Play/Pause |
| `F` | Fullscreen |
| `Esc` | Exit fullscreen |
| `Ctrl+F` | Search |
| `Ctrl+P` | Preferences |
| `Ctrl+R` | Reload playlist |
| `F5` | Refresh channels |
| `M` | Mute/Unmute |
| `↑/↓` | Navigate channels |
| `Enter` | Play selected |

## ⚙️ Configuration

### Settings File
Settings stored in `core/settings.json`:

```json
{
  "theme": "Dark",
  "buffer_ms": 1500,
  "decoder_mode": "Auto",
  "epg_source": "https://iptv-org.github.io/epg/index.xml",
  "favorites": ["channel_id_1", "channel_id_2"],
  "recent_channels": [],
  "last_channel": "channel_name",
  "volume": 80
}
```

### Environment Variables
```bash
# Cache directory
IPTV_CACHE_DIR=~/.iptv_cache

# Recordings directory
IPTV_RECORDINGS_DIR=~/iptv_recordings

# Log level
IPTV_LOG_LEVEL=INFO
```

## 🔧 Backend Setup (Optional)

The licensing backend is optional for personal use. For commercial deployment:

### 1. Setup Backend Environment

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 2. Configure Environment

```bash
cp .env.example .env
# Edit .env with your PayPal credentials
```

### 3. Generate Signing Key

```bash
python -c "from app.utils.license import generate_signing_key; print(generate_signing_key())"
# Add output to .env as LICENSE_SIGNING_KEY
```

### 4. Run Backend

```bash
python run.py
# Server starts at http://localhost:5000
```

See [backend/README.md](backend/README.md) for detailed backend documentation.

## 🐛 Troubleshooting

### VLC Not Found
**Error:** "VLC media player is not installed"

**Solution:**
1. Install VLC from https://www.videolan.org/vlc/
2. Ensure VLC is in system PATH
3. Restart application

### Stream Won't Play
**Error:** "Stream not available"

**Solutions:**
- Check internet connection
- Verify stream URL is valid
- Increase buffer size in Preferences
- Try different decoder mode (Hardware/Software)
- Check VLC logs in `logs/app.log`

### No Channel Logos
**Issue:** Logos not displaying

**Solutions:**
- Check internet connection
- Clear logo cache: `tools/cleanup_logos.py`
- Verify logo URLs in playlist
- Check `resources/logos/` directory permissions

### Application Freezes
**Issue:** UI becomes unresponsive

**Solutions:**
- Disable translucent effects in Preferences
- Reduce buffer size
- Update graphics drivers
- Check system resources (RAM/CPU)

### License Activation Fails
**Issue:** "License key is invalid"

**Solutions:**
- Verify key is entered correctly
- Check license expiration date
- Ensure backend is running (if using online validation)
- Contact support for license issues

## 📊 Performance Optimization

### Reduce Memory Usage
- Limit recent channels history (default: 50)
- Clear logo cache periodically
- Disable EPG if not needed
- Use hardware decoding when available

### Improve Streaming Quality
- Increase buffer size (1500-3000ms)
- Use wired connection instead of WiFi
- Close bandwidth-heavy applications
- Enable hardware acceleration

### Faster Startup
- Reduce playlist size
- Disable splash screen (edit `run.py`)
- Use local playlist instead of remote URL

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Code Style
- Follow PEP 8 guidelines
- Use type hints where applicable
- Add docstrings to functions/classes
- Write unit tests for new features

## 📝 License

This project is licensed under a **Commercial License**. See [LICENSE](LICENSE) file for details.

### License Features
- ✅ Personal use allowed with valid license
- ✅ Commercial deployment requires enterprise license
- ❌ Redistribution prohibited without permission
- ❌ Reverse engineering prohibited

## 🙏 Acknowledgments

- **VLC Media Player** - Robust multimedia framework
- **PyQt5** - Powerful GUI framework
- **IPTV-Org** - Community-maintained channel lists

## 📞 Support

- **Documentation**: [Wiki](https://github.com/yourusername/iptv_app/wiki)
- **Issues**: [GitHub Issues](https://github.com/yourusername/iptv_app/issues)
- **Email**: support@nexustv.example.com
- **Discord**: [Join our community](https://discord.gg/nexustv)

## 🗺️ Roadmap

### Version 2.0 (Planned)
- [ ] Multi-language support (i18n)
- [ ] Cloud sync for favorites/settings
- [ ] Chromecast/AirPlay support
- [ ] Picture-in-Picture mode
- [ ] Parental controls
- [ ] Advanced EPG features (reminders, series recording)

### Version 2.1 (Future)
- [ ] Mobile companion app
- [ ] Web interface
- [ ] Plugin system
- [ ] Social features (watch parties)
- [ ] Advanced analytics dashboard

## 📈 Changelog

### v1.0.0 (Current)
- ✨ Initial release
- ✨ VLC-based playback engine
- ✨ Smart recommendations
- ✨ EPG support
- ✨ Recording functionality
- ✨ Multi-theme support
- ✨ PayPal licensing integration

---

**Made with ❤️ by the NEXUS TV Team**

*For the best IPTV viewing experience*
