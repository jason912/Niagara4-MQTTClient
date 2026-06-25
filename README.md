# Niagara4-MQTTClient 📡

[![Niagara 4.14+](https://img.shields.io/badge/Niagara-4.14%2B-blue)](https://www.tridium.com)
[![License: Free](https://img.shields.io/badge/License-Free-brightgreen)](LICENSE)
[![Contact](https://img.shields.io/badge/Contact-WhatsApp-brightgreen)](https://wa.me/8613801909968)

> **A free MQTT debugging client for Niagara 4 — send, receive, and inspect MQTT messages directly from your station.**

---

## What Is It?

A lightweight, zero-license MQTT client module that runs inside Niagara Workbench. Use it to:

- **Publish** messages to any MQTT broker
- **Subscribe** to topics and view incoming messages in real time
- **Debug** MQTT communication during development and commissioning

> ⚠️ **Not for production.** This tool is designed for debugging and testing only. Each client consumes CPU resources — not suitable for large-scale deployment.

---

## Quick Start

```bash
# 1. Install gline.pem certificate into your station trust store

# 2. Add glineMqtt-rt.jar to your modules/ directory

# 3. Restart station

# 4. Create an MQTT Client component in Workbench:
#    - Set broker IP / port
#    - Enter topic to subscribe
#    - Set QoS (0/1/2 supported)
#    - Configure username/password (encrypted)

# 5. Enable the client → messages appear in the panel
```

> After changing any parameter, **disable then re-enable** the client for changes to take effect.

---

## Features

| Feature | Support |
|---------|:-------:|
| MQTT publish & subscribe | ✅ |
| QoS 0, 1, 2 | ✅ |
| Username/password authentication | ✅ |
| EMQX & Node-RED Aedes brokers | ✅ Tested |
| SSL/TLS | ❌ Not yet |
| BQL → JSON → MQTT pipeline | ✅ Via companion bql2json module |

---

## BQL + MQTT Pipeline

For sending large datasets via MQTT, pair this module with our **bql2json** tool:

```sql
station:|slot:/Drivers/MQTT/yourFolder/points|bql:select name,out.value as 'value',out.status as 'status' from control:ControlPoint
```

This query extracts all point values under a folder. Convert to JSON with bql2json, then publish via the MQTT client.

---

## Changelog

| Date | Change |
|------|--------|
| May 7, 2026 | Removed log toggle — all logs now in Platform Director |
| May 6, 2026 | Added QoS 0/1/2, encrypted auth, EMQX/Aedes support |
| Apr 28, 2026 | Client ID now read-only; added log enable/disable |

---

## Requirements

| Component | Requirement |
|-----------|-------------|
| **Niagara** | 4.14 or later |
| **JAR signing** | Requires gline.pem certificate |
| **Broker tested** | EMQX, Node-RED Aedes |

---

## Support & Contact

- **Email**: [jason.zhang@gline-net.com](mailto:jason.zhang@gline-net.com)
- **WhatsApp**: [+86 138 0199 0968](https://wa.me/8613801909968)

**Shanghai Gline Net Co., Ltd.** — Your Partner in Smarter Automation

---

© 2026 Shanghai Gline Net Co., Ltd. All rights reserved.
