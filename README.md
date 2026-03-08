WordPress Authentication Bypass – CVE-2024-10924

Análisis de seguridad y explotación de la vulnerabilidad CVE-2024-10924 que afecta al plugin de WordPress Really Simple Security.

Descripción

Este proyecto documenta el análisis de una vulnerabilidad de tipo Authentication Bypass presente en el plugin Really Simple Security (versiones 9.0.0 – 9.1.1).

La vulnerabilidad permite a un atacante eludir el mecanismo de autenticación de dos factores (2FA) debido a una validación incorrecta dentro del flujo de autenticación.

Entorno de trabajo

Sistema operativo: Kali Linux (VirtualBox)

Servidor web: XAMPP 7.4.33

CMS: WordPress 5.9

Plugin vulnerable: Really Simple Security 9.1.1

Herramientas utilizadas:

Burp Suite

EditThisCookie

Script de explotación en Python

Vulnerabilidad

El problema ocurre porque el método skip_onboarding no valida el resultado devuelto por la función check_login_and_get_user.

Debido a esto, el flujo de ejecución continúa hacia el método authenticate_and_redirect, permitiendo establecer la cookie de autenticación y redirigir al usuario incluso cuando la autenticación no fue correctamente validada.

Esto permite que un atacante eluda el sistema de autenticación de dos factores (2FA) y obtenga acceso no autorizado a la cuenta.

Contenido del proyecto

El proyecto incluye:

Análisis técnico de la vulnerabilidad

Explicación del flujo de explotación

Desarrollo del exploit

Impacto en la seguridad

Propuesta de contramedidas

Aviso

Este proyecto fue desarrollado con fines educativos en un entorno de laboratorio controlado.
No se busca comprometer sistemas reales ni promover el uso malicioso de la vulnerabilidad.
