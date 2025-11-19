# ⚡ Quick Start - Test Now!

## 30-Second Setup

### Step 1️⃣: Make Sure Server is Running
In PowerShell, run:
```powershell
cd "c:\Users\Darshan Padasalagi\OneDrive\Desktop\proj2\ai-voice-assistance\ai_voice_assistant"
python app.py
```

You should see:
```
Starting server...
Running on http://127.0.0.1:5000
```

### Step 2️⃣: Open Chrome/Edge Browser
```
URL: http://localhost:5000
```

### Step 3️⃣: Allow Microphone
- Click "Allow" when browser asks for microphone permission

### Step 4️⃣: Wait for Greeting
- You should **HEAR**: "I'm ready to help you. What can I do for you?"
- If you don't hear it, see **TROUBLESHOOTING** below

### Step 5️⃣: Speak Your Command
Say: "Tell me about Diwali"

### Step 6️⃣: You Should See & Hear
1. ✅ Your speech appears in the text box in real-time
2. ✅ Your message appears in the chat (green, on the right)
3. ✅ AI response appears in the chat (cyan, on the left)
4. ✅ **You HEAR the AI speak the response**
5. ✅ Automatically ready for next command

---

## 🎯 Test Commands

Try these commands and they should work:

### Information
- "Tell me about Taj Mahal"
- "What is machine learning?"
- "Who is Albert Einstein?"

### System Info
- "What time is it?"
- "What is today's date?"
- "Check battery status"

### Web/Apps
- "Open Google"
- "Open YouTube"
- "Open Chrome"

### Other
- "Volume up"
- "Search for Python"

---

## ❌ Troubleshooting

### Problem: No Greeting Heard on Page Load

**Check List:**

