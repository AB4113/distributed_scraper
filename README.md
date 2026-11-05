
distributed_scraper

A scalable, fault-tolerant distributed web crawling and scraping system designed to extract data from high-volume websites concurrently using multiple worker nodes.

✨ Features

• Distributed Architecture: Scales horizontally across multiple worker nodes to maximize data throughput.
• Centralized Task Queue: Uses a robust messaging backend to manage, schedule, and distribute scraping jobs fairly among workers.
• Resilience & Fault Tolerance: Automatically retries failed requests, handles worker crashes gracefully, and recovers pending tasks.
• Anti-Bot Mitigation: Features built-in support for proxy rotation, user-agent randomization, and configurable request throttling (politeness delay).
• Data Storage Storage Pipeline: Streamlines parsed data directly into a central database (PostgreSQL/MongoDB) or cloud storage bucket.

🚀 Quick Start


Prerequisites

• Python 3.10+
• Redis or RabbitMQ (for task orchestration)
• MongoDB or PostgreSQL (for data persistence)

Installation

1. Clone the repository:bash
git clone https://github.com
cd distributed_scraper
Use code with caution.
2. Create and activate a virtual environment:bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
Use code with caution.
3. Install dependencies:bash
pip install -r requirements.txt
Use code with caution.

💻 Usage


1. Start the Orchestrator / Message Broker

Ensure your Redis or RabbitMQ instance is running, then initialize the coordinator node:
bash
python main.py --mode coordinator --config config.yaml
Use code with caution.

2. Launch Worker Nodes

Run this command on any machine inside your network to start consuming scraping tasks:
bash
python main.py --mode worker
Use code with caution.

3. Submit a Scraping Job

bash
python submit_job.py --url "https://example.com" --depth 3
Use code with caution.

📁 Project Structure

text
distributed_scraper/
├── config/             # Configuration files (YAML/JSON)
├── src/
│   ├── broker.py       # Message broker and task queue interface
│   ├── crawler.py      # Core scraping logic and HTTP request handling
│   ├── parser.py       # HTML parsing and data extraction logic
│   ├── pipeline.py     # Database connection and data storage pipeline
│   └── worker.py       # Worker management and concurrency execution
├── requirements.txt    # Python dependencies
├── main.py             # Main system entry point
└── README.md
Use code with caution.

🤝 Contributing

Contributions, bug reports, and feature requests are welcome!
1. Fork the repository.
2. Create your feature branch (git checkout -b feature/amazing-feature).
3. Commit your changes (git commit -m 'Add some amazing feature').
4. Push to the branch (git push origin feature/amazing-feature).
5. Open a Pull Request.

📄 License

This project is licensed under the MIT License. See the LICENSE file for details.
© 2026 Abenezer Beyene
