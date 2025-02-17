# Krishna Chatbot - Standard Operating Procedure (SOP)

## 📌 Introduction  
Krishna Chatbot is an AI-powered voice assistant that responds to queries in **English** and **Malayalam**. It uses **speech recognition, text-to-speech (TTS), and the GROQ API** to generate responses. The bot listens for a wake word (**"Hey Krishna" / "ഹലോ കൃഷ്ണ"**), processes user input, and provides spoken responses.  

## 🔧 Features  
- 🎤 **Voice Command Recognition** (English & Malayalam)  
- 🗣️ **Text-to-Speech (TTS)** using pyttsx4 and gtts  
- 🔍 **AI-Powered Responses** using GROQ API  
- 🔔 **Notification Sound** before listening  
- 🎶 **Audio Output** with pygame.mixer  

## 🖥️ Installation Guide  

### ✅ Windows Setup  
1. **Install Dependencies**  
   Open **Command Prompt (cmd)** and run:  
   ```
   pip install speechrecognition pyttsx4 gtts pygame numpy deep_translator requests
   ```
2. **Ensure Espeak is Installed (for pyttsx4 TTS)**  
   ```
   sudo apt install espeak
   ```
3. **Run the Script**  
   ```
   python krishna_chatbot.py
   ```

### ✅ Linux Setup  
1. **Update the System**  
   ```
   sudo apt update && sudo apt upgrade -y
   ```
2. **Install Required Packages**  
   ```
   sudo apt install python3-pip espeak ffmpeg libsdl2-mixer-2.0-0 -y
   ```
3. **Install Python Libraries**  
   ```
   pip3 install speechrecognition pyttsx4 gtts pygame numpy deep_translator requests
   ```
4. **Run the Script**  
   ```
   python3 krishna_chatbot.py
   ```

### ✅ Raspberry Pi 4 Setup  
1. **Update the System**  
   ```
   sudo apt update && sudo apt upgrade -y
   ```
2. **Install Required Packages**  
   ```
   sudo apt install python3-pip espeak ffmpeg libsdl2-mixer-2.0-0 -y
   ```
3. **Install Python Libraries**  
   ```
   pip3 install speechrecognition pyttsx4 gtts pygame numpy deep_translator requests
   ```
4. **Enable Audio and Set Permissions**  
   ```
   sudo usermod -aG audio pi
   reboot
   ```
5. **Run the Script**  
   ```
   python3 krishna_chatbot.py
   ```

## 🎙️ How to Use  
- **Paste your API key** in line **32** before running.  
- Start the chatbot by **running the script**.  
- Say **"Hey Krishna"** (English) or **"ഹലോ കൃഷ്ണ"** (Malayalam) to wake it up.  
- Ask a question, and the bot will **respond with AI-generated speech**.  
- To stop, say **"Krishna Sleep"** or **"കൃഷ്ണ സ്ലീപ്"**.  

## ⚠️ Troubleshooting  

### 🛠 Microphone Issues (Raspberry Pi)  
- Check if the microphone is detected:  
  ```
  arecord -l
  ```
- Adjust audio settings using **alsamixer**.  
- If the microphone is **not working**, try:  
  ```
  sudo nano /boot/config.txt
  ```
  Add this line at the **end**:  
  ```
  dtparam=audio=on
  ```
  Save and **reboot**.  

### 🛠 Speech Recognition Issues  
- If the bot **doesn't recognize your voice**, increase timeout in:  
  ```
  recognizer.listen(source, timeout=20)
  ```
- If Malayalam recognition is inaccurate, **update SpeechRecognition**:  
  ```
  pip install --upgrade speechrecognition
  ```

### 🛠 TTS Not Working (Pyttsx3)  
- Make sure **espeak** is installed:  
  ```
  sudo apt install espeak
  ```
- If TTS crashes, **reinstall Pyttsx3**:  
  ```
  pip uninstall pyttsx3 && pip install pyttsx3
  ```

### 🛠 No Sound Output (Raspberry Pi)  
- Set the correct **audio output**:  
  ```
  amixer cset numid=3 1  # 1 for headphones, 2 for HDMI
  ```
- Test the speaker:  
  ```
  speaker-test -t wav -c 2
  ```

## 🏆 Contributing  
Feel free to **fork** this repository and add improvements. Pull requests are welcome!  

## 📜 License  
**MIT License** – See LICENSE for details.  

🚀 **Now you're all set to use Krishna Chatbot!** 🎙️  
