# Deployment & Operations Guide: Trader

## 🚀 Live Access & URLs
- **Live Public Access URL:** [/preview/prod-trader-88d6ef/](/preview/prod-trader-88d6ef/)
- **Internal Port:** `0`
- **Runtime Engine:** `python_preview`
- **Deployment Status:** `DEPLOYED / ACTIVE`
- **Timestamp:** `2026-09-19T16:16:38.656848+00:00`

## 🛠️ Management & Service Control
### Launch Command
```bash
python3 app.py --port 0
```

### Health Check Probe
```bash
curl -I http://127.0.0.1:0/
```

### Systemd Service Template
```ini
[Unit]
Description=Trader Service
After=network.target

[Service]
Type=simple
WorkingDirectory=/tmp/pytest-of-root/pytest-0/test_human_in_the_loop_blocker0/workspaces/prod-trader-88d6ef
ExecStart=/usr/bin/python3 /tmp/pytest-of-root/pytest-0/test_human_in_the_loop_blocker0/workspaces/prod-trader-88d6ef/app.py
Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
```

## 🔒 Production Security Protocols
- HTTP-only reverse proxy via Nexus Gateway.
- Dedicated port allocation with zero port conflict.
