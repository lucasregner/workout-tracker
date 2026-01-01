# Workout Tracker

Personal workout tracker with optimized Google Sheets sync. Built with React.

## ✨ Features

### Core Functionality
- ✅ 3 customizable workouts (A, B, C) - 2 home workouts, 1 gym workout
- ✅ Smart progression tracking with 3-session system for dumbbells
- ✅ Reverse progression for dumbbells (strongest on last set)
- ✅ Rest timer with visual countdown and vibration
- ✅ Plate calculator for barbell exercises
- ✅ Mobile-optimized PWA (install to home screen)

### Data & Sync
- ✅ **Optimized Google Sheets sync** - only 3 API calls per workout (vs 40+ before)
- ✅ **Auto-loads weights from Sheets** on startup - works across devices
- ✅ Offline-first with localStorage backup
- ✅ Manual "Reload from Sheets" button
- ✅ Timestamps on last workout dates (e.g., "Jan 1, 3:45 PM")

### Tracking
- ✅ Session progress tracking during workout
- ✅ Complete workout history in Google Sheets
- ✅ Weight progression automatically calculated
- ✅ Failed set tracking

## 🚀 Deployment

### Quick Deploy to Netlify

1. **Fork or clone this repository**
2. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Choose GitHub and select this repository
   - Build settings:
     - Build command: (leave empty)
     - Publish directory: `/`
   - Click "Deploy site"

3. **Your app will be live!**
   - You'll get a URL like `https://your-app-name.netlify.app`
   - Customize the domain in Netlify settings

### Required Setup

Before using the app, you need:

1. **Google Sheet** with these tabs:
   - `Workout Log` - All your set-by-set history
   - `Current Weights` - Your current weight for each exercise
   - `Workout History` - Summary of completed workouts

2. **SheetDB Account** (free tier works great):
   - Sign up at [sheetdb.io](https://sheetdb.io)
   - Connect your Google Sheet
   - Copy your API URL
   - Update `SHEETDB_API` in `index.html` with your URL

## 📱 Usage

### First Time Setup
1. Open the app
2. Click "Setup Weights"
3. Enter your starting weights for each exercise
4. Or click "Reload from Sheets" if you already have data

### During Workout
1. Select workout (A, B, or C)
2. Complete sets and log them with big, clear buttons:
   - ✅ Green = Completed target reps
   - ⚠️ Yellow = Partial reps (enter actual count)
   - ❌ Red = Failed set
3. Rest timer automatically starts between sets
4. Data syncs to Google Sheets when workout completes

### View Your Data
- Check your Google Sheet to see all workout history
- Cloud icon shows sync status (green = synced, blue = syncing, red = error)
- Timestamps show when you last did each workout

## 💪 Workout Structure

### Workout A - Home (Dumbbells, 3x8)
Progressive resistance with 5 lbs increments
- Dumbbell Chest Press (Flat)
- Standing Row
- Bulgarian Split Squats
- Squats with Overhead Press

### Workout B - Gym (Barbell, 5x5)
Heavy compound lifts with 5 kg increments
- Barbell Squats
- Barbell Deadlift
- Pullups (3x8, bodyweight)

### Workout C - Home (Dumbbells, 3x8)
Isolation and accessory work with 5 lbs increments
- Dumbbell Incline Chest Press
- Biceps Curls
- Dumbbell Skull Crusher
- Standing Dumbbell Calf Raises
- Stiff Calf Jumps (bodyweight)

## 📈 Progression System

### Dumbbells (3-Session Reverse Progression)
Unique reverse progression where you're strongest on later sets:
- **Session 1**: Target 6, 7, 8 reps (building up each set)
- **Session 2**: Target 7, 8, 8 reps
- **Session 3**: Target 8, 8, 8 reps (all out!)
- **After Session 3 success**: Weight increases by 5 lbs per dumbbell → back to Session 1

### Barbells
- Complete all 5x5 → weight increases by 5 kg
- Immediate progression after successful completion

### Bodyweight (Pullups)
- Complete all 3x8 → reps increase by 1 per set
- Progressive rep increases

## 🛠️ Tech Stack

- **Frontend**: React 18 (via CDN)
- **Styling**: Tailwind CSS
- **Data Sync**: SheetDB API → Google Sheets
- **Storage**: localStorage (offline backup)
- **Hosting**: Netlify
- **PWA**: Installable on mobile devices

## 📊 API Efficiency

**Optimized batch syncing:**
- Only syncs once at the end of each workout
- 3 API calls per workout (vs 40+ with per-set syncing)
- Free tier allows ~160 workouts/month

**API Call Breakdown:**
1. POST workout log (all sets in one batch)
2. UPDATE current weights
3. POST workout summary

## 🔧 Customization

To modify exercises or progression:
1. Edit the `workouts` object in `index.html`
2. Adjust `increment` values for different weight jumps
3. Modify `getTargetReps` function for different rep schemes

## 📝 License

Personal use only.

## 🙏 Credits

Built for Lucas with assistance from Claude (Anthropic).

---

**Live Demo**: https://lambent-lily-008213.netlify.app/
