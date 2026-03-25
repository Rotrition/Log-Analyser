# logparse

Analyze Linux auth.log files for SSH security threats.

## Features

- Brute force detection (5+ failed attempts within 60 seconds)
- Unusual hour login alerts (2-5 AM)
- IP and user statistics
- Console and JSON output

## Installation

```bash
# make executable
chmod +x logparse

# optionally, add to path
sudo cp logparse /usr/local/bin/
```

## Usage

```bash
./logparse /var/log/auth.log
./logparse /var/log/auth.log --json
./logparse /var/log/auth.log --json -o report.json
./logparse /var/log/auth.log --no-color
```

## Configuration

Edit the constants at the top of the script:

```python
BRUTE_FORCE_THRESHOLD = 5   # failed attempts to trigger alert
BRUTE_FORCE_WINDOW = 60     # time window in seconds
UNUSUAL_HOUR_START = 2      # start of suspicious hours (2 AM)
UNUSUAL_HOUR_END = 5        # end of suspicious hours (5 AM)
```

## Requirements

Python 3.8+ (no external dependencies)
