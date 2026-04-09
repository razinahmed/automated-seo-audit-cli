# Automated SEO Audit CLI

> Command-line tool for automated SEO audits -- check meta tags, performance, accessibility, and link health.

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![CLI](https://img.shields.io/badge/Interface-CLI-lightgrey)
![License](https://img.shields.io/badge/License-MIT-green)

## Overview

Automated SEO Audit CLI is a command-line tool that performs comprehensive SEO audits on any website. It checks for missing meta descriptions, broken links, page speed issues, accessibility problems, and other common SEO deficiencies. Results are returned as structured JSON with scores and actionable issue reports.

## Features

- Meta tag analysis (title, description, Open Graph, Twitter Cards)
- SEO score calculation (0-100 scale)
- Issue detection with specific recommendations
- Structured JSON output for easy parsing
- Fast, lightweight CLI interface
- Batch URL auditing support

## Tech Stack

- **Language**: Python 3.9+
- **HTTP**: Requests / urllib
- **Parsing**: BeautifulSoup / lxml
- **Output**: JSON
- **Build**: Makefile

## Quick Start

```bash
# Clone the repository
git clone https://github.com/razinahmed/automated-seo-audit-cli.git
cd automated-seo-audit-cli

# Install dependencies
pip install requests beautifulsoup4

# Run an audit
python src/audit.py
```

## API Reference

```python
from src.audit import check_seo

result = check_seo("https://example.com")
print(result)
# Output: {'score': 85, 'issues': ['Missing meta description']}
```

## Project Structure

```
automated-seo-audit-cli/
├── src/
│   └── audit.py        # Core SEO auditing engine
├── Makefile            # Build and test commands
├── LICENSE             # MIT License
├── SECURITY.md         # Security policy
└── README.md           # Project documentation
```

## Output Format

The audit returns a JSON object with the following structure:

```json
{
  "score": 85,
  "issues": [
    "Missing meta description",
    "No Open Graph tags found",
    "Images missing alt attributes"
  ]
}
```

## Checks Performed

| Check | Category | Description |
|-------|----------|-------------|
| Meta title | On-page | Presence and length of title tag |
| Meta description | On-page | Presence and length of meta description |
| Open Graph tags | Social | OG title, description, and image tags |
| Heading hierarchy | Structure | Proper H1-H6 tag ordering |
| Image alt text | Accessibility | Alt attributes on all images |
| Broken links | Link health | HTTP status of internal and external links |

## Use Cases

- Pre-launch website SEO validation
- Continuous SEO monitoring in CI/CD pipelines
- Competitor SEO benchmarking
- Content audit for existing websites

## Contributing

Contributions are welcome. Fork the repository, create a feature branch, and submit a pull request.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
