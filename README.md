# Pipoo — Voice-Enabled Desktop Assistant

Pipoo is a Python desktop assistant that combines voice interaction with Gemini-powered responses and simple productivity features.

## What it does

- Accepts voice input and responds using text-to-speech
- Connects to the Gemini API for AI responses
- Creates, lists, and deletes notes
- Creates, lists, and cancels reminders
- Supports configurable assistant name, speech rate, and voice settings
- Stores notes and reminders locally as JSON files

This is a personal project/prototype. Test the commands on your machine and review the local storage behavior before relying on it for important reminders.

## Tech stack

- Python
- Google Gemini API
- SpeechRecognition and PyAudio
- pyttsx3
- python-dotenv
- Tkinter / local desktop UI components

## Setup

### 1. Requirements

- Python 3.8+
- Microphone and audio output
- A Gemini API key

### 2. Install dependencies

From the repository root:

```bash
python -m venv .venv
```

**Windows PowerShell**
```powershell
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install packages:

```bash
pip install -r requirements.txt
```

> Note: PyAudio can require additional system setup depending on your operating system.

### 3. Configure environment variables

Copy `.env.example` to `.env` in the repository root, then replace the placeholder with your own key.

```env
GEMINI_API_KEY=your_gemini_api_key
ASSISTANT_NAME=Pipoo
SPEECH_RATE=170
VOICE_GENDER=female
```

Keep `.env` private and never commit real credentials. The example file is safe to commit; your real key is not.

### 4. Run Pipoo

```bash
python src/main.py
```

On Windows, you can also run `run_pipoo.bat` after activating the virtual environment.

## Example voice commands

- “Create a note to buy groceries”
- “Show my notes”
- “Remind me to take a break in 30 minutes”
- “Show my reminders”
- “Delete note 2”
- “Clear all reminders”

Exact command recognition depends on how the voice and intent handlers parse the request.

## Local data

Pipoo stores notes and reminders in JSON files on your machine. Avoid storing passwords, API keys, financial details, or other sensitive information in notes.

## Project structure

```text
Pipoo-Voice-Assistant/
├── src/
│   ├── main.py
│   ├── config.py
│   ├── gemini_api.py
│   ├── voice_handler.py
│   ├── reminder_notifier.py
│   ├── automation_handler.py
│   ├── ui_manager.py
│   └── animations.py
├── requirements.txt
├── run_pipoo.bat
└── README.md
```

## Current limitations

- Voice recognition quality depends on the microphone, environment, and speech-recognition service.
- Audio dependencies may need OS-specific setup.
- Reminder timing and persistence should be tested before relying on them for time-critical tasks.

## Author

**Beauty Mauryaa (Nova)** · [GitHub](https://github.com/BeautyMauryaa)
