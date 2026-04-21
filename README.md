# mesh-data

Live data from the Noppitlabs Meshtastic LoRa node (APEX), located in Devon, UK.

This repository is updated automatically by a Raspberry Pi running 24/7 alongside the node. Every time a message is received or a new node is heard on the mesh, the data here updates in real time. A daily snapshot of cumulative node counts is taken at midnight.

No location data is stored or published here. Node identity is tracked by hardware ID only.

---

## Files

| File | Description |
|------|-------------|
| `messages.json` | The 50 most recent text messages heard on the LongFast public channel |
| `nodes.json` | All unique nodes heard by APEX, keyed by hardware ID |
| `node_history.json` | Daily snapshots of cumulative unique node count since logging began |

---

## Data format

### messages.json

```json
[
  {
    "id": 1234567890,
    "from": "!75eddf30",
    "from_name": "APEX",
    "to": "^all",
    "text": "Hello from Devon",
    "timestamp": "2026-04-21T10:00:00+00:00",
    "channel": 0,
    "snr": 8.5,
    "hops": 0
  }
]
```

### nodes.json

```json
{
  "!75eddf30": {
    "id": "!75eddf30",
    "long_name": "APEX",
    "short_name": "AP3X",
    "hw_model": "TLORA_T3_S3",
    "role": "CLIENT_BASE",
    "snr": 8.5,
    "hops_away": 0,
    "last_heard": "2026-04-21T10:00:00+00:00"
  }
}
```

### node_history.json

```json
[
  {
    "date": "2026-04-20",
    "count": 47,
    "new_today": 3
  }
]
```

---

## Raw URLs

These files are served as public JSON and can be fetched directly:

```
https://raw.githubusercontent.com/noppitlabs/mesh-data/main/messages.json
https://raw.githubusercontent.com/noppitlabs/mesh-data/main/nodes.json
https://raw.githubusercontent.com/noppitlabs/mesh-data/main/node_history.json
```

---

## Live page

The data from this repo is displayed live at **[noppitlabs.com/pages/mesh](https://www.noppitlabs.com/pages/mesh)** — messages, node cards, and a node growth graph updated in real time.

---

## Hardware

- **Node:** LilyGO T-LoRa T3 S3
- **Region:** EU_868
- **Preset:** LongFast
- **Role:** CLIENT_BASE
- **Host:** Raspberry Pi 4, Devon, UK

---

## About

[Noppitlabs](https://www.noppitlabs.com) makes IoT devices, maker kits, and open source hardware — personally designed, built, tested and shipped by someone who spends too much time in the lab.
