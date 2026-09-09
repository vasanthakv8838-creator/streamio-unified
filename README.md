# StreamIO Unified 🎮🎵🎥

A unified platform that seamlessly integrates **StreamIO** (streaming), **Spotify** (music), and **Roblox** (gaming) into one powerful application.

## Features

### 🎵 Spotify Integration
- Search and play tracks
- View current playing track
- Manage playlists
- Real-time music updates in streams

### 🎮 Roblox Integration
- Access user profiles and assets
- View game leaderboards
- Broadcast messages to players
- Track player statistics

### 🎥 StreamIO Integration
- Start and manage live streams
- Real-time chat functionality
- Stream analytics and metrics
- Multi-user streaming support

### 🔗 Unified Features
- Stream your Roblox gameplay with Spotify music playing in the background
- Share currently playing tracks with stream viewers
- Leaderboard integration with streaming features
- Real-time synchronization across all platforms

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Spotify Developer Account
- Roblox API Key
- StreamIO API Access

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/vasanthakv8838-creator/streamio-unified.git
cd streamio-unified
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment variables**
```bash
cp .env.example .env
```

Edit `.env` and add your API credentials:
```
SPOTIFY_CLIENT_ID=your_spotify_client_id
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret
SPOTIFY_REDIRECT_URI=http://localhost:3000/callback
ROBLOX_API_KEY=your_roblox_api_key
ROBLOX_UNIVERSE_ID=your_roblox_universe_id
STREAMIO_API_KEY=your_streamio_api_key
STREAMIO_API_URL=https://api.streamio.com
PORT=3000
JWT_SECRET=your_jwt_secret_key
```

## Usage

### Development Mode
```bash
npm run dev
```

### Production Mode
```bash
npm run build
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `GET /api/auth/spotify/callback` - Spotify OAuth callback
- `POST /api/auth/logout` - User logout

### Spotify
- `GET /api/spotify/current-track` - Get currently playing track
- `GET /api/spotify/playlists` - Get user playlists
- `GET /api/spotify/search?q=query` - Search tracks
- `POST /api/spotify/play` - Play a track

### Roblox
- `GET /api/roblox/user/:userId` - Get user info
- `GET /api/roblox/game/:placeId` - Get game data
- `GET /api/roblox/assets/:userId` - Get user assets
- `GET /api/roblox/leaderboard?limit=10` - Get leaderboard
- `POST /api/roblox/broadcast` - Broadcast message

### StreamIO
- `GET /api/streamio/streams` - Get active streams
- `POST /api/streamio/streams/start` - Start a stream
- `POST /api/streamio/streams/:streamId/end` - End a stream
- `GET /api/streamio/streams/:streamId/chat` - Get stream chat
- `POST /api/streamio/streams/:streamId/chat` - Send chat message
- `GET /api/streamio/streams/:streamId/analytics` - Get stream analytics

## Real-time Features

The application uses **Socket.IO** for real-time communication:

```javascript
// Join a game stream
socket.emit('join-game-stream', { roomId, userId, username });

// Update now playing track
socket.emit('now-playing', { roomId, trackData });

// Listen for updates
socket.on('track-update', (data) => {
  console.log('Now playing:', data);
});
```

## Project Structure

```
streamio-unified/
├── src/
│   ├── index.js                 # Main app entry point
│   ├── routes/
│   │   ├── auth.js             # Authentication routes
│   │   ├── spotify.js          # Spotify routes
│   │   ├── roblox.js           # Roblox routes
│   │   └── streamio.js         # StreamIO routes
│   ├── services/
│   │   ├── spotifyService.js   # Spotify API service
│   │   ├── robloxService.js    # Roblox API service
│   │   └── streamioService.js  # StreamIO API service
│   └── middleware/
│       └── auth.js              # Authentication middleware
├── package.json
├── .env.example
└── README.md
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues, questions, or suggestions, please open a GitHub issue.

---

**Built with ❤️ by vasanthakv8838-creator**
