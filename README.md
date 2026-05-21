# -
Ассистент для перевода видео и аудио в текст
# Video to Text (Whisper)

Преобразование видео в текст с помощью [OpenAI Whisper](https://github.com/openai/whisper).

## Установка

1. Установите [ffmpeg](https://ffmpeg.org/download.html) и добавьте его в PATH:
   - **Windows:** скачайте с официального сайта
   - **macOS:** `brew install ffmpeg`
   - **Linux:** `sudo apt-get install ffmpeg`

2. Клонируйте репозиторий и установите зависимости:
   ```bash
   git clone https://github.com/USERNAME/REPO.git
   cd REPO
   pip install -r requirements.txt

   # Базовый запуск
python app.py video.mp4

# С выбором модели и языка
python app.py video.mp4 --model medium --language ru --output result.txt

# Автоопределение языка
python app.py video.mp4 --language auto
