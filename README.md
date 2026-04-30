# Dream11 Tracker

A beautiful and interactive fantasy cricket leaderboard tracker for IPL 2026. Track your Dream11 performance, compete with friends, and climb the ranks with gamification features including levels, XP, badges, and achievements.

![Dream11 Tracker](https://img.shields.io/badge/IPL-2026-orange) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow) ![Supabase](https://img.shields.io/badge/Backend-Supabase-green)

## ✨ Features

### 🏆 Unified Ranking System
- **Weighted scoring algorithm**: 50% average points + 30% average rank + 20% consistency
- **Real-time leaderboard** with animated position changes
- **Podium visualization** for top 3 players

### 🎯 Gamification
- **XP System**: Earn/lose XP based on match performance
- **Levels**: Progress from "Useless" to "GAME MASTER"
- **Badges**: Unlock achievements like "Champion", "Podium King", "Consistency Ace"
- **Streaks**: Track win streaks and podium streaks
- **Celebrations**: Confetti animations for level-ups and achievements

### 📊 Analytics Dashboard
- **Performance metrics**: Average points, ranks, win rates, consistency scores
- **Heatmaps**: Visual representation of match-by-match performance
- **Charts**: Powered by Chart.js for detailed analytics
- **Rival tracking**: See who's closest in the rankings

### 🏏 Match Management
- **Pre-loaded IPL 2026 schedule** with all 74 matches
- **Custom matches**: Add additional tournaments or friend matches
- **Venue information** and match status tracking

### 👥 Player Management
- **Easy player addition/removal**
- **Entry tracking** per match with ranks and points
- **Bulk operations** for efficient data management

## 🚀 Quick Start

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection for Supabase backend

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/dream11-tracker.git
   cd dream11-tracker
   ```

2. **Open in browser**
   - Simply open `d11.html` in your web browser
   - No build process required!

### Setup (Optional - for custom backend)

If you want to host your own data:

1. **Create a Supabase project** at [supabase.com](https://supabase.com)

2. **Create the following tables**:

   ```sql
   -- Players table
   CREATE TABLE players (
     id SERIAL PRIMARY KEY,
     name TEXT NOT NULL,
     created_at TIMESTAMP DEFAULT NOW()
   );

   -- Custom matches table
   CREATE TABLE custom_matches (
     id SERIAL PRIMARY KEY,
     teams TEXT NOT NULL,
     match_date TEXT NOT NULL,
     venue TEXT NOT NULL,
     created_at TIMESTAMP DEFAULT NOW()
   );

   -- Entries table
   CREATE TABLE entries (
     id SERIAL PRIMARY KEY,
     match_id INTEGER NOT NULL,
     player_name TEXT NOT NULL,
     rank INTEGER,
     points DECIMAL,
     created_at TIMESTAMP DEFAULT NOW(),
     UNIQUE(match_id, player_name)
   );
   ```

3. **Update the configuration** in `d11.html`:
   ```javascript
   const SUPABASE_URL = 'your-supabase-url';
   const SUPABASE_ANON_KEY = 'your-supabase-anon-key';
   ```

## 🎮 How to Use

### Adding Players
1. Navigate to the **Players** tab
2. Click **"Add Player"**
3. Enter player names and save

### Recording Match Results
1. Go to the **Matches** tab
2. Click on any match
3. Enter ranks and points for each player
4. Data saves automatically to Supabase

### Viewing Leaderboard
- **Leaderboard** tab shows unified rankings
- **Analytics** tab provides detailed performance insights
- Rankings update in real-time with smooth animations

## 🛠️ Technologies Used

- **Frontend**: Vanilla JavaScript (ES6+), HTML5, CSS3
- **Backend**: Supabase (PostgreSQL)
- **Animations**: GSAP (GreenSock Animation Platform)
- **Charts**: Chart.js
- **Celebrations**: Canvas Confetti
- **Fonts**: Google Fonts (Outfit, JetBrains Mono)
- **Icons**: Unicode emojis and custom CSS

## 📱 Responsive Design

- **Mobile-first approach** with responsive breakpoints
- **Touch-friendly** interface for mobile devices
- **Optimized** for tablets and desktops
- **Dark theme** with beautiful gradients and glassmorphism effects

## 🎨 UI/UX Features

- **Glassmorphism design** with backdrop blur effects
- **Smooth animations** and micro-interactions
- **Color-coded rankings** (Gold, Silver, Bronze for top 3)
- **Loading states** and error handling
- **Accessible** with proper ARIA labels

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **IPL 2026 schedule** data
- **Supabase** for the amazing backend-as-a-service
- **Chart.js** for beautiful data visualizations
- **GSAP** for smooth animations
- **Canvas Confetti** for celebration effects

---

**Made with ❤️ for cricket fans and fantasy enthusiasts**

*Track your Dream11 journey and may the best fantasy team win!* 🏏✨