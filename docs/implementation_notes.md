# ShadowShield Implementation Notes

- ShadowShield is an autonomous decision engine that consumes Suricata `eve.json` events.
- Events are normalized into a ShadowShield format (see `samples/sample_events.json`).
- The engine assigns a risk level and action for each event and logs decisions to `shadowshield_events.log`.
