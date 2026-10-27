# 04 - Problemas y Soluciones

## Problema 1: Error de resolución DNS

### Mensaje observado

```text
Temporary failure resolving 'security.debian.org'
Temporary failure resolving 'mxrepo.com'
```

### Causa

El sistema no podía resolver nombres DNS correctamente.

### Diagnóstico

Comprobación de conectividad mediante:

```bash
ping -c 4 8.8.8.8
```

y

```bash
ping -c 4 google.com
```

### Solución

Verificar la conexión de red y volver a ejecutar:

```bash
sudo apt update
```

---

## Problema 2: Error durante la actualización

### Mensaje observado

```text
Sub-process /usr/bin/dpkg returned an error code (1)
```

### Causa

La actualización se ejecutó inicialmente desde la sesión Live de MX Linux.

### Diagnóstico

El usuario activo era:

```bash
demo
```

lo que indicaba que el sistema estaba funcionando desde el USB.

### Solución

Reiniciar el equipo.

Retirar el USB de instalación.

Arrancar desde el disco duro.

Verificar el usuario mediante:

```bash
whoami
```

Resultado:

```text
giovospo
```

---

## Problema 3: Espacio insuficiente durante la actualización

### Mensaje observado

```text
No space left on device
```

### Causa

La actualización estaba utilizando el entorno Live del USB.

### Solución

Arrancar desde la instalación definitiva del disco duro.

---

## Problema 4: Acceso a Copilot desde navegador

### Síntoma

Al acceder a Copilot aparecía un mensaje:

```text
Se requiere autorización
```

y la página se recargaba continuamente.

### Acciones realizadas

- Verificación de la cuenta Microsoft.
- Evaluación de instalación de Microsoft Edge.
- Inicio del proceso de documentación del sistema en GitHub.

---

## Lecciones aprendidas

- Verificar siempre si se está usando la sesión Live o el sistema instalado.
- Comprobar la conectividad de red antes de actualizar.
- Ejecutar las actualizaciones únicamente desde el sistema instalado.
- Documentar los problemas y sus soluciones facilita futuras instalaciones.
