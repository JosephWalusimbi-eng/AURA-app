# Third-party notices

AURA's applications include or are built from the following open-source components. Each is used under its own
licence; the full licence texts are in the upstream projects.

| Component | Licence | Used for |
|---|---|---|
| OpenAI Whisper (model weights and tokenizer) | MIT | Base speech models that are adapted |
| whisper.cpp / ggml (Georgi Gerganov and contributors) | MIT | On-device speech recognition and training engine |
| openWakeWord (David Scripka) mel and speech-embedding networks; Google speech_embedding | Apache-2.0 | Wake-word features |
| Flutter and Dart (Google) and the Dart packages the app uses | BSD-3-Clause and others | Application framework |
| SQLite | Public domain | Local database |
| AfriSpeech-200 (Intron Health) | CC BY-NC-SA 4.0 | Training data for the accent adapters and the wake-word classifier (adapted models are released under the same licence) |

The adapted speech models and the wake-word classifier are released under **CC BY-NC-SA 4.0** (non-commercial use) at
https://huggingface.co/Walusimbi/whisper-afrispeech-east-africa and https://huggingface.co/Walusimbi/aura-wakeword.
The applications are free to use. Each application also lists its bundled packages' licences under its own licence
screen. If you believe a notice is missing or wrong, please open an issue.
