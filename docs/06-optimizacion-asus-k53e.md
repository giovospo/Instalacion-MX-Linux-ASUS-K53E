# 06 - Optimización del ASUS K53E

## Hardware

| Componente | Especificación |
|------------|---------------|
| Modelo | ASUS K53E |
| CPU | Intel Core i5-2450M |
| RAM | 4 GB |
| Disco | 500 GB |
| Gráficos | Intel HD Graphics 3000 |
| Sistema Operativo | MX Linux XFCE |

---

## Objetivos de optimización

- Reducir consumo de memoria RAM.
- Mejorar velocidad de arranque.
- Optimizar rendimiento general.
- Prolongar la vida útil del equipo.
- Mejorar la experiencia de navegación web.

---

## Configuración recomendada

### Swap

Configuración utilizada:

```text
4096 MB
```

### ZRAM

Activado.

Beneficios:

- Menor uso de disco.
- Mejor aprovechamiento de la RAM.
- Mayor fluidez al abrir varias aplicaciones.

---

## Servicios recomendados

Verificar servicios activos:

```bash
systemctl list-unit-files --state=enabled
```

Desactivar servicios innecesarios cuando proceda.

---

## Limpieza del sistema

Eliminar paquetes innecesarios:

```bash
sudo apt autoremove
```

Limpiar caché:

```bash
sudo apt clean
```

---

## Monitoreo de recursos

Instalar utilidades:

```bash
sudo apt install htop neofetch -y
```

### Ver uso de CPU y memoria

```bash
htop
```

### Ver información general del sistema

```bash
neofetch
```

---

## Navegadores recomendados

### Firefox

Ventajas:

- Incluido por defecto.
- Buen equilibrio entre consumo y rendimiento.

### Brave

Ventajas:

- Bloqueo de anuncios integrado.
- Menor consumo de recursos en algunos escenarios.

### Microsoft Edge

Ventajas:

- Compatibilidad completa con servicios Microsoft.
- Acceso a Copilot.
- Sincronización de cuenta Microsoft.

---

## Recomendaciones de hardware futuras

### Prioridad 1

Instalar SSD SATA.

Beneficios:

- Arranque más rápido.
- Apertura inmediata de aplicaciones.
- Mayor fluidez general.

### Prioridad 2

Ampliar memoria RAM a 8 GB.

Beneficios:

- Mejor multitarea.
- Más pestañas de navegador abiertas.
- Mejor experiencia con aplicaciones modernas.

---

## Comandos útiles

Actualizar sistema:

```bash
sudo apt update && sudo apt full-upgrade
```

Ver espacio libre:

```bash
df -h
```

Ver memoria disponible:

```bash
free -h
```

Ver temperatura:

```bash
sensors
```

---

## Estado actual del equipo

✅ MX Linux XFCE instalado

✅ Usuario configurado

✅ Red operativa

✅ Swap configurada

✅ ZRAM configurado

✅ Repositorio GitHub creado

⏳ Configuración completa del idioma español

⏳ Instalación definitiva de Microsoft Edge

⏳ Incorporación de capturas al repositorio
