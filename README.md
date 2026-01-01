# Workout Tracker

Personal workout tracker with automatic Google Sheets sync.

## Features

- ✅ 3 customizable workouts (A, B, C)
- ✅ Smart progression tracking (3-session system for dumbbells)
- ✅ Rest timer with visual countdown
- ✅ Plate calculator for barbell exercises
- ✅ Automatic sync to Google Sheets via SheetDB
- ✅ Works offline (data stored locally)
- ✅ Mobile-optimized PWA (install on phone home screen)
- ✅ Session tracking with reverse progression for dumbbells

## Deployment

### Quick Deploy to Netlify

1. **Connect this repo to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Choose GitHub and select this repository
   - Build settings:
     - Build command: (leave empty)
     - Publish directory: `/`
   - Click "Deploy site"

2. **Your app will be live!**
   - You'll get a URL like `https://your-app-name.netlify.app`
   - You can customize the domain in Netlify settings

### Setup Required

Before using the app, make sure you have:

1. **Google Sheet** set up with these tabs:
   - "Workout Log" 
   - "Current Weights"
   - "Workout History"

2. **SheetDB API** configured:
   - Your SheetDB API URL is already configured in the code
   - URL: `https://sheetdb.io/api/v1/4zo8oj6yl9rca`

## Usage

1. **First time setup:**
   - Open the app
   - Click "Setup Weights"
   - Enter your starting weights for each exercise

2. **During workout:**
   - Select workout (A, B, or C)
   - Complete sets and log them
   - Data automatically syncs to Google Sheets

3. **View your data:**
   - Check your Google Sheet to see all workout history
   - Cloud icon shows sync status (green = synced, blue = syncing)

## Workout Structure

### Workout A - Home (Dumbbells)
- Dumbbell Chest Press (Flat) - 3x8
- Standing Row - 3x8
- Bulgarian Split Squats - 3x8
- Squats with Overhead Press - 3x8

### Workout B - Gym (Barbell)
- Barbell Squats - 5x5
- Barbell Deadlift - 5x5
- Pullups - 3x8

### Workout C - Home (Dumbbells)
- Dumbbell Incline Chest Press - 3x8
- Biceps Curls - 3x8
- Dumbbell Skull Crusher - 3x8
- Standing Dumbbell Calf Raises - 3x8
- Stiff Calf Jumps - 3x8

## Progression System

### Dumbbells (3-session progression)
- **Session 1**: Target 6, 7, 8 reps (strongest on last set)
- **Session 2**: Target 7, 8, 8 reps
- **Session 3**: Target 8, 8, 8 reps
- After completing Session 3 → weight increases by 5 lbs per dumbbell

### Barbells & Bodyweight
- Progress immediately after completing all sets

## Tech Stack

- React (via CDN)
- Tailwind CSS
- SheetDB API for Google Sheets integration
- LocalStorage for offline data persistence

## License

Personal use only
