# DlabOdonto - Sistema Integral de Gestión Odontológica 🦷

![Estado del Proyecto: En Producción](https://img.shields.io/badge/Estado-En%20Producci%C3%B3n-brightgreen)
![Tecnología Principal: Next.js](https://img.shields.io/badge/Frontend-Next.js%2015-blue)
![Base de Datos: Firebase](https://img.shields.io/badge/Backend-Firebase-orange)
![Licencia: Todos los derechos reservados](https://img.shields.io/badge/Licencia-Privada-red)

**DlabOdonto** es una aplicación web moderna, segura y de alto rendimiento diseñada para la administración completa de consultorios odontológicos. Permite gestionar pacientes, citas, consultas, y pagos desde una única plataforma intuitiva.

El sistema está construido con un enfoque en la **seguridad empresarial** y una **experiencia de usuario fluida**, garantizando la integridad de los datos y optimizando el flujo de trabajo diario de la clínica.

---

## 🚀 Demo en Vivo

Puedes probar una demostración en vivo del sistema con las siguientes credenciales de acceso.

**URL:** [www.dlab-odonto.vercel.app/](https://dlab-odonto.vercel.app/)

* **Email:** `demo@demo.com`
* **Contraseña:** `asd123`

*(Nota: La base de datos de la demo puede reiniciarse periódicamente).*

---

## ✨ Características Principales

Este sistema integral cubre todo el ciclo de vida del paciente dentro de la clínica:

### 1. 🔐 Autenticación y Seguridad Avanzada
* **Login Seguro:** Sistema de autenticación robusto.
* **reCAPTCHA Progresivo:** Implementa reCAPTCHA v3 invisible solo después de 2 intentos fallidos para no afectar la UX.
* **Bloqueo por IP:** Límite de 10 intentos y bloqueo automático de 30 minutos para prevenir ataques de fuerza bruta.
* **Reglas de Seguridad en Firebase:** Reglas estrictas que aseguran que cada usuario solo pueda acceder y modificar su propia información.

### 2. 👥 Módulo de Pacientes
* **Gestión Completa (CRUD):** Registro, edición y eliminación de pacientes.
* **Búsqueda Rápida:** Filtros en tiempo real por nombre, email o teléfono.
* **Historial Médico y Dental:** Campos detallados para alergias, medicamentos, y antecedentes.
* **Integridad de Datos:** No se permite eliminar pacientes que tengan citas, consultas o pagos asociados, protegiendo el historial.

### 3. 📅 Módulo de Citas
* **Agenda Inteligente:** Búsqueda obligatoria de pacientes para evitar duplicados.
* **Horarios Personalizables:** Permite definir duración de la cita (en minutos) en lugar de slots fijos.
* **Gestión de Estados:** Flujo completo de estados (`programada`, `confirmada`, `en_progreso`, `completada`, `cancelada`, etc.).
* **Validación:** No permite eliminar citas que ya tengan una consulta registrada.

### 4. 🦷 Módulo de Consultas
* **Registro Clínico:** Diagnóstico, plan de tratamiento, recetas y observaciones.
* **Generación de PDF:** Exporta un resumen profesional de la consulta para el paciente.
* **Vínculo con Pagos:** Muestra el estado de pago de la consulta directamente en los detalles.
* **Integridad:** No permite eliminar consultas que tengan pagos asociados.

### 5. 💰 Módulo de Pagos
* **Pagos Inmutables:** Por seguridad financiera, los registros de pago **no se pueden eliminar**.
* **Múltiples Métodos:** Registra pagos en efectivo, tarjeta, transferencia, Yape, Plin y otros.
* **Integridad Financiera:** Cada pago está estrictamente vinculado a una consulta, garantizando un registro contable claro.

### 6. 📊 Dashboard
* **Métricas en Tiempo Real:** Visualiza de un vistazo el total de pacientes, citas del día, ingresos del mes y consultas totales.
* **Accesos Rápidos:** Enlaces directos a las próximas citas y últimos pacientes registrados para un flujo de trabajo ágil.

---

## 💻 Tecnologías Utilizadas

El proyecto fue construido utilizando un stack moderno enfocado en el rendimiento, la escalabilidad y la mantenibilidad.

| Área | Tecnología | Propósito |
| :--- | :--- | :--- |
| **Framework** | **Next.js 15 (App Router)** | Renderizado del lado del servidor (SSR), rutas y performance. |
| **Lenguaje** | **TypeScript** | Tipado estático para un código robusto y escalable. |
| **Backend & DB** | **Firebase** | Autenticación, Base de Datos (Firestore) y Reglas de Seguridad. |
| **Estilos** | **Tailwind CSS** | Diseño de UI moderno y totalmente responsivo (Mobile-First). |
| **Estado** | **React Hooks & Context** | Manejo de estado global y local de la aplicación. |
| **Seguridad** | **Google reCAPTCHA v3** | Protección anti-bots en el inicio de sesión. |

---

## 🛠️ Decisiones Clave de Arquitectura

El diseño del sistema priorizó tres pilares fundamentales:

1.  **Seguridad Progresiva:** Para no sacrificar la UX, el CAPTCHA **solo** aparece cuando es necesario. La seguridad debe ser inteligente, no un obstáculo.
2.  **Integridad de Datos (Efecto Cascada):** Se implementaron validaciones estrictas (vía Reglas de Firebase y lógica de negocio) que impiden la eliminación de registros padres (Paciente, Cita, Consulta) si tienen hijos (Citas, Consultas, Pagos), asegurando la coherencia del historial.
3.  **Inmutabilidad Financiera:** Los registros de pago nunca se eliminan, **solo** pueden cambiar de estado (ej. `completado` a `reembolsado`), garantizando una auditoría financiera confiable.

---

## 📞 Contacto

Desarrollado y mantenido por **www.dlab.net.pe**.

*Este repositorio es **solo** una vitrina del proyecto. El código fuente es privado y no está disponible públicamente.*
