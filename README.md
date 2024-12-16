Transcripción Automática de Audio con Whisper y Python

Este repositorio contiene un script en Python para transcribir archivos de audio en formato MP4 a texto, utilizando el modelo Whisper de OpenAI y la biblioteca de Transformers de Hugging Face. El script realiza varias tareas, incluyendo la conversión de audio, segmentación basada en silencios, transcripción de audio y guardado de resultados en un documento de Word.

Características

Conversión de audio: Convierte archivos MP4 a WAV utilizando FFmpeg y la biblioteca Pydub.

Segmentación por silencios: Divide el archivo de audio en fragmentos basándose en los silencios detectados.

División de fragmentos largos: Divide fragmentos largos en subfragmentos más manejables (por ejemplo, de 30 segundos).

Transcripción de audio: Utiliza el modelo Whisper de OpenAI para convertir audio en texto.

Guardado en Word: Transcribe el texto directamente a un documento de Word, organizando los fragmentos de manera secuencial.

Compatibilidad con GPU: Si está disponible, el procesamiento se realiza en GPU para un mejor rendimiento.

Requisitos

Dependencias

Este proyecto requiere las siguientes bibliotecas:

torch

transformers

pydub

docx

librosa

gc

os

time

Configuración del entorno

GPU opcional: El script detecta automáticamente si hay una GPU disponible y optimiza el procesamiento en consecuencia.

FFmpeg: Es necesario tener FFmpeg instalado en el sistema para la conversión de audio.

Puedes instalar las dependencias de Python utilizando el siguiente comando:

pip install torch transformers pydub python-docx librosa

Para instalar FFmpeg:

En sistemas basados en Debian/Ubuntu:

sudo apt update
sudo apt install ffmpeg

En Windows: Descarga el ejecutable desde FFmpeg.org y agrégalo al PATH.

Uso

Coloca tu archivo MP4 en el mismo directorio que el script.

Asegúrate de que el archivo de entrada tenga el nombre correcto o actualiza la variable mp4_audio_file en el script.

Ejecuta el script con:

python script.py

El script realizará los siguientes pasos:

Convertirá el archivo MP4 a WAV.

Dividirá el audio en fragmentos según los silencios.

Procesará los fragmentos para dividirlos en subfragmentos si son demasiado largos.

Guardará los fragmentos como archivos WAV.

Transcribirá los fragmentos y guardará el texto en un archivo Word (transcripcion_clase.docx).

Al finalizar, encontrarás el archivo Word con la transcripción en el mismo directorio.

Estructura del Código

Configuración inicial

Configura el dispositivo (CPU o GPU) y carga el modelo Whisper de Hugging Face.

Funciones principales

convert_mp4_to_wav

Convierte el archivo MP4 a formato WAV compatible con Whisper.

split_audio_by_silence

Divide el archivo de audio en fragmentos basándose en silencios.

split_long_chunks

Divide fragmentos largos en subfragmentos de duración manejable.

save_audio_chunks

Guarda cada fragmento de audio como un archivo WAV independiente.

save_chunk_to_word

Escribe el texto transcrito de cada fragmento en un documento de Word.

transcribe_audio_to_word

Transcribe los fragmentos de audio utilizando el modelo Whisper y guarda el resultado en Word.

Ejecución principal

El flujo principal realiza los siguientes pasos secuencialmente:

Convierte el archivo MP4 a WAV.

Divide el audio según silencios detectados.

Maneja fragmentos largos dividiéndolos en subfragmentos.

Guarda los fragmentos como archivos WAV.

Transcribe los fragmentos y los guarda en un archivo Word.

Calcula y muestra el tiempo total de procesamiento.

Ejemplo de Salida

Archivo WAV convertido: converted_audio.wav

Fragmentos generados: Guardados en la carpeta audio_chunks.

Archivo de transcripción: transcripcion_clase.docx

Contribución

Siente libre de enviar pull requests o abrir issues para mejorar el script. ¡Cualquier sugerencia o mejora es bienvenida!

Licencia

Este proyecto está licenciado bajo la MIT License.
