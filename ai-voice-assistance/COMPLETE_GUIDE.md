# 🎤 AI Voice Assistant - Complete Setup Guide

## ✨ Features

### **Core Capabilities**
- ✅ **Voice Recognition** - Listen and understand natural spoken commands
- ✅ **AI Powered Responses** - Uses OpenAI GPT to answer any question (Diwali festival, general knowledge, etc.)
- ✅ **Text-to-Speech** - Responds back in natural human voice
- ✅ **Continuous Listening** - Auto-starts on page load and restarts after each command
- ✅ **Real-time Transcription** - Shows what you're saying in the display box
- ✅ **System Task Execution** - Open applications, control laptop functions

### **System Tasks Supported**
- Open applications: "Open WhatsApp", "Open Chrome", "Open Notepad"
- Web browsing: "Open Google", "Open YouTube"
- Search commands: "Search for [query]"
- Time & Date: "What time is it?", "What's the date?"
- Battery status: "Check battery"
- Volume control: "Volume up", "Volume down"
- Laptop control: "Shutdown", "Restart"
- Wikipedia search: "Wikipedia [topic]"
- YouTube search: "Play [song name]"

## 🚀 How to Use

### **1. Start the Application**
```powershell
cd C:\Users\Darshan Padasalagi\OneDrive\Desktop\proj2\ai-voice-assistance\ai_voice_assistant
python app.py
```

### **2. Open in Browser**
Go to: **http://localhost:5000**

### **3. Allow Microphone Access**
- Click "Allow" when browser asks for microphone permission
- Green "START" button will be active

### **4. Using the Assistant**

**Simple Workflow:**
1. 🎤 Say "Tell me about Diwali festival"
2. ✍️ Your speech appears in the display box in real-time
3. ⚙️ Message is automatically sent to OpenAI
4. 🤖 AI generates a response
5. 🔊 Response is read aloud to you
6. 🎤 Listening automatically restarts
7. Repeat!

**Control Buttons:**
- **START (Green)** - Toggle assistant on/off (auto-starts on page load)
- **STOP (Red)** - Same function as START (toggle)

**Display Box:**
- Shows what you're saying in **real-time**
- Shows "Listening..." when ready
- Shows "Processing..." while AI responds
- Shows "Speaking..." while response is being spoken

## 🔧 Configuration

### **OpenAI API Key Setup**
1. Get key from: https://platform.openai.com/account/api-keys
2. Update `.env` file:
   ```
   OPENAI_API_KEY=sk-proj-YOUR_KEY_HERE
   ```

### **System Requirements**
- Windows 10/11
- Chrome, Edge, Firefox, or Safari browser
- Microphone connected and enabled
- Python 3.8+
- Internet connection

## 📋 Technical Architecture

### **Frontend (Web Interface)**
- **HTML/CSS** - Black theme with cyan/green accents
- **JavaScript** - Web Speech API for voice recognition
- **Socket.IO** - Real-time communication with backend
- **Two Large Buttons** - Clean, minimalist interface
- **Real-time Transcript Display** - Shows spoken text

### **Backend (Flask)**
- **Flask** - Web server
- **Flask-SocketIO** - WebSocket communication
- **OpenAI API** - GPT integration for intelligent responses
- **speech_recognition** - Voice input processing
- **pyttsx3** - Text-to-speech synthesis
- **subprocess** - System command execution
- **psutil** - System status monitoring

### **Backend Features**
- `process_web_command()` - Handles user queries
- `get_ai_response()` - Sends queries to OpenAI GPT
- System task handlers for application/file operations
- Error handling with fallback responses
- Thread-based async processing

## 🎯 Example Commands

### **Information Queries**
- "Tell me about Diwali festival"
- "Who is Albert Einstein?"
- "What is machine learning?"
- "Explain quantum computing"

### **System Control**
- "Open WhatsApp"
- "Open Google Chrome"
- "What's my battery percentage?"
- "Increase volume"
- "Shutdown the laptop"

### **Searches & Navigation**
- "Search for pizza near me"
- "Play Despacito on YouTube"
- "Wikipedia Albert Einstein"
- "Open Gmail"

## 🔄 Workflow Example

```
User: "Tell me about Diwali"
     ↓
[Voice Recognition] → "Tell me about Diwali" (displayed in box)
     ↓
[Auto-send to Backend]
     ↓
[Backend sends to OpenAI GPT]
     ↓
[OpenAI Returns Response] → "Diwali is the Festival of Lights..."
     ↓
[Text-to-Speech] → Speaks response aloud
     ↓
[Auto-restart Listening] → Ready for next command
     ↓
User: "What is Diwali celebrated for?" (cycle repeats)
```

## 📁 Project Structure

```
ai-voice-assistant/
├── ai_voice_assistant/
│   ├── app.py                 # Flask backend
│   ├── assistant.py           # AI logic & commands
│   ├── requirements.txt       # Python dependencies
│   ├── .env                   # API keys (keep private!)
│   ├── templates/
│   │   └── index.html        # Web interface
│   └── static/
│       └── styles.css        # Styling
├── README.md
└── SETUP_GUIDE.md
```

## ⚠️ Troubleshooting

### **Issue: "Microphone access denied"**
- Solution: Check browser permissions in Settings → Privacy
- Refresh page and allow microphone access

### **Issue: "No response from AI"**
- Check OpenAI API key in `.env`
- Verify internet connection
- Check API account has credits

### **Issue: "No speech detected"**
- Speak clearly and louder
- Check microphone is working
- Try refreshing the page

### **Issue: "Speech synthesis not working"**
- Browser might not support text-to-speech
- Try Chrome or Edge browser
- Check system volume is not muted

## 🎨 Customization

### **Change Voice Properties**
Edit `assistant.py`:
```python
self.engine.setProperty('rate', 180)  # Speed (default: 180)
self.engine.setProperty('voice', voices[1].id)  # 0=Male, 1=Female
```

### **Add New Commands**
Edit `assistant.py` in `process_web_command()`:
```python
elif 'your command' in command:
    return "Your custom response"
```

### **Modify UI Colors**
Edit `static/styles.css`:
```css
--accent: #00d4ff;          /* Cyan color */
--button-start: #00ff88;    /* Green color */
--button-stop: #ff4444;     /* Red color */
```

## 🔒 Security Notes
- **Never share** your OpenAI API key
- Keep `.env` file private
- Don't commit `.env` to version control
- Use minimal necessary API permissions

## 📞 Support

For issues or feature requests:
1. Check SETUP_GUIDE.md for common problems
2. Verify all dependencies are installed
3. Check API key is valid
4. Test microphone with browser's built-in mic check

## 📝 License

This project is designed for personal desktop voice assistance.

---

**Enjoy your AI Voice Assistant! 🎉**
