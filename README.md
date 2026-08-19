# 🤖 Automatyzacja Monitorowania Dotacji i Dofinansowań AI

Kompleksowy system automatyzacji procesów (BPA) stworzony w środowisku **n8n**, służący do automatycznego przeszukiwania, analizy oraz agregacji informacji o aktualnych i planowanych programach wsparcia (PARP, NFOŚiGW, fundusze regionalne).

```mermaid
graph TD
    A[Cron Trigger: Harmonogram] --> B[SerpAPI / Google Search]
    B --> C{Weryfikacja Nowych Naborów}
    C -->|Brak zmian| D[Zakończenie cyklu]
    C -->|Nowe dotacje| E[AI Agent - GPT-4o]
    E --> F[Ekstrakcja kryteriów i terminów]
    F --> G[Structured Output Parser]
    G --> H[Generowanie Raportu HTML]
    H --> I[Gmail API: Wysyłka Powiadomienia]
## 📌 Problem Biznesowy
Ręczne śledzenie harmonogramów i wymagań dotyczących dotacji (PARP, NFOŚiGW, fundusze regionalne) jest czasochłonne i niesie ryzyko przeoczenia kluczowych terminów składania wniosków.

## 🔑 Kluczowe Funkcjonalności
* **Automatyczny Monitoring:** Przeszukiwanie oficjalnych źródeł pod kątem nowych naborów.
* **Analiza Semantyczna AI:** Przetwarzanie wytycznych przez GPT-4o (alokacja, terminy, grupy docelowe).
* **Raportowanie E-mail:** Wysyłka sformatowanych zestawień HTML z bezpośrednimi linkami.

## 🛠️ Architektura i Struktura Projektu

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
│   ├── analyzer.py       # Integracja z OpenAI GPT-4o (analiza kryteriów i terminów)
│   └── reporter.py       # Generowanie szablonów HTML i przygotowanie wysyłki e-mail
├── tests/
│   └── test_analyzer.py
└── data/
    └── mock_grants.json  # Przykładowe, zanonimizowane dane wejściowe
