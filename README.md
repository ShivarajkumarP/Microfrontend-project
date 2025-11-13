# MicroFrontend Demo
# 🧩 MicroFrontend-Demo

A modular **Micro-Frontend architecture** demo project showcasing how multiple independent frontend apps (built using different frameworks like Svelte and React) can work together seamlessly under a single host.

---

## 🚀 Project Overview

This repository acts as the **parent container** for multiple microfrontend apps, each living in its own Git submodule.

| App Name       | Framework | Purpose                             |
|----------------|------------|--------------------------------------|
| **main-host**  | React     | Root shell application managing layout, routing, and loading remote apps |
| **contactform**| Svelte      | Contact form micro-frontend embedded dynamically |
| **todo-app**   | React      | Simple to-do list micro-frontend for demonstration |
| **cardcomp**   | React      | Simple card details and card short for dynamic demonstration |

---

## 📁 Repository Structure

MicroFrontend-Demo/
├── main-host/ # Parent shell (react)
├── contactform/ # svelte micro-frontend
├── cardcomponent/ # React micro-frontend
├── todo-app/ # React micro-frontend
└── .gitmodules # Git submodules configuration


Each folder is its own Git repository (added as a submodule).

---

## 🛠️ Setup Instructions

### 1. Clone the parent repository with all submodules

```bash
git clone --recurse-submodules https://github.com/YOUR_USERNAME/MicroFrontend-Demo.git
cd MicroFrontend-Demo
🧠 Tip: If you already cloned without --recurse-submodules, run:
git submodule update --init --recursive

▶️ Running Each App Locally

Each microfrontend runs independently — open a new terminal for each.

Default dev server: http://localhost:3000

1️⃣ Main Host (React)
cd main-host
npm install
npm run start


Default dev server: http://localhost:3003

2️⃣ Contact Form App (Svelte)
cd contactform
npm install
npm start


Default dev server: http://localhost:3002

3️⃣ Todo App (React)
cd todo-app
npm install
npm start


Default dev server: http://localhost:3001

3️⃣ Card Component (React)
cd card-details
npm install
npm start

🔗 Microfrontend Integration

The Main Host dynamically loads and mounts the Contact Form and Todo App via module federation (Webpack).

Each app can be developed, tested, and deployed independently.

The host manages shared dependencies and orchestrates runtime communication between apps.

🧪 Running Tests

Each submodule may include its own Jest test suite.

Example (inside any sub-app):

cd main-host
npm test

🔄 Updating Submodules

When a submodule gets updates (for example, you pushed new commits in contactform):

git submodule update --remote
git add contactform
git commit -m "Update contactform to latest version"
git push

🧹 Common Commands
Command	Description
git submodule update --init --recursive	Initialize and fetch all submodules
git submodule foreach git pull origin main	Pull latest for all submodules
git add <submodule>	Stage updated submodule reference
git rm -f <submodule>	Remove a submodule
🧠 Notes for QA / Seminar

Ensure all apps are running locally before testing the host.

Main host should automatically detect microfrontends when started.

You can stop individual apps without breaking others (isolation demo).

Useful for explaining modular architecture, deployment independence, and scalability.

📜 License

 © 2025 [Shivarajkumar / DevCanSol]
 