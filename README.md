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


Параметр	Описание	По умолчанию
video	Путь к видеофайлу	—
-m, --model	Размер модели: tiny / base / small / medium / large	base
-l, --language	Язык (ru, en, auto)	ru
-o, --output	Файл для сохранения текста	transcription.txt


Модель	VRAM	Скорость
tiny	~1 GB	очень быстро
base	~1 GB	быстро
small	~2 GB	средне
medium	~5 GB	медленно
large	~10 GB	очень медленно, максимальная точность


## 🔑 Что изменилось по сравнению с Colab-версией:

| Было (Colab) | Стало (GitHub) |
|--------------|----------------|
| `!pip install ...` | Перенесено в `requirements.txt` |
| `!apt-get install ffmpeg` | Инструкция в README (ставится в систему) |
| `drive.mount()` | Удалено |
| `files.upload()` / `files.download()` | Заменено на аргументы командной строки |
| `input(...)` для путей | Аргументы через `argparse` |
| `!ffmpeg ...` (shell-магия) | `subprocess.run([...])` |
| Жёстко прописанный путь `/content/...` | Относительные пути |

## 🚀 Пример запуска после клонирования с GitHub:

```bash
pip install -r requirements.txt
python app.py my_video.mp4 --model medium --language ru
