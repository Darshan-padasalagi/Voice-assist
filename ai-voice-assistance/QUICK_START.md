# 🚀 Quick Start - AI Voice Assistant

## **5-Minute Setup**

### **Step 1: Start the Server**
```powershell
cd C:\Users\Darshan Padasalagi\OneDrive\Desktop\proj2\ai-voice-assistance\ai_voice_assistant
python app.py
```

### **Step 2: Open in Browser**
Visit: **http://localhost:5000**

### **Step 3: Allow Microphone**
Click **"Allow"** when browser asks

### **Step 4: Start Speaking!**
- 🎤 Say: "Tell me about Diwali festival"
- ✍️ Watch your words appear in the box
- 🤖 AI responds with voice
- 🎯 Automatically listens again

---

## **What You Can Ask**

### **General Knowledge**
- "Tell me about Diwali"
- "Who is Elon Musk?"
- "What is artificial intelligence?"
- "Explain photosynthesis"

### **System Control**
- "Open WhatsApp"
- "Open Google Chrome"
- "What time is it?"
- "Shutdown the computer"

### **Search & Browse**
- "Search for pizza"
- "Play Despacito"
- "Wikipedia Python"
- "Open Gmail"

---

## **Button Controls**

| Button | Action |
|--------|--------|
| 🟢 START | Turn assistant ON/OFF |
| 🔴 STOP | Turn assistant ON/OFF |

Both buttons do the same thing - they toggle the assistant.

---

## **Display Box**

Shows what you're saying in **real-time** as you speak:
- **"Listening for your voice..."** → Ready to listen
- **"Your actual speech..."** → What you said (updating live)
- **"Processing..."** → AI is thinking
- **"Speaking..."** → AI is responding

---

## **Important: API Key Setup**

⚠️ **This is essential for the AI to work!**

1. Go to: https://platform.openai.com/account/api-keys
2. Sign up or log in
3. Create a new API key
4. Open `.env` file in the project folder
5. Replace:
   ```
   OPENAI_API_KEY=sk-proj-YOUR_ACTUAL_API_KEY_HERE
   ```

---

## **Green vs Red Button**

- **🟢 GREEN START**: Microphone is ACTIVE (listening)
- **🔴 RED STOP**: Press to turn OFF
- Both buttons toggle the same function

**Default State**: Green button is ACTIVE when page loads
- Assistant starts listening automatically
- Just speak naturally into your microphone!

---

## **Workflow**

```
1. Page loads → Green button ACTIVE → Automatically listening
2. You speak → Text appears in box → Auto-sends
3. AI thinks → "Processing..." shown
4. AI speaks → Your message displayed in chat
5. Auto-listens again → Ready for next command
6. You speak again → Repeat!
```

---

## **Troubleshooting**

**"Button doesn't work?"**
- Refresh the page
- Check microphone in system settings

**"No response from AI?"**
- Verify API key in `.env` file
- Check internet connection

**"Can't hear response?"**
- Check system volume (not muted)
- Try different browser

---

## **Stop the Server**

Press **CTRL + C** in the terminal

---

**Ready to chat with AI? Let's go! 🚀**
