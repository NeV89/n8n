🎙️ Voice CRM: n8n + Airtable + Clay Bridge

System automatyzacji typu Voice-to-CRM, który przekształca wiadomości głosowe z Telegrama w ustrukturyzowane dane biznesowe w bazie Airtable, przygotowując grunt pod wzbogacanie danych w Clay.
⚙️ Jak to działa? (Architektura)

    Ingest: Bot na Telegramie odbiera wiadomość głosową, tekstową lub zdjęcie.

    Transcription: Nagranie trafia do modelu Whisper (przez OpenAI/LM Studio), który zamienia mowę na tekst.

    Intelligence (AI): Modele LLM (Gemini 2.0 / Qwen 2.5) analizują tekst, wyciągając dane: nazwa kontrahenta, streszczenie, dane kontaktowe (email, telefon, stanowisko).

    Database Bridge: System sprawdza w Airtable, czy kontrahent już istnieje:

        Jeśli tak: Konsoliduje (łączy) nową rozmowę z istniejącą historią i aktualizuje dane kontaktowe.

        Jeśli nie: Tworzy nowy rekord.

    Clay Integration: Airtable służy jako pomost – nowe wpisy mogą automatycznie triggerować Clay w celu głębokiego researchu firmy (Enrichment).

🛠️ Stack Technologiczny

    n8n: Orkiestracja całego procesu.

    Airtable: Relacyjna baza danych i centrum operacyjne.

    LLM: Ollama (Qwen), Google Gemini, OpenAI.

    Telegram API: Interfejs wejściowy dla użytkownika.