1. **Is it a REAL browser?**
   - ❌ VS Code Simple Browser (doesn't work)
   - ✅ Chrome, Edge, Firefox, Safari
   
   → **Fix**: Open http://localhost:5000 in Chrome/Edge

2. **Is browser console showing errors?**
   - Press `F12`
   - Go to **Console** tab
   - Look for red errors
   
   → **Fix**: Hard refresh: `Ctrl+Shift+R`

3. **Is microphone permission granted?**
   - Look at browser address bar
   - Should show microphone icon
   
   → **Fix**: Click icon → Select "Allow"

4. **Is volume muted?**
   - Check system volume in taskbar
   - Make sure not muted
   
   → **Fix**: Unmute and increase volume

5. **Did you wait long enough?**
   - Sometimes takes 1-2 seconds
   - Check console for connection logs
   
   → **Fix**: Wait 3 seconds after page loads

### Problem: You Speak But Nothing Happens

**Check List:**

1. **Is microphone working?**
   - Click START button
   - Say "Hello"
   - Does text appear in the box?
   
   → **Fix**: If no text appears, microphone not detected
   - Windows Settings → Privacy → Microphone → Allow browser

2. **Is the message being sent?**
   - Open Console (F12)
   - Speak something
   - Do you see: `📢 SENDING MESSAGE: ...`?
   
   → **Fix**: If not, WebSocket not connected
   - Hard refresh: `Ctrl+Shift+R`

3. **Is the server receiving it?**
   - Look at server terminal
   - Should show: `📨 RECEIVED MESSAGE: ...`
   
   → **Fix**: If not, server might have crashed
   - Restart: Stop server (Ctrl+C) and run again

### Problem: Server Responds But No Voice Output

**Check List:**

1. **Does message appear in chat?**
   - Should see green (you) and cyan (AI) messages
   
   → **Fix**: If no message, API issue (see next section)

2. **Is browser volume up?**
   - Check system volume
   - Make sure not muted
   
   → **Fix**: Increase volume

3. **Is speech synthesis working?**
   - Open Console (F12)
   - Look for: `🔊 Starting speech synthesis`
   
   → **Fix**: If not showing:
   - Try different browser (Chrome recommended)
   - Check Windows sound settings

### Problem: "I'm having trouble processing your request" Error

**This means API issue:**

1. **Is OpenAI API key valid?**
   - Open file: `ai_voice_assistant/.env`
   - Check line: `OPENAI_API_KEY=sk-proj-...`
   - Should have actual key, not placeholder
   
   → **Fix**: Get real API key from:
   - https://platform.openai.com/account/api-keys
   - Replace in .env file
   - Restart server

2. **Do you have API credits?**
   - Go to: https://platform.openai.com/account/usage
   - Should show available credits
   
   → **Fix**: If no credits, add payment method

3. **Is API rate limit hit?**
   - Try again after a few seconds
   
   → **Fix**: Wait and retry

---

## 📊 Console Debugging

**Open Console with F12 and look for these patterns:**

### ✅ GOOD - Healthy Connection:
```
📱 Browser Speech Recognition available: true
🔊 Browser Speech Synthesis available: true
🔌 Initializing Socket.IO connection
✅ SOCKET CONNECTED
📨 Emitting start_listening event
```

### ❌ BAD - Socket Not Connected:
```
🔌 Initializing Socket.IO connection
[nothing after this]
```

**Fix**: Hard refresh or restart server

### ❌ BAD - Message Not Sending:
```
📢 SENDING MESSAGE: [text]
[nothing after this]
```

**Fix**: Check socket connection or server logs

### ❌ BAD - No Speech Synthesis:
```
🔵 RECEIVED ASSISTANT MESSAGE: [text]
[no 🔊 logs after]
```

**Fix**: Check volume or try different browser

---

## 🎵 Audio Setup Check

Before troubleshooting, verify your audio:

1. **Is anything playing?**
   - Open YouTube, play any video
   - Do you hear sound?
   
   → **Fix**: If no sound, Windows audio issue

2. **Is microphone working?**
   - Open Voice Recorder app
   - Record something
   - Play back
   
   → **Fix**: If can't record, microphone issue

3. **Can browser access microphone?**
   - Windows Settings
   - Privacy & Security
   - Microphone
   - Make sure app has permission
   
   → **Fix**: Toggle permission off/on

---

## ⚡ Quick Fixes (Try These First)

### Fix 1: Hard Refresh Browser
```
Windows: Ctrl + Shift + R
Mac: Cmd + Shift + R
```

### Fix 2: Restart Server
```powershell
# Press Ctrl+C to stop
# Then run:
cd "c:\Users\Darshan Padasalagi\OneDrive\Desktop\proj2\ai-voice-assistance\ai_voice_assistant"
python app.py
```

### Fix 3: Clear Browser Cache
- Chrome: Ctrl+Shift+Delete → Select "All time" → Delete

### Fix 4: Try Different Browser
```
Chrome (Best) > Edge > Firefox > Safari
```

### Fix 5: Check API Key
```
1. Open: ai_voice_assistant/.env
2. Replace: OPENAI_API_KEY=sk-proj-YOUR_ACTUAL_KEY
3. Restart server
```

---

## ✅ Success Checklist

After fixes, verify:

- [ ] Server running with no errors
- [ ] Browser is Chrome/Edge/Firefox
- [ ] Page loaded and greeting heard
- [ ] Microphone permission granted
- [ ] Console shows: ✅ SOCKET CONNECTED
- [ ] Can speak and text appears in real-time
- [ ] Message sends (console shows: 📢 SENDING MESSAGE)
- [ ] Server responds (server logs show: 📨 RECEIVED MESSAGE)
- [ ] AI message appears in chat
- [ ] AI voice heard (console shows: 🔊 Speech started/ended)
- [ ] Auto-listening ready for next command

---

## 🎉 If Everything Works!

You now have a fully functional **AI Voice Assistant** that:

✅ Listens to your voice continuously
✅ Understands natural language
✅ Responds with AI (GPT)
✅ Speaks responses aloud
✅ Performs system tasks (open apps, check time, etc.)
✅ No manual interactions needed

**Try these:**
- "Tell me about space exploration"
- "What's the weather like?" (if integrated)
- "Open YouTube"
- "What time is it?"
- "Play my favorite music"

---

**Need more help?** Check `FIXED_ISSUES.md` or `TEST_VOICE.md` for detailed info.
