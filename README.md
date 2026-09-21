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

## Watched scope

The feed is limited to:

- ときのそら
- AZKi
- 風真いろは
- 博衣こより
- hololive-wide events/campaigns that apply to the whole group

## Feed schema

`deadlines.json` uses schema version 1.

Each item contains:

- `id`: stable public identifier
- `title`: public event/product/campaign title
- `audience`: one or more of `全体`, `そら`, `AZKi`, `いろは`, `こより`
- `kind`: `GOODS`, `TICKET`, `PAYMENT`, or `APPLICATION`
- `start`: ISO 8601 start time when publicly stated; otherwise null
- `deadline`: ISO 8601 end/deadline time
- `generalSaleTicket`: true only for general/first-come ticket sales
- `sourceUrl`: public source URL

## Update policy

A scheduled ChatGPT task may update this repository using only publicly accessible information.

When updating:

1. Prefer official Hololive, official talent/event sites, official shops, and official ticket/event pages.
2. Do not add inferred dates when an authoritative source does not state them.
3. Preserve a source URL for every item.
4. Correct an existing item when an official source changes its dates.
5. Remove expired entries after their deadline has passed.
6. Never store credentials, private schedules, device data, location data, account identifiers, or other non-public personal information.

The Echo Clock Android app reads this file directly and checks the public feed every 30 minutes. It also retains its existing local official-site collection as a fallback.
