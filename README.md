```text
n8n-ai-grants-monitor/
├── .env.example
├── .gitignore
├── README.md
├── requirements.txt
├── config/
│   └── settings.py
├── src/
│   ├── __init__.py
│   ├── fetcher.py        # Wyszukiwanie dotacji (SerpAPI / Google Search API)
│   ├── analyzer.py       # Integracja z OpenAI GPT-4o (analiza kryteriów i krytycznych dat)
│   └── reporter.py       # Generowanie szablonów HTML i przygotowanie wysyłki e-mail
├── tests/
│   └── test_analyzer.py
└── data/
    └── mock_grants.json  # Przykładowe, zanonimizowane dane wejściowe
