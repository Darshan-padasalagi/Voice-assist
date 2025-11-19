# Testing Guide for AI Voice Assistant

## 🔍 Diagnostic Steps

### Step 1: Check Server is Running
```
✅ Should see: Running on http://127.0.0.1:5000
```

### Step 2: Check Browser Console
**Open Developer Tools:**
- Press `F12` in Chrome/Edge
- Go to **Console** tab
- You should see logs like:
  - `📱 Browser Speech Recognition available: true`
  - `🔊 Browser Speech Synthesis available: true`
  - `🔌 Initializing Socket.IO connection`
  - `✅ SOCKET CONNECTED`

### Step 3: Test Speech Recognition
- Wait for page to say "I'm ready to help you"
- Speak something like "Tell me about Diwali"
- In Console, you should see:
  - `📢 SENDING MESSAGE: Tell me about Diwali`
  - On the server terminal: `📨 RECEIVED MESSAGE`
  - Server then processes and responds

### Step 4: Test Voice Output
- After server responds, you should:
  - See message in chat
  - Hear AI speak the response
  - See logs like:
    - `🔵 RECEIVED ASSISTANT MESSAGE`
    - `🔊 Starting speech synthesis`
    - `🔊 Speech started`
    - `🔊 Speech ended`

## ❌ Common Issues & Solutions

### Issue: "Always Listening, No Response"

#### Check 1: Are Socket logs appearing?
```
❌ Missing: ✅ SOCKET CONNECTED
Fix: Hard refresh browser (Ctrl+Shift+R)
```

#### Check 2: Is microphone permission granted?
```
❌ Missing: Speech recognized in console
Fix: Check browser address bar for microphone icon
     Click and select "Allow" for microphone access
```

#### Check 3: Is voice input working?
```
Expected in Console: 📢 SENDING MESSAGE: [your text]
If missing: Microphone not working or browser issue
Fix: Try Chrome/Edge browser
```

#### Check 4: Is server receiving messages?
```
Check Server Terminal for: 📨 RECEIVED MESSAGE
If missing: Socket.IO connection failed
Fix: Check browser console for connection errors
```

#### Check 5: Is OpenAI API key valid?
```
Server logs show: 🤖 Got response: [text]
If missing: API key issue or rate limit
```

#### Check 6: Is browser speech synthesis working?
```
Console should show: 🔊 Starting speech synthesis
Then: 🔊 Speech started
Then: 🔊 Speech ended
If missing: TTS not working, check browser volume
```

## 🔧 Quick Fixes

### Fix 1: Hard Refresh Browser
```
Windows/Linux: Ctrl + Shift + R
Mac: Cmd + Shift + R
```

### Fix 2: Check Microphone
1. Go to Windows Settings
2. Privacy → Microphone
3. Make sure Chrome/Browser is "On"

### Fix 3: Check Browser Audio Output
1. Make sure volume is not muted
2. Try different browser (Chrome recommended)

### Fix 4: Restart Server
```powershell
# Kill old server (Ctrl+C in terminal)
# Restart
cd "c:\Users\Darshan Padasalagi\OneDrive\Desktop\proj2\ai-voice-assistance\ai_voice_assistant"
python app.py
```

### Fix 5: Check API Key
1. Open `.env` file in `ai_voice_assistant/` folder
2. Verify `OPENAI_API_KEY=sk-proj-...` is present
3. If not, get key from https://platform.openai.com/account/api-keys

## 🧪 Test Phrases

Try these to test different features:

1. **General Knowledge**
   - "Tell me about the Taj Mahal"
   - "Who is Elon Musk?"
   - "Explain artificial intelligence"

2. **System Commands**
   - "What time is it?"
   - "Check my battery"
   - "Volume up"

3. **Web Commands**
   - "Open Google"
   - "Open YouTube"
   - "Search for Python tutorials"

## 📊 Expected Behavior

### ✅ Correct Flow:
1. Page loads → Hears "I'm ready to help you"
2. You speak → Text appears in real-time
3. Text auto-sends → See "Processing..." status
4. Server responds → Text appears in chat (Ava)
5. AI speaks response → Hear natural voice
6. Auto-listens → Ready for next command

### ❌ Wrong Flow to Fix:
- **No greeting**: Socket not connected
- **Text doesn't send**: Microphone/speech recognition issue
- **No server response**: OpenAI API issue or server error
- **No voice output**: Browser TTS issue or volume muted

## 🆘 If Nothing Works

1. **Check Console (F12)**
   - Look for red error messages
   - Screenshot and check details

2. **Check Server Logs**
   - Look for ❌ errors with timestamps

3. **Check Browser Compatibility**
   - Chrome ✅ (Recommended)
   - Edge ✅
   - Firefox ✅
   - Safari ✅
   - IE ❌ (Not supported)

4. **Restart Everything**
   - Close browser
   - Stop server (Ctrl+C)
   - Restart server
   - Open browser fresh

---

**🚀 Once working, you can:**
- Ask any question and get AI responses
- Control your system with voice
- Open applications
- Search the web
- And much more!
