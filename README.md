# 🥔 Potato Tracker

A smart calorie tracking app that distributes your daily calorie budget across your eating hours, helping you understand exactly how many calories you can consume at any point in the day.

## 🎯 Core Concept

Unlike traditional calorie trackers that just show a daily total, Potato Tracker calculates your **hourly calorie budget** based on the current time within your eating window. This helps you pace your eating throughout the day and avoid front-loading or back-loading calories.

---

## ✨ Features

### 📊 BMR & Goal Calculator
- Calculate your Basal Metabolic Rate (BMR) from:
  - Weight, height, age, gender
  - Activity level (sedentary to extremely active)
- Set calorie deficit as percentage or flat amount
- Define your eating window (start/end hours)

### ⏰ Hourly Budget System
- Real-time tracking of calories budgeted by current hour
- Visual progress bar showing consumption vs. goal
- Display of:
  - **Budgeted**: Calories allocated up to current hour
  - **Net Consumed**: Food calories minus exercise
  - **Remaining**: How many calories left in budget

### 🍽️ Feed Logging
- Log meals with:
  - Calories
  - Time (optional, defaults to now)
  - Notes (meal description)
- Quick-add buttons: +100, +200, +500 calories
- Edit and delete any feed entry
- View all feeds for the current day

### 🧮 Calorie Calculator
- Build a **food library** with:
  - Food name
  - Calories per serving
  - Serving size (grams)
- Calculate meal totals:
  - Select foods from your library
  - Enter actual grams consumed
  - Auto-calculates total calories
  - One-click apply to feed log
- Foods persist in localStorage for reuse

### 💪 Exercise Tracking
- Log exercise with calories burned
- Exercise calories **subtract from net consumption**
- Quick-add buttons: 100, 200, 300 calories
- Edit and delete exercise entries
- Activity notes for each entry

### ⚖️ Weight Progress
- **Monday weigh-ins** with automatic reminders
- Weight changes **auto-update BMR** and recalculate daily goal
- Beautiful **line chart** showing weight trend over time
- Stats display:
  - Current weight
  - Starting weight
  - Total change
- Edit and delete weight entries
- Auto-adjusts settings when most recent weight is edited

### 📅 History Calendar
- **Heatmap calendar view** of all tracked days
- Color coding:
  - 🟢 **Green**: Success (under goal)
  - 🔴 **Red**: Over goal
  - 🔵 **Blue border**: Today
  - ⚪ **White**: No data
- Click any day to view detailed stats modal:
  - Food consumed
  - Exercise burned
  - Net calories
  - Daily goal
  - Difference from goal

### 📈 Stats & Streaks
- 🔥 **Daily streak counter**: Consecutive successful days
- 📊 **7-day rolling statistics**:
  - Average net calories
  - Average remaining calories
  - Success rate (days under goal / total days)

---

## 💾 Data Storage

All data persists locally in your browser using `localStorage`:
- ⚙️ Settings (BMR, goal, eating hours, personal info)
- 🍽️ Daily feeds
- 💪 Daily exercise
- 📜 Historical data
- ⚖️ Weight entries
- 🥘 Saved food library

---

## 🧠 Key Logic

### Calorie Calculations
- Net Calories = Food Consumed - Exercise Burned
- Success = Net Calories ≤ Daily Goal
- Hourly Budget = (Hours Passed / Total Eating Hours) × Daily Goal

### Weight Updates
When you log a new weight:
1. Updates current weight in settings
2. Recalculates BMR with new weight
3. Maintains same **deficit percentage**
4. Adjusts daily goal accordingly

### Daily Rollover
At midnight:
1. Saves previous day's data to history
2. Records: total food, exercise, goal, success/failure
3. Resets feeds and exercise for new day

---

## 🎨 Design Principles

- **Clean, colorful UI** with gradient backgrounds
- **Visual feedback** with color-coded cards (green/red/blue/purple)
- **Quick actions** for common tasks (quick-add buttons)
- **Mobile-responsive** design
- **No external dependencies** except React and Tailwind

---

## 🚀 Getting Started

1. Open the app
2. Complete initial setup:
   - Enter your weight, height, age, gender
   - Select activity level
   - Set calorie deficit
   - Define eating window hours
3. Start logging feeds and exercise
4. Track your progress on the calendar
5. Weigh in every Monday to update your BMR

---

## 🛠️ Tech Stack

- **React** (via CDN)
- **Tailwind CSS** (via CDN)
- **Babel Standalone** (for JSX)
- **localStorage API** for data persistence
- **Vanilla JavaScript** for calculations and logic

---

## 📝 Notes

- This is a **single-file HTML application** - everything runs in the browser
- No server or database required
- Data is stored locally and never leaves your device
- Works offline after initial load

---

**Built with 🥔 for potato enthusiasts everywhere**
