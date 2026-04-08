# ShadowShield Data

This folder contains experimental datasets used to test the ShadowShield decision engine.

## Files

- `sample_events.json`  
  A mixed dataset that combines both normal and suspicious network events for multiple IP addresses.  
  It is used to observe how the engine behaves when different scenarios are evaluated in a single run.

- `sample_events_normal.json`  
  Contains network events that represent **normal** traffic with no clear malicious activity.  
  It is used to verify that ShadowShield rules (such as `traffic_spike`) do not generate false positives and that most decisions remain LOW / ALLOW.

- `sample_events_suspicious.json`  
  Contains events with unusual patterns, such as sharp increases in packet counts for specific IPs (traffic spikes) or activity close to rule thresholds.  
  It is used to validate that the rules can correctly flag suspicious traffic and produce MEDIUM / HIGH decisions with `ALERT` when appropriate.

## Usage

- The `shadowshield_engine.py` script reads these files and converts each record into `test_cases` for rules like `detect_traffic_spike`.  
- The resulting decisions are written as JSON lines into `shadowshield_events.log`, making it easy to analyze how many LOW / MEDIUM / HIGH decisions are produced for each dataset.
