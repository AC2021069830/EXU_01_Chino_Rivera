<img width="1864" height="127" alt="tra1" src="https://github.com/user-attachments/assets/3af5f437-b1ae-4505-8b25-6b0e03bbaeef" />##Informe de Auditoría de Sistemas - Examen de la Unidad I

## Datos del Estudiante
- **Nombres y apellidos:** Angel Alessandro Chino Rivera  
- **Fecha:** 10/09/2025  
- **URL GitHub:** [AC2021069830/EXU_01_Chino_Rivera](https://github.com/AC2021069830/EXU_01_Chino_Rivera.git)  

---

## 1. Proyecto de Auditoría de Riesgos


- **Descripción:**  
Se implementó un inicio de sesión ficticio sin base de datos, en el cual se validan credenciales predefinidas directamente en el código del frontend.  
Para esta evaluación, las credenciales configuradas por defecto son:  
  - **Usuario:** `admin`  
  - **Contraseña:** `123456`  

---

### Motor de Inteligencia Artificial
- **Evidencia:**

<img width="1201" height="454" alt="mejroappy" src="https://github.com/user-attachments/assets/f69ccb1d-b9da-404a-a2ff-3aa730cce57f" />

<img width="1150" height="492" alt="mejora appy2" src="https://github.com/user-attachments/assets/7eba0c5d-306e-47b5-9b86-e31dc642f542" />

- **Descripción:**  

Se mejoró el sistema agregando un motor IA basado en modelos locales a través de la librería openai conectada a Ollama (http://localhost:11434/v1).
La función obtener_riesgos identifica 5 riesgos e impactos posibles para un activo de información ingresado.
La función obtener_tratamiento sugiere un tratamiento correctivo o preventivo alineado a ISO 27000.
Se usan ejemplos iniciales en los mensajes (few-shot prompting) para guiar la respuesta y expresiones regulares para separar riesgos e impactos.
Esta mejora permite la generación automática de perfiles de riesgo, impactos y sugerencias, cumpliendo con los requisitos de la práctica.
---

## 2. Hallazgos


## Activo 1: Servidor de Base de Datos (Base de Datos)  
- **Evidencia:**
<img width="1864" height="127" alt="tra1" src="https://github.com/user-attachments/assets/45950fdf-0c7b-47a6-83e5-7a8695d6cb94" />

- **Condición:** Sin cifrado en reposo ni en tránsito; sin backups automáticos.  
- **Recomendación:** Habilitar cifrado (AES-256, TLS), configurar respaldos automáticos.  
- **Riesgo:** 🔴 Alta  

---

## Activo 2: API de Transacciones (Servicio Web)  
- **Evidencia:**
<img width="1842" height="61" alt="tra2" src="https://github.com/user-attachments/assets/5032381b-106b-4522-9884-82ed294b7fbc" />
  
- **Condición:** Sin protección contra inyecciones; tokens inseguros.  
- **Recomendación:** Validación estricta, WAF, autenticación JWT/OAuth2.  
- **Riesgo:** 🔴 Alta  

---

## Activo 3: Aplicación Web de Banca (Aplicación)  
- **Evidencia:**
<img width="1849" height="68" alt="tra3" src="https://github.com/user-attachments/assets/5d7377c7-6891-4f82-8999-69be968abacd" />

- **Condición:** Sesiones indefinidas, sin MFA.  
- **Recomendación:** Expiración de sesión (15 min), regeneración de sesión, MFA.  
- **Riesgo:** 🟠 Media  

---

## Activo 4: Servidor de Correo (Infraestructura)  
- **Evidencia:**
<img width="1847" height="69" alt="tra4" src="https://github.com/user-attachments/assets/ea0d1d79-0840-4ecc-9565-2b91181b13db" />

- **Condición:** Permite correos sin TLS; sin SPF/DKIM/DMARC.  
- **Recomendación:** TLS obligatorio (587), habilitar SPF, DKIM y DMARC.  
- **Riesgo:** 🟠 Media  

---

## Activo 5: Firewall Perimetral (Seguridad)  
- **Evidencia:**
<img width="1844" height="98" alt="tra5" src="https://github.com/user-attachments/assets/2a7d1ec0-75d8-4243-9946-3a20bac800c2" />

- **Condición:** Reglas permisivas sin justificación.  
- **Recomendación:** Hardening de configuración, cierre de puertos, monitoreo con alertas.  
- **Riesgo:** 🔴 Alta  
---

