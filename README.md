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
