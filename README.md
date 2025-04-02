# Roof Status Monitor

Roof Status Monitor is a Python-based GUI application that monitors the open/closed status of a roof in real time. It reads a designated text file to determine the roof's status and logs any changes along with a timestamp and current weather data. Additionally, the program displays formatted weather information from a separate file and, if enabled, can send notifications via Telegram.

## Features

- **Real-Time Roof Monitoring:**  
  Reads a text file every 10 seconds to detect if the roof is **OPEN** or **CLOSED** and logs changes.

- **Persistent Logging:**  
  Supports configurable logging modes:
  - **append:** Append new status changes to an existing log file.
  - **new:** Clear the log file at startup and start fresh.
  - **off:** Disable persistent logging.

  Each log entry includes the date, time, roof status (with extra spacing for **OPEN** for formatting), and current weather data.

- **Weather Data Display:**  
  Displays formatted weather information (e.g., Ambient Temp, Sky Temperature, Humidity, etc.) in a neat two-column layout. The weather file is read every 10 minutes.

- **Configurable via a Configuration File:**  
  Use `config.ini` to specify paths for the roof status file, weather data file, log file, and to set options such as debug mode, logging mode, and Telegram notifications.

- **Optional Telegram Notifications:**  
  When enabled, sends notifications upon roof status changes to your Telegram account.

## Installation

### Prerequisites

- **Python 3.x** installed.
- Required Python packages:
  - `tkinter` (usually bundled with Python)
  - `requests`  
  - (Other modules like `configparser` are part of the standard library)

### Steps

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/roof-status-monitor.git
   cd roof-status-monitor

2. **(optional) Create a Virtual Environment and Install Dependencies:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   pip install requests

3. **Configure the Application:**
   Update the `config.ini` file with your specific settings (see example below).

4. **Run the Program:**
   
   ```bash
   python roof_status_monitor.py

## Configuration
The application uses a configuration file (config.ini) to specify settings. Below is an example configuration:

   ```bash
   [Settings]
   debug = true
   log_mode = new                
   telegram_enabled = false
   status_file = C:/path/to/roof_status_file.txt
   weather_file = C:/path/to/weather_data.txt
   log_file = C:/path/to/roof_status_log.txt
   telegram_token = YOUR_TELEGRAM_BOT_TOKEN
   telegram_chat_id = YOUR_TELEGRAM_CHAT_ID
   ```
Make sure to adjust the paths and other parameters to match your environment. Note that at Starfront Observatories, the roof status file is building-specific, and the weather data file that contains the formatted data used by roof_status_monitor is 'daily.txt'.

## Usage

- **Roof Monitoring:**
  The program reads the roof status file every 10 seconds. If the status changes, the new status (with a timestamp) is displayed in the GUI and logged to the persistent log file (if logging is enabled).

- **Weather Data:**
  Weather data is read every 10 minutes and displayed in a two-column format.

- **Telegram Notifications:**
  If enabled (via the config file), the program sends a Telegram notification whenever the roof status changes.

- **Persistent Log File:**
  Depending on your log_mode setting:
  - **new:** The log file is cleared at startup.
  - **append:** New log entries are appended to the existing log.
  - **off:** No persistent logging is performed.

  Each log entry is a formatted line including the date, time, roof status (with extra spaces after "OPEN"), and a summary of the current weather data.

## License
This project is licensed under the **MIT License with Commons Clause Restriction**. This means you are free to use, modify, and distribute the software for non-commercial purposes only. Commercial use or selling the software is prohibited. For full details, please see the LICENSE file.

## Contact
For questions or support, please contact Keith Roberts at keithcroberts@gmail.com.

