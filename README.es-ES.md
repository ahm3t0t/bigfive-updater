

# BigFive Updater

**Un solo comando. Todas las distros. Cero complicaciones.**

[![CI](https://github.com/CalmKernelTR/bigfive-updater/actions/workflows/ci.yml/badge.svg)](https://github.com/CalmKernelTR/bigfive-updater/actions/workflows/ci.yml)
[![Version](https://img.shields.io/github/v/release/CalmKernelTR/bigfive-updater?sort=semver&label=Version)](https://github.com/CalmKernelTR/bigfive-updater/releases)
[![License: MIT](https://img.shields.io/github/license/CalmKernelTR/bigfive-updater)](LICENSE)

---

Ejecutas Fedora en tu escritorio, Ubuntu en tu servidor, Arch en un proyecto secundario y Alpine en tus contenedores. Actualizarlos implica recordar `dnf`, `apt`, `pacman`, `zypper`, `apk`… y sus banderas, particularidades y trampas.

**BigFive Updater** te ofrece un único comando que funciona en todas partes: `guncel`.

Detecta tu distribución, selecciona el gestor de paquetes correcto, ejecuta la actualización con valores predeterminados sensatos, registra todo y se mantiene en segundo plano. Bash puro. Sin dependencias. Sin magia.

---

## Distribuciones Soportadas

| | Familia de Distro | Gestor de Paquetes |
|---|---|---|
| 🎩 | Fedora, RHEL, CentOS, Rocky, Alma | `dnf` / `yum` |
| 🐧 | Ubuntu, Debian, Linux Mint, Pop!_OS, Zorin | `apt` |
| 🏗️ | Arch, Manjaro, EndeavourOS, CachyOS | `pacman` |
| 🦎 | openSUSE Leap, Tumbleweed, GeckoLinux | `zypper` |
| 🏔️ | Alpine Linux | `apk` |

---

## Instalación

```bash
# Universal (todas las distros)
curl -fsSL https://github.com/CalmKernelTR/bigfive-updater/releases/latest/download/install.sh | sudo bash

# Arch Linux (AUR)
yay -S bigfive-updater

# Alpine Linux — consulte la documentación completa para la configuración del repositorio
apk add bigfive-updater
```

## Uso

```bash
guncel                # Actualización interactiva: solo ejecútalo
guncel --auto         # No interactiva, ideal para cron
guncel --dry-run      # Previsualiza los cambios sin aplicar nada
guncel --doctor       # Verificación de estado del sistema
guncel --history      # Revisa actualizaciones anteriores
guncel --verbose      # Muestra cada detalle
guncel --quiet        # Salida mínima
guncel --lang en      # Salida en inglés (predeterminado: turco)
guncel --version      # Muestra la versión
guncel --help         # Muestra todas las opciones
```

Tres alias, misma herramienta: `guncel`, `updater`, `bigfive`.

### Ejemplo de Salida

```
$ sudo guncel --auto

>>> BigFive Updater v6.5.1 (Fluent Edition - India)
--------------------------------------------------

>>> APT: Iniciando actualización
--------------------------------------------------
  [✓] Lista de paquetes actualizada.

>>> APT: Actualización de distribución
--------------------------------------------------
  [✓] 12 paquetes actualizados.

>>> APT: Limpieza
--------------------------------------------------
  [✓] Limpieza completada.

>>> Flatpak: Actualización
--------------------------------------------------
  [✓] 3 aplicaciones actualizadas.

========================================
  [+] ACTUALIZACIÓN COMPLETADA
----------------------------------------
  APT: 12 paquetes actualizados
  Flatpak: 3 aplicaciones actualizadas
  Snap: Actualizado
  Firmware: Actualizado
----------------------------------------
  Snapshot: No creado
  Reinicio: No necesario
  Log: /var/log/bigfive-updater/update_20260224_030000.log
========================================
```

---

## ¿Por qué no simplemente `apt upgrade`?

Ya conoces tu gestor de paquetes. BigFive no lo reemplaza, lo envuelve con funcionalidades que tú mismo crearías si tuvieras el tiempo:

- **Detección de distribución** — un solo comando en todas tus máquinas, sin cambiar de herramienta por memoria muscular
- **Registro (logging)** — cada actualización registrada con marcas de tiempo, consultable con `--history`
- **Verificaciones de estado** — `--doctor` detecta problemas comunes antes de que causen daños (repositorios desactualizados, dependencias rotas, espacio en disco)
- **Ejecución en seco** — previsualiza los cambios antes de aplicarlos, especialmente en producción
- **i18n** — turco e inglés, intercambiables en tiempo de ejecución
- **Compatible con cron** — `--auto --quiet` para servidores sin supervisión, con logrotate incluido
- **Completado de shell** — Bash, Zsh, Fish

Si solo ejecutas una distribución en una máquina, tu gestor de paquetes nativo es suficiente. BigFive brilla cuando gestionas varias distribuciones o deseas salvaguardas en tus actualizaciones.

---

## Documentación

| | Idioma | README | Hoja de Ruta | Registro de Cambios |
|---|---|---|---|---|
| 🇹🇷 | Türkçe | [README.tr.md](README.tr.md) | [ROADMAP.tr.md](ROADMAP.tr.md) | [CHANGELOG.tr.md](CHANGELOG.tr.md) |
| 🇬🇧 | English | [README.en.md](README.en.md) | [ROADMAP.en.md](ROADMAP.en.md) | [CHANGELOG.en.md](CHANGELOG.en.md) |

---

## Contribución

Vea [CONTRIBUTING.md](CONTRIBUTING.md) · [Código de Conducta](CODE_OF_CONDUCT.md) · [Política de Seguridad](SECURITY.md)

---

## Licencia

MIT — úsalo, bifúrcalo, mejóralo.

---

<p align="center">
  <i>Construido por <a href="https://calmkernel.tr">CalmKernel</a> — el mejor amigo del administrador perezoso pero obsesivo.</i>
</p>
