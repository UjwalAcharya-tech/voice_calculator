# AI Voice Calculator Pro

A Flask-based calculator that accepts voice and keyboard input for mathematical expressions.

## Setup

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the app:**
   
   **Option A: localhost (Simplest - Recommended)**
   ```bash
   python app.py
   ```
   Then open: `http://localhost:5000`

   **Option B: With HTTPS (for external IP access)**
   ```bash
   USE_HTTPS=1 python app.py
   ```
   Then open: `https://127.0.0.1:5000` (ignore certificate warning)

## Troubleshooting Voice Input

### "Voice service unreachable" / "network" error

The Web Speech API requires a **secure context**. This means:

- ✅ **Works:** `http://localhost:5000` or `http://127.0.0.1:5000`
- ✅ **Works:** `https://any-url.com` (with valid HTTPS)
- ❌ **Doesn't work:** `http://192.168.x.x:5000` (non-localhost HTTP)

**Solutions:**
1. Use `http://localhost:5000` instead of IP addresses
2. Or enable HTTPS: `USE_HTTPS=1 python app.py` then use `https://127.0.0.1:5000`

### Microphone blocked error

Click the permission icon in your browser's address bar and allow microphone access.

### "No browser support" error

The Web Speech API only works in Chromium-based browsers (Chrome, Edge, Opera).

## Features

- **Voice input:** Speak math expressions naturally (e.g., "twenty one times four")
- **Keyboard input:** Type expressions with operators
- **Safe evaluation:** Expressions are validated using AST to prevent code injection
- **Voice output:** Results are read aloud using text-to-speech
- **Calculation history:** Last 6 calculations are displayed
