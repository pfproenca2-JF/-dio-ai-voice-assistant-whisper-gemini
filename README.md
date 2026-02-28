🤖 AI Voice Assistant: Multilingual Speech-to-Text & Text-to-Speech Pipeline

📝 Project Overview

This project implements a complete conversational AI pipeline. The system is designed to capture audio, transcribe it using state-of-the-art ASR (Automatic Speech Recognition), process the intent via a Large Language Model (LLM), and generate a natural voice response.

🚀 Tech Stack

 * Speech-to-Text (STT): OpenAI Whisper (Robust multilingual transcription).
 * Large Language Model (LLM): Google Gemma-3-27b-it (Contextual reasoning and intent processing).
 * Text-to-Speech (TTS): Google gTTS (Neural speech synthesis).
 * Environment: Python 3.x / Google Colab.
   
🛠️ Technical Troubleshooting & Engineering Log

During development, the project faced several infrastructure and integration challenges. Below is the technical log of how they were resolved:

| Technical Challenge | Root Cause | Engineering Solution |
|---|---|---|
| API Rate Limiting (429) | Exceeded OpenAI's free tier quota/credits. | Failover Strategy: Switched the core LLM engine to Google Gemini API for higher throughput. |
| Model Endpoint 404 | Deprecated model versions or restricted access to legacy endpoints (gemini-1.5-flash). | Model Auditing: Performed list_models() and updated the pipeline to use the Google Gemma-3-27b-it  stable release. |
| Environment Dependency | ModuleNotFoundError for the gTTS library in the cloud runtime. | Dynamic Provisioning: Implemented automated package installation using !pip install gTTS in the deployment script. |
| Quota Exhaustion (Gemini) | Per-minute token limits on the Gemini Free Tier. | Resilience Logic: Developed a Retry/Backoff algorithm with a 35-second cooldown to ensure system availability. |

🧠 Professional Soft Skills Applied

 * Problem-Solving: Analytical approach to debugging complex API interaction errors and logs.
 * Adaptability: Ability to pivot between different AI frameworks and providers mid-project to maintain system uptime.
 * Technical Documentation: Clear mapping of the development lifecycle, ensuring maintainability and transparency.
 * Persistence: Iterative testing and optimization of the pipeline until achieving a stable end-to-end flow.
