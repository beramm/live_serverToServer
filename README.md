#  LIVEAPI APPROACH 

## ✨ Key Features

*   **🎤 Real-time Voice:** Natural, low-latency voice conversations.
*   **🔊 Streamed Audio Output:** Hear responses instantly as they are generated.
*   **↩️ Interruptible:** Talk over the AI, just like a real conversation.
*   **📱 Responsive UI:** Includes both a development interface and a mobile-optimized view.


## 🚀 Getting Started

Choose your path: run locally for development or deploy straight to the cloud.


---

### 1. 💻 Run Locally


1.  **Clone the repo:**
    ```bash
    git clone https://github.com/beramm/live_serverToServer.git
    cd live_serverToServer
    ```

2.  **Configure Backend:**
    ```bash
    cd server
    cp .env.example .env
    nano .env # Edit with your API keys & Function URLs
    # --> See server/README.md for detailed .env options <--
    ```
    *   *Minimum required in `.env`:* `GOOGLE_API_KEY` (if not using Vertex/ADC), `WEATHER_FUNCTION_URL`, etc.

3.  **Run Backend:**
    ```bash
    pip install -r requirements.txt
    python server.py
    # Backend runs on localhost:8081
    ```

4.  **Run Frontend (in a *new* terminal):**
    ```bash
    cd ../client
    python -m http.server 8000
    # Frontend served on localhost:8000
    ```

5.  **Access:**
    *   Dev UI: `http://localhost:8000/index.html`
    *   Mobile UI: `http://localhost:8000/mobile.html`

---


##  Overview


1.  **Client (`client/`):** Vanilla JS frontend handling UI, media capture, and WebSocket connection. ([Details](./client/README.md))
2.  **Server (`server/`):** Python WebSocket server proxying to Gemini, managing sessions, and calling tools. ([Details](./server/README.md))
3.  **Gemini API:** Google's multimodal AI model accessed via the Live API.

![Architecture Diagram](assets/architecture.png)
*(User -> Client -> Server -> Gemini API / Tools -> Server -> Client -> User)*
