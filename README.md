# AskMyLogs 🔍

> **Unified Observability Platform with Natural Language Querying**

Transform your observability chaos into intelligent insights. AskMyLogs is a self-hosted enterprise platform that connects your existing observability tools and lets you query them using natural language, powered by AI and MCP (Model Context Protocol).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![Docker](https://img.shields.io/badge/Docker-ready-blue.svg)](https://www.docker.com/)
[![Enterprise](https://img.shields.io/badge/Enterprise-Ready-green.svg)](#enterprise-features)

## 🎯 Problem Statement

DevOps and SRE teams struggle with:
- **Tool Fragmentation**: Switching between multiple observability dashboards
- **Context Loss**: Correlating events across different systems
- **Query Complexity**: Learning different query languages for each tool
- **Incident Response**: Slow root cause analysis during outages
- **Knowledge Silos**: Tribal knowledge locked in individual engineers

## 🚀 Solution

AskMyLogs provides a unified interface where engineers can:
- **Ask Questions in Plain English**: "Why did my payment service fail at 3 PM?"
- **Get Intelligent Answers**: AI analyzes logs, metrics, and traces across all connected tools
- **Accelerate Incident Response**: Automated root cause analysis and remediation suggestions
- **Reduce Context Switching**: Single dashboard for all observability data
- **Democratize Observability**: No need to learn tool-specific query languages

## ✨ Key Features

### 🧠 Natural Language Intelligence
- **Conversational Queries**: Ask questions like you would to a colleague
- **Context-Aware Responses**: Understands service relationships and dependencies
- **Multi-Tool Analysis**: Correlates data across different observability platforms
- **Automated Insights**: Proactive anomaly detection and trend analysis

### 🔌 Universal Plugin Architecture
- **Tool Agnostic**: Works with any observability tool through plugins
- **Easy Integration**: Add new tools without changing core platform
- **Unified Data Model**: Consistent experience across all connected tools
- **Future Proof**: Extensible architecture for emerging tools

### 🛠️ Enterprise Grade
- **Self-Hosted**: Complete control over your sensitive observability data
- **Multi-Tenant**: Isolated environments for different teams/organizations
- **RBAC**: Role-based access control with fine-grained permissions
- **Audit Logging**: Complete audit trail for compliance requirements
- **High Availability**: Designed for production environments

### 📊 Intelligent Dashboards
- **Service-Centric Views**: Organize observability data by business services
- **Real-Time Streaming**: Live log and metric updates
- **Custom Visualizations**: Build dashboards that matter to your team
- **Alert Correlation**: Intelligent grouping and noise reduction

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                     AskMyLogs Platform                         │
├─────────────────┬─────────────────┬─────────────────────────────┤
│   Web Interface │   API Gateway   │    Natural Language        │
│   (React/Next)  │   (Kong)        │    Query Engine             │
├─────────────────┼─────────────────┼─────────────────────────────┤
│   LLM Service   │   MCP Server    │    Plugin Manager          │
│   (OpenAI/Local)│   (Tools)       │    (Registry)               │
└─────────────────┴─────────────────┴─────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                      Plugin Ecosystem                          │
├─────────────────┬─────────────────┬─────────────────────────────┤
│   Grafana       │   DataDog       │    New Relic               │
│   Plugin        │   Plugin        │    Plugin                  │
├─────────────────┼─────────────────┼─────────────────────────────┤
│   Splunk        │   Elastic       │    Custom Tools            │
│   Plugin        │   Plugin        │    Plugin                  │
└─────────────────┴─────────────────┴─────────────────────────────┘
```

## 🎮 Quick Start

### Prerequisites
- Docker & Docker Compose
- Python 3.11+
- Node.js 18+
- PostgreSQL 15+
- Redis 7+

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/askmylogs.git
   cd askmylogs
   ```

2. **Environment Setup**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

3. **Start with Docker Compose**
   ```bash
   docker-compose up -d
   ```

4. **Access the Platform**
   - Web UI: http://localhost:3000
   - API: http://localhost:8080
   - Admin Panel: http://localhost:3000/admin

### First Steps

1. **Connect Your First Tool**
   - Navigate to Settings → Integrations
   - Add your Grafana instance
   - Test the connection

2. **Configure Your Services**
   - Define your microservices
   - Map them to observability data sources
   - Set up service dependencies

3. **Ask Your First Question**
   ```
   "Show me errors in the payment service from the last hour"
   "Why is my API response time increasing?"
   "What caused the spike in database connections?"
   ```

## 🔧 Supported Integrations

### Currently Supported
- **Grafana** (Prometheus, Loki, Alertmanager)
- **DataDog** (Logs, Metrics, Traces)
- **New Relic** (APM, Infrastructure)
- **Splunk** (Enterprise Search)
- **Elastic** (Elasticsearch, Kibana)

### Coming Soon
- **Honeycomb** (Observability for complex systems)
- **Jaeger** (Distributed tracing)
- **Prometheus** (Direct integration)
- **AWS CloudWatch** (AWS native monitoring)
- **Azure Monitor** (Azure native monitoring)

## 📖 Documentation

### User Guides
- [Getting Started](./docs/getting-started.md)
- [Service Configuration](./docs/service-configuration.md)
- [Natural Language Queries](./docs/natural-language-queries.md)
- [Dashboard Creation](./docs/dashboard-creation.md)

### Developer Guides
- [Plugin Development](./docs/plugin-development.md)
- [API Reference](./docs/api-reference.md)
- [Contributing](./docs/contributing.md)
- [Architecture Deep Dive](./docs/architecture.md)

### Operations
- [Deployment Guide](./docs/deployment.md)
- [Security Configuration](./docs/security.md)
- [Monitoring & Observability](./docs/monitoring.md)
- [Troubleshooting](./docs/troubleshooting.md)

## 🧪 Example Use Cases

### Incident Response
```
Engineer: "Why is checkout failing?"

AskMyLogs: "I found 3 issues in the last 15 minutes:
1. Payment service showing 503 errors (85% failure rate)
2. Database connection pool exhausted
3. High memory usage on payment-service-3

Root Cause: Database connection leak in payment validation
Recommendation: Restart payment-service-3 and check connection pooling configuration"
```

### Performance Analysis
```
Engineer: "API response times are slow today"

AskMyLogs: "API latency increased by 300% since 2 PM:
- Database query time: +150ms average
- Cache hit rate dropped from 95% to 60%
- Redis memory usage at 90%

Suggested Actions:
1. Clear Redis cache
2. Optimize database queries in user-service
3. Scale Redis cluster"
```

### Capacity Planning
```
Engineer: "Will our infrastructure handle Black Friday traffic?"

AskMyLogs: "Based on current trends and last year's data:
- Expected 10x traffic increase
- Database CPU will hit 80% (recommend scaling)
- CDN bandwidth sufficient
- Payment service needs 3 additional instances

Recommended prep: Scale database and payment service by Nov 20"
```

## 🏢 Enterprise Features

### Security & Compliance
- **Data Encryption**: AES-256 encryption at rest and in transit
- **Access Control**: SSO integration with SAML/OIDC
- **Audit Logging**: Complete audit trail for compliance
- **Data Residency**: Keep data in your preferred regions

### Scalability & Performance
- **Multi-Region Deployment**: Deploy across multiple regions
- **High Availability**: 99.9% uptime SLA
- **Auto-Scaling**: Automatic scaling based on demand
- **Performance Optimization**: Sub-second query response times

### Advanced Analytics
- **Custom ML Models**: Train models on your specific data
- **Predictive Analytics**: Forecast issues before they happen
- **Business Intelligence**: Connect observability to business metrics
- **Custom Dashboards**: Build dashboards for executives and stakeholders

## 🛠️ Development

### Local Development Setup

1. **Backend Setup**
   ```bash
   cd backend
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   python manage.py migrate
   python manage.py runserver
   ```

2. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

3. **Plugin Development**
   ```bash
   cd plugins
   python create_plugin.py --name my-tool
   # Edit plugins/my-tool/plugin.py
   ```

### Running Tests
```bash
# Backend tests
pytest backend/tests/

# Frontend tests
npm test

# Integration tests
docker-compose -f docker-compose.test.yml up
```

## 📊 Roadmap

### Q1 2025
- [x] Core platform with plugin architecture
- [x] Grafana plugin with full feature parity
- [x] Natural language query engine
- [x] Basic dashboard functionality

### Q2 2025
- [ ] DataDog and New Relic plugins
- [ ] Advanced alert correlation
- [ ] Mobile-responsive UI
- [ ] API for third-party integrations

### Q3 2025
- [ ] Predictive analytics and ML models
- [ ] Advanced RBAC and multi-tenancy
- [ ] Slack/Teams integration
- [ ] Custom plugin marketplace

### Q4 2025
- [ ] SaaS offering (cloud-hosted option)
- [ ] Advanced business intelligence features
- [ ] White-label solutions
- [ ] Enterprise support tier

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](./CONTRIBUTING.md) for details.

### Ways to Contribute
- **Plugin Development**: Add support for new observability tools
- **Feature Development**: Implement new platform features
- **Documentation**: Improve docs and examples
- **Bug Reports**: Help us identify and fix issues
- **Testing**: Write tests and improve test coverage

### Development Philosophy
- **Plugin First**: Every new tool should be a plugin
- **API First**: All features should be accessible via API
- **Security First**: Security considerations in every decision
- **Performance First**: Sub-second response times are non-negotiable

## 🙋 Support

### Community Support
- **GitHub Issues**: [Report bugs and request features](https://github.com/yourusername/askmylogs/issues)
- **Discord**: [Join our community](https://discord.gg/askmylogs)
- **Documentation**: [Comprehensive guides](https://docs.askmylogs.com)

### Enterprise Support
- **Professional Services**: Implementation and customization
- **24/7 Support**: Priority support with SLA
- **Training**: On-site training for your team
- **Custom Development**: Bespoke features and integrations

Contact: enterprise@askmylogs.com

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.


<!-- ## 🔗 Links

- **Website**: [https://askmylogs.com](https://askmylogs.com)
- **Documentation**: [https://docs.askmylogs.com](https://docs.askmylogs.com)
- **Blog**: [https://blog.askmylogs.com](https://blog.askmylogs.com)
- **Twitter**: [@AskMyLogs](https://twitter.com/askmylogs)
- **LinkedIn**: [AskMyLogs](https://linkedin.com/company/askmylogs) -->

---

**Built with ❤️ by engineers, for engineers**

*Making observability accessible to everyone, one natural language query at a time.*