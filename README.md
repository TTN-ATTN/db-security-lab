## Structure

```
db-security-lab/
├── README.md
├── docker-compose.yml
│
├── config/
│   ├── acra.yaml               # Cấu hình AcraServer
│   ├── acracensor.yaml         # Cấu hình DBF rules
│   ├── prometheus.yml          # Scrape configs
│   ├── alertmanager.yml        # Alert routes
│   └── grafana/
│       └── dashboards/
│           └── mysql-overview.json
│
├── mysql/
│   ├── init.sql                # Schema khởi tạo
│   └── my.cnf                  # MySQL config (slow log, etc.)
│
├── scripts/
│   ├── seed_all.py             # Sinh dữ liệu mẫu
│   ├── scan_schema.py          # Sensitive Discovery - schema scan
│   ├── scan_data_patterns.py   # Sensitive Discovery - data scan
│   ├── test_sqli.py            # DBF - SQL injection test
│   ├── test_firewall.py        # DBF - firewall rules test
│   ├── test_masking.py         # Data Masking verification
│   ├── generate_load.py        # Performance - tạo load test
│   └── stress_connections.py   # Performance - connection stress
│
├── screenshots/                # Bằng chứng demo (PNG)
│   ├── active_monitor/
│   ├── dbf/
│   ├── data_masking/
│   ├── performance/
│   └── sensitive_discovery/
│
├── logs/                       # Log mẫu thu được
│   ├── audit_sample.json
│   └── slow_query_sample.log
│
└── report/
    ├── proposal.md             # File này
    ├── final_report.md         # Báo cáo cuối
    └── demo_video_link.txt
```

