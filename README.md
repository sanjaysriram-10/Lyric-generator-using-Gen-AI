
# 🎵 AI Lyrics Extractor
### _Extract and Format Song Lyrics Directly from Audio Files_

## 📘 Overview
**AI Lyrics Extractor** is a deep-learning–based tool that automatically extracts lyrics from any song or vocal audio file using **OpenAI’s Whisper model**.
It works entirely within **Google Colab**, so no API keys or paid services are required.

The model listens to your uploaded music file and generates clean, line-by-line formatted lyrics that resemble a real song sheet.

## 🚀 Features
- ✅ Upload any `.mp3`, `.wav`, `.m4a`, or `.flac` audio file
- ✅ Automatically transcribes vocals into lyrics
- ✅ Formats lyrics neatly into song-like lines
- ✅ Works 100% locally in Google Colab (no external API)
- ✅ Supports multiple languages (English, Hindi, Tamil, Spanish, etc.)
- ✅ Customizable formatting (words per line, silence gap threshold)

## 🧠 Technologies Used
- **Python 3**
- **OpenAI Whisper**
- **pydub**
- **ffmpeg**
- **Google Colab**

## ⚙️ Setup Instructions

1. **Open in Google Colab**
   - Copy the project notebook code or upload this `.py`/`.ipynb` file to your Colab workspace.

2. **Install Dependencies**
   ```python
   !pip install -q git+https://github.com/openai/whisper.git
   !pip install -q ffmpeg-python pydub
   ```

3. **Upload Your Audio File**
   ```python
   from google.colab import files
   uploaded = files.upload()
   ```
   - Select your local song file (`.mp3`, `.wav`, etc.)

4. **Run the Extractor**
   - The script will automatically:
     - Convert your song to a Whisper-compatible format
     - Transcribe the audio into lyrics
     - Clean and format the lyrics

## 📝 Example Output

**Input:** `ShapeOfYou.mp3`

**Output:**
```
🎶 Cleanly Formatted Lyrics:

01. The club isn't the best place to find a lover, so the bar is where I go.
02. Me and my friends at the table doing shots, drinking fast and then we talk slow.
03. You can start up a conversation with just me, and trust me, I'll give it a chance.
04. I'm in love with the shape of you, we push and pull like a magnet do.
05. Last night you were in my room, now my bed sheets smell like you.
...
```

## 🔧 Configuration Options

Inside the code, you can modify:
```python
smart_format_lyrics(result, max_words=12, gap_threshold=5.0)
```
- `max_words`: Maximum words per lyric line
- `gap_threshold`: Time gap (seconds) to start a new line

Example:
```python
smart_format_lyrics(result, max_words=10, gap_threshold=3.0)
```
Produces shorter lines with more lyric breaks.

## 💡 Future Enhancements
- 🌐 Auto language detection and translation to English
- 🪶 Add rhyme pattern detection
- 🎧 Integrate waveform + lyrics sync
- 📄 Export lyrics to `.txt` or `.srt` format

## 🧩 Limitations
- Accuracy depends on vocal clarity
- Noisy audio may reduce lyric quality
- Long songs (>10 min) take longer to process

