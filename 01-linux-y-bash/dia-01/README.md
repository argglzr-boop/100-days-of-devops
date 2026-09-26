# Día [01] — [Linux User Setup with Non-Interactive Shell]

**Foco:** Linux
**Fecha:** 2026-08-02

---

## 🎯 Objetivo de la Sesión

> [!TIP]
> **Meta principal:** Crear una cuenta de usuario en Linux asignándole una shell no interactiva (por ejemplo, para usuarios de servicio o cuentas restringidas).

---

## 💻 Práctica y Comandos Principales

```bash
# 1. Crear el usuario de servicio con shell restringida
sudo useradd -s /sbin/nologin devops_user

# 2. Si el usuario ya existía previamente, actualizar su shell predeterminada
sudo usermod -s /sbin/nologin devops_user

# 3. Comprobar la entrada en el archivo de cuentas del sistema
grep "devops_user" /etc/passwd

# 4. Prueba de intento de inicio de sesión (debe rechazar la sesión)
su - devops_user
```

| Comando | ¿Para qué sirve? |
|---|---|
| `useradd` | Crea un nuevo usuario |
| `usermod` | Modifica la configuración de un usuario existente |
| `grep` | Busca patrones en archivos |
| `su` | Cambia de usuario en la sesión actual |

---

## ⚠️ Retos y Solución de Problemas

> [!WARNING]
> **Problema:**
> 

**Causa raíz:**
[Explicación del origen del problema]

**Solución aplicada:**
[Pasos o comando que resolvió el problema]

```bash
# Comando de la solución (si aplica)
```

---

## 📝 Conclusiones y Aprendizaje

- **Principio de menor privilegio (PoLP):** Las cuentas de servicio para bases de datos, agentes CI/CD o daemons web nunca deben tener /bin/bash o /bin/sh como shell predeterminada.

- **Diferencia entre /sbin/nologin y /bin/false:** Mientras que /sbin/nologin notifica educadamente que la cuenta no está disponible, /bin/false simplemente devuelve un estado de salida fallido de inmediato.

- **Validación defensiva:** Siempre verificar el archivo /etc/passwd o usar getent passwd  tras aprovisionar cuentas vía scripts de automatización. 

---

## 🏷️ Tags

`#kodekloud` `#linux` `#sysadmin` `#security` `#100diasdedevops`

---

## 🔗 Recursos y Artefactos

- [Laboratorio de KodeKloud](https://kodekloud.com/)
- [Man page: usermod(8)](https://man7.org/linux/man-pages/man8/usermod.8.html)


<div align="center">

---
[Día anterior](#) · [Índice general](../../README.MD) · [Día siguiente](#)

</div>
