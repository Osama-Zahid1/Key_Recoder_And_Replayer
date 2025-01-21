# Key Recorder and Replayer Script

This script, written in AutoHotkey (AHK), allows you to record and replay specific key sequences. It's useful for automating repetitive tasks or simulating key presses in games or applications.

## Features:
- **Keys Recorded:** `w`, `a`, `s`, `d`, `l`, and `Shift`.
- **Start/Stop Recording:** Press `F8` to toggle recording mode.
  - Recorded keys and their timestamps are stored during this mode.
- **Replay Recorded Sequence:** Press `F9` to replay the recorded key sequence with accurate timing.
- **Exit Script:** Press `F10` to terminate the script.

## How It Works:
1. **Recording:**
   - Press `F8` to start recording.
   - Any press of the defined keys will be recorded with the exact time of the press.
   - Press `F8` again to stop recording.

2. **Replaying:**
   - Press `F9` to replay the recorded key sequence.
   - The script simulates each key press and release with the same timing as recorded.

3. **Exiting:**
   - Press `F10` to safely exit the script.

## Requirements:
- AutoHotkey must be installed to run this script.


