# 07 - Git y GitHub

## Objetivo

Aprender a utilizar Git y GitHub para documentar proyectos Linux.

---

## Instalación de Git

```bash
sudo apt install git -y
```

Verificar la instalación:

```bash
git --version
```

---

## Configuración inicial

Configurar usuario:

```bash
git config --global user.name "Giovanni Ospina"
```

Configurar correo:

```bash
git config --global user.email "correo@ejemplo.com"
```

Ver configuración:

```bash
git config --list
```

---

## Clonar repositorio

```bash
git clone URL_DEL_REPOSITORIO
```

Ejemplo:

```bash
git clone https://github.com/giovospo/Instalacion-MX-Linux-ASUS-K53E.git
```

---

## Ver estado

```bash
git status
```

---

## Añadir cambios

```bash
git add .
```

---

## Crear commit

```bash
git commit -m "Descripción de los cambios"
```

---

## Subir cambios

```bash
git push origin main
```

---

## Actualizar repositorio local

```bash
git pull
```

---

## Buenas prácticas

- Documentar cada cambio.
- Crear commits pequeños.
- Mantener README actualizado.
- Utilizar nombres descriptivos.
- Realizar copias de seguridad en GitHub.

---

## Resultado

Repositorio GitHub creado y utilizado para documentar la instalación de MX Linux en ASUS K53E.
