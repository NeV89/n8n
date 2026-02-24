## 🚀 Enterprise Local AI Infrastructure (On-Premise)
System lokalnej infrastruktury AI, zaprojektowany z myślą o prywatności danych i wydajności obliczeniowej na potrzeby firmowe.

### ⚙️ Architektura i Stack Techniczny
Infrastruktura oparta na dedykowanej stacji roboczej **NVIDIA RTX 5090 (32GB VRAM)**, zoptymalizowana pod kątem modeli o parametrach 32B-70B.

* **Orkiestracja:** n8n (Self-hosted via Docker).
* **Modele LLM:**
* **Bazy danych:** Supabase (PostgreSQL + pgvector) oraz Qdrant (Vector Store).
* **Obserwowalność:** Langfuse (Monitoring śladów AI, latencji i zużycia tokenów).
* **System:** Ubuntu 24.04 LTS z optymalizacją PCIe 5.0 oraz Re-Size BAR.

### 🛠️ Główne Funkcjonalności
1.  **Lokalny RAG (Retrieval-Augmented Generation):** Hybrydowe wyszukiwanie danych łączące zapytania SQL z przeszukiwaniem wektorowym.
2.  **Pełna Prywatność:** Żadne dane firmowe nie opuszczają sieci lokalnej.
3.  **Monitoring Wydajności:** Pełny tracing procesów myślowych agentów w Langfuse, pozwalający na debugowanie promptów w czasie rzeczywistym.
