# AVISO — Verificación de Identidad mediante Biometrica Facial

Sistema de control de acceso que verifica la identidad de una persona comparando, en el momento, una fotografía capturada en vivo (selfie) con una fotografía de referencia registrada previamente. Si ambas imágenes corresponden a la misma persona, se otorga el acceso; en caso contrario, se deniega.

Proyecto desarrollado por **Sylvain Delice** como Proyecto APT (Ingeniería Informática).

## Descripción

El sistema reemplaza los métodos tradicionales de control de acceso (tarjetas, revisión visual de un guardia) por una verificación automática y trazable, mediante reconocimiento facial. Está compuesto por dos partes:

- **Backend**: API REST que gestiona el registro de personas, la verificación de identidad y el historial de eventos de acceso (entrada/salida).
- **Aplicación móvil**: app que permite capturar fotografías desde la cámara del dispositivo y comunicarse con el backend para registrar personas y verificar su identidad.

## Funcionalidades principales

- Registro de personas con foto de referencia.
- Verificación de identidad mediante comparación biométrica facial (selfie vs. foto de referencia).
- Registro automático de eventos de entrada/salida según el resultado de la verificación.
- Historial de eventos por persona.
- Notificaciones automáticas por correo (avisos programados).

## Tecnologías

**Backend**: Python 3.12, FastAPI, SQLAlchemy, APScheduler, face_recognition/dlib (reconocimiento principal), OpenCV (respaldo).

**Aplicación móvil**: Python 3.12, Kivy, KivyMD.

## Estructura del proyecto

\`\`\`
identidad-app/
├── backend/          # API REST (FastAPI)
│   ├── app/
│   ├── requirements.txt
│   └── .env
└── mobile/           # Aplicación móvil (Kivy/KivyMD)
    ├── main.py
    ├── identidad.kv
    └── requirements.txt
\`\`\`

## Instalación y ejecución

### Backend

\`\`\`bash
cd backend
python -m venv venv
venv\Scripts\Activate.ps1   # Windows
pip install -r requirements.txt
uvicorn app.main:app --reload
\`\`\`

La API queda disponible en `http://127.0.0.1:8000` (documentación en `/docs`).

### Aplicación móvil

\`\`\`bash
cd mobile
python -m venv venv
venv\Scripts\Activate.ps1   # Windows
pip install -r requirements.txt
python main.py
\`\`\`

> El backend debe estar corriendo antes de iniciar la aplicación móvil.

## Autor

Sylvain Delice — Ingeniería Informática, Duoc UC (Sede Alameda)
