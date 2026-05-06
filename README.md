# Twitch Emote Tracker - Laiys Tracker

A real-time Twitch chat tracker that detects and counts 7TV emotes, specifically tracking WW's and LL's with live leaderboards.

## Features

✦ **Real-time Chat Tracking** - Connects to any Twitch channel instantly
✦ **7TV Emote Detection** - Automatically loads global and channel-specific 7TV emotes
✦ **Live Statistics** - Running count of WW and LL detections
✦ **Leaderboards** - Top users ranked by WW and LL counts
✦ **Beautiful UI** - Dark theme optimized for streaming with Twitch colors
✦ **Responsive Design** - Works perfectly on desktop and mobile

## Tech Stack

- React 18
- Tailwind CSS
- Lucide Icons
- TMI.js (Twitch Chat)
- 7TV API

## Getting Started

### Prerequisites

- Node.js 14+
- npm or yarn

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/twitch-emote-tracker.git
   cd twitch-emote-tracker
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```
   The app will open at `http://localhost:3000`

### Building for Production

```bash
npm run build
```

This creates a production-optimized build in the `build/` directory.

## Deployment to Vercel

### Option 1: Via GitHub (Recommended)

1. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/yourusername/twitch-emote-tracker.git
   git push -u origin main
   ```

2. **Import on Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Select "Import Git Repository"
   - Choose your GitHub repository
   - Click "Import"

3. **Configure (Optional)**
   - Environment Variables: None required
   - Build Command: `npm run build`
   - Output Directory: `build`

4. **Deploy**
   - Click "Deploy"
   - Your site will be live in seconds!

### Option 2: Direct Vercel CLI

```bash
npm install -g vercel
vercel
```

Follow the prompts to deploy your project.

## Project Structure

```
twitch-emote-tracker/
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── ChatPanel.jsx
│   │   ├── ControlsPanel.jsx
│   │   ├── PromotionModal.jsx
│   │   └── StatsPanel.jsx
│   ├── app.jsx
│   ├── index.jsx
│   ├── index.css
│   └── ...
├── package.json
├── tailwind.config.js
├── postcss.config.js
└── README.md
```

## Component Guide

### App.jsx
Main component that manages:
- Twitch connection state
- Chat message buffer
- Emote detection logic
- User leaderboards
- Component orchestration

### ChatPanel.jsx
Displays live Twitch chat with:
- Real-time message updates
- User color coding
- WW/LL badge highlights
- Auto-scrolling to latest

### StatsPanel.jsx
Shows the count boxes for:
- WW emote occurrences
- LL emote occurrences

### ControlsPanel.jsx
Contains:
- Channel name input
- Connect/Disconnect buttons
- Reset stats button
- Connection status indicator

### PromotionModal.jsx
Bottom popup showing:
- Discord bot advertisement
- Features list
- Pricing information
- Call-to-action links

## How It Works

1. **User enters Twitch channel name** and clicks Connect
2. **App fetches the user ID** via Twitch Kraken API
3. **7TV emotes are loaded** (global and channel-specific)
4. **TMI.js connects** to Twitch chat
5. **Messages are analyzed** for WW/LL emote names
6. **Counts updated** and user leaderboards built
7. **Live chat displayed** with highlights for tracked emotes

## Emote Detection

The tracker detects emotes by:
1. Loading all 7TV emotes into a map
2. Checking each message word against the emote names
3. Identifying emotes containing "ww" or "ll" in the name
4. Updating counts and leaderboards in real-time

## Customization

### Change Colors
Edit the color values in:
- `tailwind.config.js` - Extend the color palette
- Component className attributes - Modify Tailwind color utilities

### Change Tracked Emotes
In `app.jsx`, modify the `detectEmotes()` function:
```javascript
if (cleanWord.toLowerCase().includes('your-emote-name')) {
  // Track this emote
}
```

### Modify Leaderboard Size
Change the `.slice(0, 14)` value in `updateTopUsers()` function.

## Troubleshooting

### Connection Issues
- Verify the channel name is correct (case-insensitive)
- Check that TMI.js is loading properly (check browser console)
- Ensure 7TV API is accessible

### Emotes Not Detecting
- Check the 7TV emote names are spelled correctly
- Verify the channel has the emotes available
- Check browser console for API errors

### Styling Issues
- Clear browser cache and rebuild: `npm run build`
- Ensure Tailwind CSS is properly configured
- Check that PostCSS is processing your CSS

## API References

- [Twitch Kraken API](https://dev.twitch.tv/docs/kraken) - User lookups
- [7TV API](https://7tv.io/docs) - Emote data
- [TMI.js](https://tmijs.com/) - Twitch chat connection

## Support

For issues or feature requests, please open a GitHub issue.

## License

MIT License - feel free to use and modify!

## Credits

Created for tracking 7TV emotes in Twitch chat.
Features Discord bot promotion modal with Zenian Bot details.
