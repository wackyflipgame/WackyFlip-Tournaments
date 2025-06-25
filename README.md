# 🏆 WackyFlip-Tournaments

Event & Tournament System
Backend and frontend modules for powering competitive gameplay — including time-limited events, seasonal ladders, real-time brackets, and player rewards in the Wacky Flip universe.

---

## 📋 Overview

`WackyFlip-Tournaments` enables the **creation, scheduling, tracking, and display of competitive tournaments** across all Wacky Flip games. Whether it’s a weekend event, daily challenge, or ranked ladder season, this system provides a unified infrastructure for competitive gameplay and player progression.

This repo manages both backend logic and UI components used on [WackyFlip.com](https://wackyflip.com) and mobile clients to promote, update, and conclude tournaments.

---

## 🎯 Features

* 🗓️ **Event Scheduling Engine**
  Create recurring or one-time events with specific start and end times and game modes.

* 🥇 **Leaderboard Linking**
  Attach live leaderboards to each tournament, filtered by score type or difficulty.

* 🏁 **Bracket & Ladder Formats**
  Support for elimination brackets, point ladders, and time trials.

* 🎁 **Reward Distribution System**
  Automatically assign in-game rewards or badges to top performers upon the completion of events.

* 🎨 **UI Widgets for Web & Mobile**
  Reusable components to display active events, countdowns, rules, and rankings.

* 🔒 **Secure Result Validation**
  Validates score submissions against tournament constraints and anti-cheat checks.

---

## 🧱 Tech Stack

* **Node.js + Express** – Tournament backend API
* **MongoDB** – Tournament metadata, player signups, results
* **Redis** – Caching active brackets and time-sensitive operations
* **Socket.io** – Real-time updates for brackets and countdown timers
* **React + Tailwind** – UI components used on WackyFlip-Web
* **JWT / OAuth** – Secure player registration and submission flow

---

## 🗂️ Directory Structure

```
WackyFlip-Tournaments/
├── backend/
│   ├── routes/            # Tournament APIs (create, join, results)
│   ├── models/            # MongoDB schemas (Tournament, PlayerEntry, Reward)
│   ├── services/          # Business logic (scoring, status updates)
│   └── utils/             # Time parsing, validation, reward calculators
├── frontend/
│   ├── components/        # React tournament widgets
│   ├── pages/             # Event landing page views
│   └── hooks/             # Live countdowns, bracket updates
├── scheduler/             # Cron jobs for event start/end tasks
├── tests/                 # Unit and integration tests
├── .env.example           # Environment template
├── README.md
└── LICENSE
```

---

## 📣 Key API Endpoints

| Method | Endpoint                   | Description                            |
| ------ | -------------------------- | -------------------------------------- |
| GET    | `/api/tournaments/active`  | List active or upcoming events         |
| POST   | `/api/tournaments/join`    | Player joins an event (auth required)  |
| POST   | `/api/tournaments/submit`  | Submit event score (auth + validation) |
| GET    | `/api/tournaments/:id`     | Tournament details, rules, rewards     |
| GET    | `/api/tournaments/history` | Past event summaries and winners       |

---

## 🧪 Example Use Cases

* 🥇 **Weekly Challenge**
  All players compete in "Noob Flip" for the highest combo in 72 hours.

* 🧗 **Parkour Cup**
  Bracket-style head-to-head parkour challenges with real-time elimination.

* 🧨 **Timed Survival Events**
  Players aim to last the longest in chaos-based mini-games like “Ragdoll Playground.”

---

## 💻 Frontend Widget Example

```jsx
<TournamentCard
  title="Flip Cup Weekend"
  countdown={eventEndTime}
  description="Land the craziest flips and climb the leaderboard!"
  onJoin={() => joinTournament(id)}
/>
```

Styled using TailwindCSS and integrated into both [`WackyFlip-Web`](https://github.com/wackyflipgame/WackyFlip-Web) and [`WackyFlip-Mobile`](https://github.com/wackyflipgame/WackyFlip-Mobile).

---

## 🧩 Integration Targets

* \[`WackyFlip-API`] – For user stats and score validation
* \[`WackyFlip-Stats`] – Stores historical results and analytics
* \[`WackyFlip-Locale`] – Multilingual support for event content
* \[`WackyFlip-Auth`] – Player registration and eligibility checks

---

## 🤝 Contributing

Want to build a new tournament format or improve the UI for event pages? We welcome PRs!

1. Fork the repo
2. Create a feature branch (`feature/double-elim`, `fix/date-parser`)
3. Submit a pull request

> See `CONTRIBUTING.md` for guidelines.

---

## 📜 License

MIT License © Wacky Flip Studios
