# 🤖 Asistente Inteligente

Asistente de escritorio **multimodal** en Python que se controla por **voz**: lee lo que hay en la pantalla (OCR), gestiona un calendario de eventos, responde preguntas con IA y habla las respuestas.

## ✨ Funcionalidades

- **Palabra de activación personalizable**: eliges el nombre (por defecto *"asistente"*) y solo responde a los comandos que empiezan con él.
- **Reconocimiento de voz** con calibración automática del ruido ambiente y reintentos.
- **Análisis de pantalla**: captura la pantalla y extrae el texto con OCR.
- **Vigilancia de capturas**: detecta pantallazos nuevos en una carpeta, extrae su texto y guarda un resumen que luego se puede buscar.
- **Calendario por voz**: crear, editar, eliminar y consultar eventos ("¿qué tengo hoy?", "¿qué tengo esta semana?").
- **Preguntas a la IA** (OpenAI) con respuesta hablada.
- **Síntesis de voz** (pyttsx3 / gTTS) y un panel gráfico con Tkinter.

### Comandos

`analizar pantalla` · `crear evento` · `editar evento` · `eliminar evento` · `qué tengo hoy` · `qué tengo esta semana` · `pregunta <texto>` · `panel` · `salir`

## 🛠️ Tecnologías

Python · SpeechRecognition · PyAudio · pyttsx3 · gTTS · OpenCV · mss · NumPy · watchdog · Tkinter · API de OCR.space · API de OpenAI

## 🚀 Instalación

```bash
git clone https://github.com/juanromanbedoya/asistente-inteligente.git
cd asistente-inteligente
python -m venv venv
venv\Scripts\activate          # Windows  (Linux/macOS: source venv/bin/activate)
pip install -r requirements.txt
```

Para las preguntas a la IA, define tu clave de OpenAI:

```bash
set OPENAI_API_KEY=tu_clave        # Windows (PowerShell: $env:OPENAI_API_KEY="tu_clave")
```

Ejecuta:

```bash
python src/main.py
```

> Necesitas micrófono. Si `pyaudio` falla al instalarse en Windows, prueba con `pip install pipwin && pipwin install pyaudio`.

## 📁 Estructura

| Archivo | Responsabilidad |
|---|---|
| `src/main.py` | Orquestador: palabra de activación y despacho de comandos |
| `src/voz.py` | Escucha (speech-to-text) y habla (text-to-speech) |
| `src/vision.py` | Captura de pantalla y OCR |
| `src/asistente.py` | Vigilancia de pantallazos, resúmenes y búsqueda |
| `src/calendario.py` | CRUD de eventos (`resumenes/eventos.json`) |
| `src/ia.py` | Preguntas a la IA |
| `src/interfaz.py` | Panel gráfico |
| `Asistente_Inteligente_Documento_Tecnico (1).docx` | Documento técnico del proyecto |
| `pasos a seguir` | Hoja de ruta por fases |

## 👥 Autores

- **Juan José Román Bedoya** ([@juanromanbedoya](https://github.com/juanromanbedoya))
- **Jose David Osorio Gallego** ([@josedavidosorio2005](https://github.com/josedavidosorio2005))
