# Instalación de MX Linux XFCE en ASUS K53E

## Descripción

Guía completa para reemplazar Windows 10 por MX Linux XFCE en un portátil ASUS K53E.

## Hardware utilizado

- Modelo: ASUS K53E
- Procesador: Intel Core i5-2450M
- Memoria RAM: 4 GB
- Disco duro: 500 GB
- Sistema anterior: Windows 10
- Sistema instalado: MX Linux XFCE

## Objetivos

- Crear USB booteable con Rufus.
- Instalar MX Linux XFCE.
- Configurar Swap.
- Configurar ZRAM.
- Configurar red.
- Actualizar el sistema.
- Instalar navegadores.
- Documentar incidencias y soluciones.

---

## Proceso realizado

### 1. Descarga de MX Linux

Versión utilizada:

MX Linux XFCE x64

---

### 2. Creación del USB de instalación

Herramienta utilizada:

- Rufus

Configuración:

- Esquema: MBR
- Sistema destino: BIOS o UEFI
- Sistema de archivos: FAT32

---

### 3. Arranque desde USB

Teclas utilizadas:

- ESC → Menú de arranque
- F2 → BIOS

---

### 4. Instalación

Configuración seleccionada:

- Disco completo
- Swap: 4096 MB
- Hibernación: Activada
- ZRAM: Activado
- Samba: Activado

---

### 5. Problemas encontrados

#### Error de actualización

Mensaje:

```text
Sub-process /usr/bin/dpkg returned an error code (1)
```

#### Causa

Intento de actualización desde la sesión Live del USB.

#### Solución

Arrancar desde el disco duro instalado y ejecutar nuevamente:

```bash
sudo apt update
sudo apt full-upgrade
```

---

## Estado actual

✅ MX Linux instalado

✅ Arranque desde disco duro

✅ Usuario creado

✅ Red funcionando

✅ Repositorio GitHub creado

⏳ Configuración completa del idioma español

⏳ Instalación de Microsoft Edge

---

## Autor

Giovanni Ospina Osorio
