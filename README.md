# holo-deadlines

Public deadline feed used by the Echo Clock display.

Only publicly available event/sales information is stored here:

- title
- target talent/group
- category
- sale/application start time
- deadline/end time
- whether a ticket entry is a general-sale ticket
- public source URL

No device information, account credentials, private schedules, location data, or other personal information is stored in this repository.

## Feed

`deadlines.json` uses ISO 8601 timestamps with timezone offsets. It is designed to be updated by a scheduled ChatGPT research task and consumed read-only by the Echo Clock Android app.
