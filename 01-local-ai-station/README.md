## 🚀 Enterprise Local AI Infrastructure (On-Premise)
System lokalnej infrastruktury AI klasy Enterprise, zaprojektowany z myślą o prywatności danych i maksymalnej wydajności obliczeniowej.

### ⚙️ Architektura i Stack Techniczny
Infrastruktura oparta na dedykowanej stacji roboczej **NVIDIA RTX 5090 (32GB VRAM)**, zoptymalizowana pod kątem modeli o parametrach 32B-70B.

* **Orkiestracja:** n8n (Self-hosted via Docker).
* **Modele LLM:** Ollama (DeepSeek-R1 32B, Qwen 2.5 32B).
* **Bazy danych:** Supabase (PostgreSQL + pgvector) oraz Qdrant (Vector Store).
* **Obserwowalność:** Langfuse (Monitoring śladów AI, latencji i zużycia tokenów).
* **System:** Ubuntu 24.04 LTS z optymalizacją PCIe 5.0 oraz Re-Size BAR.

### 🛠️ Główne Funkcjonalności
1.  **Lokalny RAG (Retrieval-Augmented Generation):** Hybrydowe wyszukiwanie danych łączące zapytania SQL z przeszukiwaniem wektorowym.
2.  **Pełna Prywatność:** Żadne dane firmowe (prompty, dokumenty, dane klientów) nie opuszczają sieci lokalnej.
3.  **Monitoring Wydajności:** Pełny tracing procesów myślowych agentów w Langfuse, pozwalający na debugowanie promptów w czasie rzeczywistym.

### 📊 Benchmark (RTX 5090)
* **Model:** Mistral Small 3.2 (Lokalnie)
* **Średnia Latencja:** 2.7s (pełny cykl agenta z narzędziami)
* **VRAM Usage:** ~19GB / 32GB`
