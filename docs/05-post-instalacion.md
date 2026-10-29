# 05 - Post Instalación

## Verificación del sistema instalado

Comprobar el usuario activo:

```bash
whoami
```

Resultado esperado:

```text
Usuario Linux MX
```

---

## Verificación de conexión a Internet

Comprobar conectividad:

```bash
ping -c 4 8.8.8.8
```

Comprobar resolución DNS:

```bash
ping -c 4 google.com
```

---

## Actualización del sistema

Actualizar la lista de paquetes:

```bash
sudo apt update
```

Actualizar paquetes instalados:

```bash
sudo apt full-upgrade
```

---

## Reparación de paquetes

Comando utilizado:

```bash
sudo dpkg --configure -a
```

Corrección de dependencias:

```bash
sudo apt --fix-broken install
```

---

## Configuración regional

Cambio de idioma:

```bash
sudo dpkg-reconfigure locales
```

Configuración recomendada:

```text
es_ES.UTF-8
```

o

```text
es_CO.UTF-8
```

---

## Instalación de Git

Instalar Git:

```bash
sudo apt install git -y
```

Verificar instalación:

```bash
git --version
```

---

## Creación de repositorio GitHub

Repositorio creado:

```text
Instalacion-MX-Linux-ASUS-K53E
```

Objetivos:

- Documentar la instalación.
- Registrar incidencias y soluciones.
- Practicar administración Linux.
- Aprender Git y GitHub.

---

## Pendientes

- Instalación de Microsoft Edge.
- Configuración completa en español.
- Optimización del sistema.
- Incorporación de capturas de pantalla.
- Uso de Git desde MX Linux.

---

## Estado actual

✅ MX Linux instalado

✅ Arranque desde disco duro

✅ Usuario configurado

✅ Conexión de red operativa

✅ Repositorio GitHub creado

✅ Documentación inicial completada

⏳ Instalación de Microsoft Edge

⏳ Configuración definitiva del idioma
