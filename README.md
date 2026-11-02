# Pacer

An AI running analyzer that sends the user an email everyday with analyzed metrics and a plan for the next day.

## The Problem

Helping runners transform their running data, from applications like Strava, into actionable improvements. This will ideally help them achieve their running goals and save time in research. 

## How It Works

The program takes in the data from Strava every day (provided by the Strava API) in a .csv file, analyzes the metrics, and stores some meaningful results in a JSON file. This information then is saved and also sent to the HuggingFace API which then gives feedback to the user based on their past data and creates an actionable plan for the following day. The saved information (from the metrics) and the plan for the following day is then sent to the user in a scheduled email (at 11:59 pm) every day.

## Tech Stack

- **Language:** Python, Bash, JSON
- **Libraries:** pandas, requests, huggingface_hub, json
- **External tools:** Strava API, HuggingFace API, Resend API, cron, curl, jq

## Setup

Step-by-step: how does someone who just cloned your repo get it
running?

```bash
git clone https://github.com/you/your-project
cd your-project
./install.sh   # or whatever
```

## Usage

How to actually run the thing, with examples.

```bash
./backup.sh ~/Documents
```

## Roadmap

Features you haven't built yet but plan to (pull these from your
"Schedule" quadrant in the Eisenhower Matrix).

- [ ] Desktop notifications
- [ ] Multi-directory support

## Author

Sanyam Bhansali, https://github.com/Sanyam12B/Pacer-CS193_Project.