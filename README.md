# 🔐 API de Autenticación con Django REST

Este proyecto es un backend desarrollado con Django y Django REST Framework que implementa un sistema completo de autenticación de usuarios.

Lo desarrollé como práctica integradora, enfocándome en entender bien cómo funcionan los flujos reales de login, manejo de tokens y recuperación de contraseñas.

---

## 🚀 ¿Qué incluye?

- Registro de usuarios
- Login con JWT
- Refresh token
- Recuperación de contraseña con OTP
- Reset de contraseña
- Manejo de errores y validaciones
- Estructura preparada para escalar

---

## 🧰 Tecnologías usadas

- Python
- Django
- Django REST Framework
- SimpleJWT
- PostgreSQL (o SQLite en desarrollo)

---

## ⚙️ Cómo levantar el proyecto

### 1. Clonar repo
`````````bash
git clone <url-del-repo>
cd practico_login_back
` `` `

### 2. Crear entorno virtual
````````bash
python -m venv .venv
` `` `

### 3. Activar entorno

**Windows:**
```````bash
.\.venv\Scripts\activate
` `` `

**Linux / Mac:**
``````bash
source .venv/bin/activate
` `` `

### 4. Instalar dependencias
`````bash
pip install -r requirements.txt
` `` `

---

## 🗄️ Base de datos
````bash
python manage.py makemigrations
python manage.py migrate
` `` `

---

## ▶️ Ejecutar servidor
```bash
python manage.py runserver
` `` `

Ir a: `http://127.0.0.1:8000/`

---

## 🔐 Endpoints principales

### Registro
```
POST /api/register/
` `` `

### Login
````
POST /api/login/
` `` `

Devuelve:
````json
{
  "access": "token",
  "refresh": "token",
  "user": {
    "id": 1,
    "username": "user"
  }

``` `

### Recuperar contraseña (OTP)
````
POST /api/forgot-password/
` `` `

Body:
````json
{
  "email": "user@example.com"
}
``` `

> 👉 El código OTP se muestra en consola (modo desarrollo)

### Resetear contraseña
````
POST /api/reset-password/
` `` `

Body:
````json
{
  "email": "user@example.com",
  "otp": "123456",
  "new_password": "NuevaClave123"
}
``` `

---

## 🔄 Flujo implementado

1. Usuario se registra o inicia sesión
2. Si olvida contraseña:
   - Solicita OTP
   - Backend genera el código
   - Usuario lo ingresa junto con la nueva contraseña
3. Se actualiza la contraseña correctamente

---

## 🧠 Cosas que aprendí haciendo esto

- Cómo funciona JWT en un sistema real
- Manejo de autenticación en APIs
- Validaciones backend (no confiar en el frontend)
- Flujo completo de recuperación de contraseña
- Manejo de errores HTTP (400, 401, 500)

---

## ⚠️ Notas

- El OTP se imprime en consola (solo desarrollo)
- En un entorno real debería enviarse por email
- Los endpoints de auth usan `AllowAny`

---

## 📌 Autor

Proyecto académico — Tecnicatura en Desarrollo de Software  
Enfocado en backend y desarrollo web
````
