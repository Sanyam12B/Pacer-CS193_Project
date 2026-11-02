# Pacer

An AI running analyzer that sends the user an email everyday with analyzed metrics and a plan for the next day.

## The Problem

Helping runners transform their running data, from applications like Strava, into actionable improvements. This will ideally help them achieve their running goals and save time in research. 

## How It Works

The program takes in the data from Strava every day (provided by the Strava API) in JSON file, analyzes the metrics, and stores some meaningful results in a JSON file. This information then is saved and also sent to the HuggingFace API which then gives feedback to the user based on their past data and creates an actionable plan for the following day. The saved information (from the metrics) and the plan for the following day is then sent to the user in a scheduled email (at 11:59 pm) every day.

## Tech Stack

- **Language:** Python, Bash, JSON
- **Libraries:** pandas, requests, huggingface_hub, json
- **External tools:** Strava API, HuggingFace API, python-dotenv, Resend API, cron, curl, jq

## Setup

Step-by-step: how does someone who just cloned your repo get it
running?

```bash
git clone https://github.com/Sanyam12B/Pacer-CS193_Project.git
cd Pacer-CS193_Project
```

Create a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

Install the required dependencies

```bash
pip install -r requirements.txt=
```

Create a .env file in the root directory and fill the following credentials

STRAVA_CLIENT_ID=
STRAVA_CLIENT_SECRET=
STRAVA_ACCESS_TOKEN=
STRAVA_REFRESH_TOKEN=
HF_TOKEN=
RESEND_API_KEY=

## Usage

Manual execution of the program (sends email instantly).

```bash
python main.py
```

Using cron to schedule the email for 11:59 pm everyday

First, run the following command to open the configurations for cron

```bash
crontab -e
```

Then store the next command in the configuration to schedule send the emails (the program runs every day at 11:59 pm).

```bash
59 23 * * * cd /path/to/Pacer && /path/to/Pacer/venv/bin/python main.py
```

Then exit vim using ":wqa" to save and exit vim. You can check your scheduled crontab tasks using the following command.

```bash
crontab -l
```

## Roadmap

Features you haven't built yet but plan to (pull these from your
"Schedule" quadrant in the Eisenhower Matrix).

- [ ] Integration of AI to create action plans for the user (using HuggingFace).
- [ ] Sending scheduled emails to the user every day.

## Author

Sanyam Bhansali, https://github.com/Sanyam12B/Pacer-CS193_Project.