# STT & TTS Prototyping Detailed Plan

**Date:** March 2, 2026
**Purpose:** Prototyping infrastructure for Speech-to-Text and Text-to-Speech activities
**For:** Aslam's AI Solopreneur Business

---

## 1. SPEECH-TO-TEXT (STT) - Open Source Options

### Top Recommendations

| Model | Accuracy | Speed | Size | Best For |
|-------|----------|-------|------|----------|
| **Whisper (OpenAI)** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | Large (1.5GB) | High accuracy, multilingual |
| **Whisper.cpp** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Small (75MB) | Local/edge deployment |
| **Coqui STT** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Medium (500MB) | Custom fine-tuning |
| **Vosk** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Tiny (50MB) | Lightweight, fast |

### Selected Stack: Whisper.cpp (Production)
- **Why:** Fast, accurate, runs locally, no API costs
- **Model size:** base (75MB) or large (600MB)
- **GitHub:** https://github.com/ggerganov/whisper.cpp

### Alternative: Whisper (Python)
- **Why:** Easiest to start with
- **Install:** `pip install openai-whisper`
- **Usage:** 3 lines of code

---

## 2. TEXT-TO-SPEECH (TTS) - Open Source Options

### Top Recommendations

| Model | Quality | Speed | Size | Best For |
|-------|---------|-------|------|----------|
| **Coqui TTS** | ⭐⭐⭐⭐ | ⭐⭐⭐ | Large | High quality, custom voices |
| **Piper** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Tiny (100MB) | Fast, low resource |
| **XTTS v2** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | Large | Voice cloning, multilingual |
| **MeloTTS** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Medium | Fast, good quality |
| **VALL-E X** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | Large | Zero-shot voice cloning |

### Selected Stack: Piper (Primary) + Coqui TTS (Advanced)
- **Piper:** For fast, lightweight TTS
- **Coqui TTS:** For high-quality, voice cloning needs
- **GitHub (Piper):** https://github.com/rhasspy/piper
- **GitHub (Coqui):** https://github.com/coqui-ai/TTS

---

## 3. PROTOTYPE ARCHITECTURE

```
┌─────────────────────────────────────────────────────────────┐
│                      USER INTERFACE                         │
│                  (Discord / Web / API)                      │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                      BACKEND API                            │
│                    (FastAPI / Flask)                        │
└─────────────────────┬───────────────────────────────────────┘
                      │
          ┌───────────┴───────────┐
          ▼                       ▼
┌─────────────────────┐   ┌─────────────────────┐
│     STT MODULE      │   │     TTS MODULE      │
│   (Whisper.cpp)    │   │     (Piper)         │
│                     │   │                     │
│ Audio → Text        │   │ Text → Audio        │
└─────────────────────┘   └─────────────────────┘
```

---

## 4. DETAILED IMPLEMENTATION STEPS

### Phase 1: Local Development (Week 1)

**Day 1-2: Environment Setup**
```bash
# Python environment
python -m venv stt_tts_env
source stt_tts_env/bin/activate

# Install Whisper
pip install openai-whisper

# Install Piper
pip install piper-tts

# Install Coqui TTS (optional)
pip install coqui-tts
```

**Day 3-4: STT Implementation**
```python
import whisper

# Load model (base for speed, large for accuracy)
model = whisper.load_model("base")

# Transcribe audio
result = model.transcribe("audio_file.mp3")
print(result["text"])
```

**Day 5-7: TTS Implementation**
```python
# Using Piper
from piper_tts import PiperTTS

tts = PiperTTS(model="en_US-lessac-medium")
tts.say("Hello, this is a test!")
```

### Phase 2: API Development (Week 2)

**FastAPI Server:**
```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class TextInput(BaseModel):
    text: str

@app.post("/tts")
async def text_to_speech(input: TextInput):
    # Convert to audio
    audio = tts.say(input.text)
    return {"audio": audio}

@app.post("/stt")
async def speech_to_text(audio: bytes):
    # Transcribe
    result = model.transcribe(audio)
    return {"text": result["text"]}
```

### Phase 3: Discord Integration (Week 3)

**Voice Bot Features:**
- Join voice channels
- Listen and transcribe speech
- Convert text responses to speech
- Play audio in voice channel

### Phase 4: Production Deployment (Week 4)

**Hosting Options:**
| Option | Cost | Performance |
|--------|------|-------------|
| **Local (Raspberry Pi)** | $50 one-time | Good for personal |
| **Cloud VPS (Hetzner)** | €4/month | Great for production |
| **Docker + GPU** | $20/month | Best performance |

---

## 5. RECOMMENDED INFRASTRUCTURE STACK

### For Aslam's Use Case (Discord Bot + Content)

| Component | Technology | Cost |
|-----------|------------|------|
| **STT** | Whisper.cpp (local) | Free |
| **TTS** | Piper (local) | Free |
| **Backend** | FastAPI + Python | Free |
| **Hosting** | Hetzner VPS (€4/mo) | €4/month |
| **Storage** | Local SSD | Included |
| **Total** | | **€4/month** |

---

## 6. QUICK START COMMANDS

### Install Everything
```bash
# Create project
mkdir stt-tts-bot && cd stt-tts-bot

# Python + Whisper + Piper
pip install openai-whisper piper-tts fastapi uvicorn

# Download Piper model
python -m piper_tts.download_model.en_US-lessac-medium
```

### Test STT
```bash
# Record audio
arecord -f cd -d 5 test.wav

# Transcribe
python -c "import whisper; print(whisper.load_model('base').transcribe('test.wav')['text'])"
```

### Test TTS
```bash
# Generate speech
echo "Hello world" | python -m piper_tts -m en_US-lessac-medium.onnx -f output.wav

# Play audio
aplay output.wav
```

---

## 7. NEXT STEPS

1. ✅ Plan created
2. ⬜ Set up local development environment
3. ⬜ Test Whisper (STT)
4. ⬜ Test Piper (TTS)
5. ⬜ Build FastAPI wrapper
6. ⬜ Integrate with Discord
7. ⬜ Deploy to VPS

---

*Plan ready for implementation*
