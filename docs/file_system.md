SOC-Dashboard-Application/
│
├── .env.example                             # Environment variable template
├── .env                                     # Environment configuration (gitignored)
├── .eslintrc.js                             # ESLint configuration
├── .gitignore                               # Git ignore rules
├── .prettierrc                              # Prettier code formatting rules
├── README.md                                # Project overview and setup instructions
├── docker-compose.yml                       # Multi-container Docker configuration
├── Dockerfile                               # Main application Docker container definition
├── LICENSE                                  # Project license information
├── package.json                             # Node.js package configuration
├── tsconfig.json                            # TypeScript configuration
├── .cursorrules                             # Repository cursor rules
│
├── backend/
│   ├── app.js                               # Main application entry point
│   ├── server.js                            # Server initialization
│   ├── config/
│   │   ├── database.js                      # Database configuration
│   │   ├── express.js                       # Express framework configuration
│   │   ├── websocket.js                     # WebSocket configuration
│   │   ├── logging.js                       # Logging configuration
│   │   └── index.js                         # Config exports
│   ├── controllers/
│   │   ├── auth.controller.js               # Authentication controller
│   │   ├── dashboard.controller.js          # Dashboard controller
│   │   ├── kpi.controller.js                # KPI data controller
│   │   ├── alerts.controller.js             # Alerts controller
│   │   ├── integration.controller.js        # Integration management controller
│   │   └── user.controller.js               # User management controller
│   ├── middleware/
│   │   ├── auth.middleware.js               # Authentication middleware
│   │   ├── error.middleware.js              # Error handling middleware
│   │   ├── logging.middleware.js            # Request logging middleware
│   │   └── rbac.middleware.js               # Role-based access control middleware
│   ├── models/
│   │   ├── alert.model.js                   # Alert data model
│   │   ├── dashboard.model.js               # Dashboard configuration model
│   │   ├── integration.model.js             # Integration model
│   │   ├── kpi.model.js                     # KPI definition model
│   │   └── user.model.js                    # User model
│   ├── routes/
│   │   ├── auth.routes.js                   # Authentication routes
│   │   ├── dashboard.routes.js              # Dashboard routes
│   │   ├── integration.routes.js            # Integration routes
│   │   ├── kpi.routes.js                    # KPI data routes
│   │   ├── user.routes.js                   # User management routes
│   │   └── index.js                         # Routes index
│   ├── services/
│   │   ├── alert.service.js                 # Alert processing service
│   │   ├── auth.service.js                  # Authentication service
│   │   ├── dashboard.service.js             # Dashboard service
│   │   ├── integration.service.js           # Integration service
│   │   ├── kpi.service.js                   # KPI calculation service
│   │   ├── realtime.service.js              # Real-time data service
│   │   └── user.service.js                  # User management service
│   └── utils/
│       ├── database.utils.js                # Database utility functions
│       ├── encryption.utils.js              # Encryption utility functions
│       ├── validation.utils.js              # Input validation utilities
│       └── logger.js                        # Logger utility
│
├── database/
│   ├── connection.js                        # Database connection manager
│   ├── migrations/
│   │   ├── 01_create_users.js               # User table migration
│   │   ├── 02_create_dashboards.js          # Dashboard table migration
│   │   ├── 03_create_integrations.js        # Integrations table migration
│   │   ├── 04_create_alerts.js              # Alerts table migration
│   │   └── 05_create_kpis.js                # KPI table migration
│   └── seeders/
│       ├── 01_default_users.js              # Default user seed data
│       ├── 02_default_dashboards.js         # Default dashboard seed data
│       ├── 03_default_integrations.js       # Default integration seed data
│       └── 04_default_kpis.js               # Default KPI seed data
│
├── planning/
│   ├── stakeholder_meetings/
│   │   ├── meeting_notes_001.md             # Initial requirements gathering
│   │   ├── meeting_notes_002.md             # KPI definition review
│   │   └── meeting_notes_003.md             # Design approval meeting
│   ├── kpi_definitions/
│   │   ├── soc_kpi_inventory.xlsx           # KPI inventory spreadsheet
│   │   ├── critical_kpis.md                 # Critical KPI definitions
│   │   └── kpi_calculation_methods.md       # KPI calculation methodologies
│   ├── wireframes/
│   │   ├── main_dashboard.png               # Main dashboard wireframe
│   │   ├── alerts_panel.png                 # Alerts panel wireframe
│   │   ├── drill_down_view.png              # Drill-down view wireframe
│   │   └── user_customization.png           # User customization wireframe
│   └── prototypes/
│       ├── dashboard_prototype.html         # HTML prototype
│       ├── prototype_screenshots/           # Prototype screenshots
│       └── interactive_prototype_link.md    # Link to interactive prototype
│
├── integrations/
│   ├── config/
│   │   ├── api_credentials.json.example     # Example API credential template
│   │   ├── connection_config.js             # Integration connection configuration
│   │   └── polling_intervals.json           # API polling interval configuration
│   ├── api/
│   │   ├── siem/
│   │   │   ├── splunk.connector.js          # Splunk API connector
│   │   │   ├── qradar.connector.js          # QRadar API connector
│   │   │   └── arcsight.connector.js        # ArcSight API connector
│   │   ├── soar/
│   │   │   ├── cortex_xsoar.connector.js    # Cortex XSOAR connector
│   │   │   └── splunk_soar.connector.js     # Splunk SOAR connector
│   │   ├── endpoint_security/
│   │   │   ├── crowdstrike.connector.js     # CrowdStrike Falcon connector
│   │   │   └── carbon_black.connector.js    # Carbon Black connector
│   │   ├── ids_ips/
│   │   │   ├── snort.connector.js           # Snort connector
│   │   │   ├── suricata.connector.js        # Suricata connector
│   │   │   └── cisco_firepower.connector.js # Cisco Firepower connector
│   │   ├── network_monitoring/
│   │   │   ├── stealthwatch.connector.js    # Cisco Stealthwatch connector
│   │   │   └── darktrace.connector.js       # Darktrace connector
│   │   ├── threat_intelligence/
│   │   │   ├── threatconnect.connector.js   # ThreatConnect connector
│   │   │   └── recorded_future.connector.js # Recorded Future connector
│   │   ├── cloud_security/
│   │   │   ├── aws_guardduty.connector.js   # AWS GuardDuty connector
│   │   │   └── prisma_cloud.connector.js    # Prisma Cloud connector
│   │   ├── dlp/
│   │   │   ├── forcepoint.connector.js      # Forcepoint DLP connector
│   │   │   └── mcafee_dlp.connector.js      # McAfee DLP connector
│   │   └── compliance/
│   │       ├── nessus.connector.js          # Nessus connector
│   │       ├── qualys.connector.js          # Qualys connector
│   │       └── rapid7.connector.js          # Rapid7 connector
│   ├── agents/
│   │   ├── filebeat/
│   │   │   ├── filebeat.yml                 # Filebeat configuration
│   │   │   └── deployment.js                # Filebeat deployment script
│   │   ├── metricbeat/
│   │   │   ├── metricbeat.yml               # Metricbeat configuration
│   │   │   └── deployment.js                # Metricbeat deployment script
│   │   └── fluentd/
│   │       ├── fluentd.conf                 # Fluentd configuration
│   │       └── deployment.js                # Fluentd deployment script
│   ├── webhooks/
│   │   ├── webhook_handler.js               # Generic webhook handler
│   │   ├── siem_webhook.js                  # SIEM webhook processor
│   │   └── alert_webhook.js                 # Alert webhook processor
│   └── soar/
│       ├── playbooks/
│       │   ├── incident_response.yml        # Incident response playbook
│       │   ├── alert_triage.yml             # Alert triage playbook
│       │   └── threat_hunting.yml           # Threat hunting playbook
│       └── incident_templates/
│           ├── malware_template.json        # Malware incident template
│           ├── phishing_template.json       # Phishing incident template
│           └── data_breach_template.json    # Data breach incident template
│
├── data_pipeline/
│   ├── config/
│   │   ├── logstash.conf                    # Logstash configuration
│   │   ├── kafka_topics.json                # Kafka topic definitions
│   │   └── nifi_templates/                  # Apache NiFi templates
│   │       ├── siem_flow.xml                # SIEM data flow template
│   │       └── metrics_flow.xml             # Metrics flow template
│   ├── normalization/
│   │   ├── schemas/
│   │   │   ├── alert_schema.json            # Alert data schema
│   │   │   ├── metric_schema.json           # Metric data schema
│   │   │   └── event_schema.json            # Event data schema
│   │   └── transformation_scripts/
│   │       ├── siem_normalizer.js           # SIEM data normalizer
│   │       ├── soar_normalizer.js           # SOAR data normalizer
│   │       └── metrics_normalizer.js        # Metrics data normalizer
│   └── aggregation_storage/
│       ├── influxdb/
│       │   ├── influxdb.conf                # InfluxDB configuration
│       │   └── retention_policies.js        # Data retention policies
│       └── prometheus/
│           ├── prometheus.yml               # Prometheus configuration
│           └── alert_rules.yml              # Prometheus alerting rules
│
├── realtime/
│   ├── config/
│   │   └── socket_config.js                 # WebSocket configuration
│   ├── processors/
│   │   ├── metric_processor.js              # Metric data processor
│   │   ├── alert_processor.js               # Alert data processor
│   │   └── event_processor.js               # Event data processor
│   ├── backend/
│   │   ├── websocket_server/
│   │   │   ├── socket_server.js             # WebSocket server implementation
│   │   │   ├── connection_manager.js        # WebSocket connection manager
│   │   │   └── authentication.js            # WebSocket authentication
│   │   └── streaming_logic/
│   │       ├── data_streamer.js             # Data streaming implementation
│   │       ├── metric_streamer.js           # Metric-specific streaming
│   │       └── alert_streamer.js            # Alert-specific streaming
│   └── frontend/
│       ├── websocket_client/
│       │   ├── socket_client.js             # WebSocket client implementation
│       │   └── connection_manager.js        # Client connection manager
│       └── real_time_visuals/
│           ├── live_chart.js                # Live-updating chart component
│           ├── alert_feed.js                # Real-time alert feed component
│           └── counter_widget.js            # Real-time counter widget
│
├── dashboard/
│   ├── frontend/
│   │   ├── public/
│   │   │   ├── index.html                   # Main HTML entry point
│   │   │   ├── favicon.ico                  # Site favicon
│   │   │   └── manifest.json                # PWA manifest
│   │   ├── assets/
│   │   │   ├── images/                      # Image assets
│   │   │   ├── icons/                       # Icon assets
│   │   │   └── styles/                      # Global styles
│   │   │       ├── main.css                 # Main CSS file
│   │   │       └── variables.css            # CSS variables
│   │   ├── config/
│   │   │   ├── webpack.config.js            # Webpack configuration
│   │   │   ├── theme.js                     # Application theming
│   │   │   └── routes.js                    # Frontend routing
│   │   ├── state/
│   │   │   ├── store.js                     # Redux/Context store
│   │   │   ├── reducers/                    # State reducers
│   │   │   │   ├── auth.reducer.js          # Authentication reducer
│   │   │   │   ├── dashboard.reducer.js     # Dashboard state reducer
│   │   │   │   ├── alerts.reducer.js        # Alerts state reducer
│   │   │   │   └── kpi.reducer.js           # KPI state reducer
│   │   │   └── actions/                     # State actions
│   │   │       ├── auth.actions.js          # Authentication actions
│   │   │       ├── dashboard.actions.js     # Dashboard actions
│   │   │       ├── alerts.actions.js        # Alerts actions
│   │   │       └── kpi.actions.js           # KPI actions
│   │   ├── react_app/
│   │   │   ├── App.js                       # Main application component
│   │   │   ├── index.js                     # React entry point
│   │   │   ├── routes.js                    # Application routes
│   │   │   └── api.js                       # API client configuration
│   │   ├── components/
│   │   │   ├── common/
│   │   │   │   ├── Button.js                # Button component
│   │   │   │   ├── Card.js                  # Card component
│   │   │   │   ├── Dropdown.js              # Dropdown component
│   │   │   │   └── Modal.js                 # Modal component
│   │   │   ├── layout/
│   │   │   │   ├── Header.js                # Header component
│   │   │   │   ├── Sidebar.js               # Sidebar component
│   │   │   │   ├── Footer.js                # Footer component
│   │   │   │   └── Layout.js                # Main layout component
│   │   │   ├── auth/
│   │   │   │   ├── Login.js                 # Login component
│   │   │   │   └── Register.js              # Registration component
│   │   │   └── dashboard/
│   │   │       ├── DashboardGrid.js         # Dashboard grid layout
│   │   │       ├── WidgetContainer.js       # Widget container component
│   │   │       └── FilterBar.js             # Dashboard filter component
│   │   ├── customization_ui/
│   │   │   ├── DashboardCustomizer.js       # Dashboard customization UI
│   │   │   ├── WidgetSelector.js            # Widget selection component
│   │   │   └── LayoutEditor.js              # Layout editing component
│   │   └── drilldown_views/
│   │       ├── AlertDetail.js               # Alert detail view
│   │       ├── KpiDetail.js                 # KPI detail view
│   │       └── IncidentView.js              # Incident detail view
│   ├── widgets/
│   │   ├── kpi_widgets/
│   │   │   ├── UptimeWidget.js              # Uptime KPI widget
│   │   │   ├── ErrorCountWidget.js          # Error count widget
│   │   │   ├── ResponseLatencyWidget.js     # Response latency widget
│   │   │   └── AlertVolumeWidget.js         # Alert volume widget
│   │   ├── chart_widgets/
│   │   │   ├── LineChartWidget.js           # Line chart widget
│   │   │   ├── BarChartWidget.js            # Bar chart widget
│   │   │   ├── PieChartWidget.js            # Pie chart widget
│   │   │   └── HeatmapWidget.js             # Heatmap widget
│   │   └── alert_panels/
│   │       ├── AlertListWidget.js           # Alert list widget
│   │       ├── CriticalAlertWidget.js       # Critical alert widget
│   │       └── AlertSummaryWidget.js        # Alert summary widget
│   ├── configuration/
│   │   └── user_dashboards/
│   │       ├── dashboard_schema.json        # Dashboard schema definition
│   │       ├── default_layout.json          # Default dashboard layout
│   │       └── widget_registry.js           # Widget registry
│   └── real_time/
│       ├── charts/
│       │   ├── RealTimeLineChart.js         # Real-time line chart
│       │   └── RealTimeCounter.js           # Real-time counter
│       └── updates/
│           ├── UpdateManager.js             # Update manager
│           └── DataSubscription.js          # Data subscription handler
│
├── alerting_automation/
│   ├── thresholds_definitions/
│   │   ├── kpi_thresholds.json              # KPI threshold definitions
│   │   ├── alert_thresholds.json            # Alert threshold definitions
│   │   └── threshold_manager.js             # Threshold management
│   ├── alerting_logic/
│   │   ├── alert_evaluator.js               # Alert evaluation logic
│   │   ├── alert_generator.js               # Alert generation
│   │   └── alert_router.js                  # Alert routing logic
│   ├── notifications_integrations/
│   │   ├── pagerduty.js                     # PagerDuty integration
│   │   ├── slack.js                         # Slack integration
│   │   ├── ms_teams.js                      # Microsoft Teams integration
│   │   ├── email.js                         # Email notification
│   │   └── notification_manager.js          # Notification management
│   └── soar_incident_automation/
│       ├── incident_creator.js              # Incident creation logic
│       ├── playbook_trigger.js              # Playbook trigger mechanism
│       ├── cortex_integration.js            # Cortex XSOAR integration
│       └── splunk_soar_integration.js       # Splunk SOAR integration
│
├── security_compliance/
│   ├── authentication/
│   │   ├── oauth_jwt/
│   │   │   ├── oauth_config.js              # OAuth configuration
│   │   │   ├── jwt_generator.js             # JWT token generator
│   │   │   └── token_validator.js           # Token validation logic
│   │   └── middleware_rbac/
│   │       ├── rbac_config.js               # RBAC configuration
│   │       ├── permission_mapper.js         # Permission mapping
│   │       └── role_definitions.json        # Role definitions
│   ├── encryption/
│   │   ├── tls_certificates/
│   │   │   ├── generate_certs.sh            # Certificate generation script
│   │   │   └── tls_config.js                # TLS configuration
│   │   └── aes_encryption/
│   │       ├── encryption_service.js        # Encryption service
│   │       └── key_management.js            # Encryption key management
│   └── compliance_audits/
│       ├── penetration_tests/
│       │   ├── test_plan.md                 # Penetration test plan
│       │   └── results_template.md          # Results template
│       ├── compliance_checks/
│       │   ├── gdpr_checklist.md            # GDPR compliance checklist
│       │   ├── nist_checklist.md            # NIST compliance checklist
│       │   └── compliance_scanner.js        # Compliance scanning tool
│       └── audit_logs/
│           ├── audit_logger.js              # Audit logging implementation
│           ├── log_retention_policy.js      # Log retention policy
│           └── audit_reporter.js            # Audit reporting tool
│
├── security/
│   ├── framework/
│   │   ├── GrayGhostSecurity.js             # Gray Ghost Security Framework implementation
│   │   ├── SecurityLevel.js                 # Security level implementation
│   │   ├── ThreatSeverity.js                # Threat severity implementation
│   │   └── SecurityEvent.js                 # Security event implementation
│   ├── crypto/
│   │   ├── CryptoUtils.js                   # Cryptographic utilities
│   │   ├── KeyManager.js                    # Key management
│   │   └── SecureConfig.js                  # Secure configuration
│   ├── auth/
│   │   ├── AuthManager.js                   # Authentication manager
│   │   └── InputValidator.js                # Input validation
│   ├── monitoring/
│   │   ├── EndpointProtection.js            # Endpoint protection
│   │   ├── NetworkSecurity.js               # Network security
│   │   ├── AnomalyDetection.js              # Anomaly detection
│   │   └── SecurityMonitor.js               # Security monitoring
│   ├── config/
│   │   ├── security_levels.json             # Security level configuration
│   │   └── security_policies.json           # Security policies
│   ├── validation/
│   │   └── schemas.js                       # Input validation schemas
│   └── compliance/
│       └── audit_config.js                  # Audit configuration
│
├── infrastructure/
│   ├── deployment/
│   │   ├── docker/
│   │   │   ├── docker-compose.prod.yml      # Production Docker Compose
│   │   │   ├── docker-compose.dev.yml       # Development Docker Compose
│   │   │   └── dockerfiles/                 # Service-specific Dockerfiles
│   │   │       ├── api.Dockerfile           # API service Dockerfile
│   │   │       ├── frontend.Dockerfile      # Frontend Dockerfile
│   │   │       └── worker.Dockerfile        # Worker service Dockerfile
│   │   ├── kubernetes/
│   │   │   ├── deployments/                 # Kubernetes deployments
│   │   │   │   ├── api-deployment.yaml      # API deployment
│   │   │   │   ├── frontend-deployment.yaml # Frontend deployment
│   │   │   │   └── worker-deployment.yaml   # Worker deployment
│   │   │   ├── services/                    # Kubernetes services
│   │   │   │   ├── api-service.yaml         # API service
│   │   │   │   └── frontend-service.yaml    # Frontend service
│   │   │   └── configmaps/                  # Kubernetes ConfigMaps
│   │   │       ├── api-config.yaml          # API configuration
│   │   │       └── app-config.yaml          # Application configuration
│   │   └── environments/
│   │       ├── development/                 # Development environment configs
│   │       ├── staging/                     # Staging environment configs
│   │       └── production/                  # Production environment configs
│   ├── monitoring/
│   │   ├── prometheus/
│   │   │   ├── prometheus.yml               # Prometheus configuration
│   │   │   └── alert_rules.yml              # Prometheus alerting rules
│   │   └── grafana/
│   │       ├── dashboards/                  # Grafana dashboards
│   │       └── datasources/                 # Grafana data sources
│   ├── ci_cd/
│   │   └── workflows/
│   │       ├── build.yml                    # Build workflow
│   │       ├── test.yml                     # Test workflow
│   │       ├── deploy.yml                   # Deployment workflow
│   │       └── security_scan.yml            # Security scanning workflow
│   └── scripts/
│       └── automation_scripts/
│           ├── backup.sh                    # Backup script
│           ├── deploy.sh                    # Deployment script
│           └── monitor.sh                   # Monitoring script
│
├── docs/
│   ├── user_guides/
│   │   ├── getting_started.md               # Getting started guide
│   │   ├── dashboard_configuration.md       # Dashboard configuration guide
│   │   ├── alert_management.md              # Alert management guide
│   │   └── integration_setup.md             # Integration setup guide
│   ├── technical_documentation/
│   │   ├── architecture.md                  # Architecture documentation
│   │   ├── api_documentation.md             # API documentation
│   │   ├── data_flow.md                     # Data flow documentation
│   │   └── security_framework.md            # Security framework documentation
│   ├── compliance_documentation/
│   │   ├── gdpr_compliance.md               # GDPR compliance documentation
│   │   ├── nist_compliance.md               # NIST compliance documentation
│   │   └── iso27001_compliance.md           # ISO 27001 compliance documentation
│   └── architecture_diagrams/
│       ├── system_architecture.png          # System architecture diagram
│       ├── data_flow_diagram.png            # Data flow diagram
│       ├── security_model.png               # Security model diagram
│       └── component_diagram.png            # Component diagram
│
├── tests/
│   ├── config/
│   │   ├── jest.config.js                   # Jest configuration
│   │   └── pytest.ini                       # Pytest configuration
│   ├── fixtures/
│   │   ├── alert_data.json                  # Alert test data
│   │   ├── user_data.json                   # User test data
│   │   └── kpi_data.json                    # KPI test data
│   ├── mocks/
│   │   ├── api_mocks.js                     # API mock data
│   │   ├── service_mocks.js                 # Service mock data
│   │   └── websocket_mocks.js               # WebSocket mock data
│   ├── unit_tests/
│   │   ├── backend/
│   │   │   ├── controllers.test.js          # Controller tests
│   │   │   ├── services.test.js             # Service tests
│   │   │   └── models.test.js               # Model tests
│   │   └── frontend/
│   │       ├── components.test.js           # Component tests
│   │       ├── reducers.test.js             # Reducer tests
│   │       └── actions.test.js              # Action tests
│   ├── integration_tests/
│   │   ├── api.test.js                      # API integration tests
│   │   ├── auth.test.js                     # Authentication integration tests
│   │   └── data_flow.test.js                # Data flow integration tests
│   ├── end_to_end_tests/
│   │   ├── dashboard.test.js                # Dashboard end-to-end tests
│   │   ├── alerts.test.js                   # Alerts end-to-end tests
│   │   └── user_customization.test.js       # User customization end-to-end tests
│   └── coverage/                            # Test coverage reports
│
├── .github/
│   ├── workflows/
│   │   ├── build.yml                        # Build workflow
│   │   ├── test.yml                         # Test workflow
│   │   ├── deploy.yml                       # Deployment workflow
│   │   └── security_scan.yml                # Security scanning workflow
│   ├── pull_request_template.md             # Pull request template
│   └── issue_templates/
│       ├── bug_report.md                    # Bug report template
│       ├── feature_request.md               # Feature request template
│       ├── security_vulnerability.md        # Security vulnerability template
│       └── incident_report.md               # Incident report template
│
└── audits/
    └── security_audit.log                   # Security audit log