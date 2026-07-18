
<div align="center">

# 👻 KODE420 GHOST

### Privacidad y Debloat Extremo para Windows 10

Elimina el bloatware preinstalado, bloquea la telemetría y endurece la privacidad de tu Windows — en un clic, con punto de restauración automático.

![Platform](https://img.shields.io/badge/platform-Windows%2010-0078D6?style=flat-square&logo=windows)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5391FE?style=flat-square&logo=powershell)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Version](https://img.shields.io/badge/version-1.0-orange?style=flat-square)

[Instalación](#-instalación) · [Cómo usar](#-cómo-usar) · [Personalización](#-personalización) · [FAQ](#-preguntas-frecuentes)

</div>

---

## 📋 Tabla de contenidos

- [Qué es KODE420 GHOST](#-qué-es-kode420-ghost)
- [Características](#-características)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Cómo usar](#-cómo-usar)
- [Qué hace paso a paso](#-qué-hace-paso-a-paso)
- [Personalización](#-personalización)
- [Notas importantes y seguridad](#-notas-importantes-y-seguridad)
- [Detalles técnicos](#-detalles-técnicos)
- [Preguntas frecuentes](#-preguntas-frecuentes)
- [Licencia](#-licencia)

---

## 🎯 Qué es KODE420 GHOST

**KODE420 GHOST** hace que tu Windows 10 deje de espiarte y de venir cargado de apps que nunca pediste. Elimina bloatware preinstalado, apaga la telemetría de Microsoft, bloquea publicidad personalizada y desactiva el rastreo de actividad — todo de forma permanente, con un punto de restauración automático como red de seguridad.

Es el complemento natural de **[KODE420 PURGE](../KODE420-PURGE)**: PURGE libera RAM al momento y se corre a diario, GHOST limpia y protege tu sistema una sola vez.

🎥 Video de presentación: *(link aquí)*

---

## 🚀 Características

| Módulo | Qué hace |
|---|---|
| 🛡️ **Punto de restauración** | Crea un checkpoint de Windows antes de tocar nada |
| 🗑️ **Debloat de apps** | Elimina ~39 apps preinstaladas (Xbox, Bing, Solitaire, Candy Crush, Disney, etc.) |
| 📡 **Bloqueo de telemetría** | Desactiva DiagTrack y 10 tareas programadas de recolección de datos |
| 🎯 **Sin publicidad personalizada** | Apaga ID de publicidad y experiencias "personalizadas" |
| 🕓 **Sin historial de actividad** | Desactiva Timeline y el registro de actividad en la nube |
| 📍 **Sin rastreo de ubicación** | Apaga el servicio de geolocalización de Windows |
| 🔍 **Sin Cortana/Bing en Inicio** | Bloquea la búsqueda web integrada en el menú inicio |
| 📊 **Reporte automático** | Apps eliminadas, tareas bloqueadas y tiempo total, guardado en un log |

---

## 📋 Requisitos

- Windows 10 (build 1809 o superior)
- PowerShell 5.1 o superior (preinstalado en Windows 10)
- Permisos de administrador
- ~15 segundos de tu tiempo

---

## 📥 Instalación

1. Descarga **[GHOST.zip](GHOST.zip)** de este repositorio, o **Code → Download ZIP**
2. Extrae el contenido en cualquier carpeta
3. Listo — no requiere instalación ni dependencias externas

```
KODE420-GHOST/
├── KODE420-GHOST.bat   ← ejecutas este
├── KODE420-GHOST.ps1   ← motor del script, no lo toques directo
├── LICENSE
└── README.md
```

---

## 🎮 Cómo usar

1. Doble clic en **`KODE420-GHOST.bat`**
2. Acepta el permiso de administrador (UAC)
3. El script crea un punto de restauración y corre solo, paso por paso
4. Al final verás cuántas apps se eliminaron y cuántas tareas de telemetría se bloquearon

Se corre **una sola vez**. No hace falta repetirlo cada día como PURGE.

> ⚠️ **Windows SmartScreen** puede marcarlo como "no reconocido" la primera vez — normal en scripts sin firma digital. Click en **Más información → Ejecutar de todas formas**.

---

## 🔍 Qué hace paso a paso

<details>
<summary><b>1️⃣ Punto de restauración de seguridad</b></summary>
<br>

Antes de cambiar nada, crea un punto de restauración de Windows ("KODE420 GHOST - Antes de aplicar cambios"). Si algo no te convence, puedes deshacer todo desde **Panel de Control → Recuperación → Abrir restaurar sistema**.
</details>

<details>
<summary><b>2️⃣ Analiza el estado actual</b></summary>
<br>

Cuenta cuántas apps (sistema + usuario) están instaladas antes de empezar, para poder mostrarte la diferencia real al final.
</details>

<details>
<summary><b>3️⃣ Elimina bloatware preinstalado</b></summary>
<br>

Recorre una lista curada de ~39 apps (Xbox, Bing Weather/News, Solitaire, Skype, 3D Builder, Candy Crush, Disney, Facebook, etc.) y las desinstala con `Remove-AppxPackage`, además de quitar el paquete "aprovisionado" para que no vuelvan a aparecer si creas un usuario nuevo en el equipo.
</details>

<details>
<summary><b>4️⃣ Bloquea la telemetría</b></summary>
<br>

Desactiva el servicio DiagTrack (el que envía datos de diagnóstico a Microsoft) y el servicio de mensajes push WAP, pone el nivel de telemetría del sistema en mínimo, y desactiva 10 tareas programadas específicas que recolectan datos de uso y errores en segundo plano.
</details>

<details>
<summary><b>5️⃣ Endurece la privacidad</b></summary>
<br>

Apaga el ID de publicidad, las "experiencias personalizadas con datos de diagnóstico", el historial de actividad (Timeline), el rastreo de ubicación, la búsqueda de Bing/Cortana en el menú inicio, los anuncios y sugerencias del menú inicio/pantalla de bloqueo, y reduce a cero la frecuencia de las encuestas de feedback de Windows.
</details>

<details>
<summary><b>6️⃣ Reporte final</b></summary>
<br>

Muestra cuántas apps había antes/después, cuántas se eliminaron, cuántas tareas de telemetría se bloquearon y el tiempo total — y guarda todo en un `.txt` con timestamp en la misma carpeta.
</details>

---

## 🔧 Personalización

Todo editable al inicio de `KODE420-GHOST.ps1`:

```powershell
# Agrega o quita apps de la lista de eliminacion
$BloatApps = @(
    'Microsoft.XboxApp', 'Microsoft.SkypeApp', ...
)

# Activa o desactiva el punto de restauracion automatico
$RestorePointEnabled = $true
```

Si usas activamente alguna app de la lista (ej. Skype), simplemente borra o comenta esa línea.

---

## 🔒 Notas importantes y seguridad

- ✅ **Con red de seguridad:** el punto de restauración permite deshacer todo el paquete de cambios desde Windows si algo no te convence
- ❌ **Apps eliminadas:** requieren reinstalarse manualmente desde Microsoft Store si las quieres de vuelta (el punto de restauración también las recupera)
- 🛡️ **Nunca toca** Windows Defender, Firewall, ni ninguna función de seguridad — solo privacidad y apps
- 🧩 Código a la vista en `KODE420-GHOST.ps1`, sin ofuscar — revísalo antes de correrlo si quieres

---

## 🧠 Detalles técnicos

- Escrito 100% en PowerShell, usando únicamente cmdlets nativos de Windows (`Get-AppxPackage`, `Remove-AppxPackage`, `Get-AppxProvisionedPackage`, `Disable-ScheduledTask`, `Checkpoint-Computer`)
- Auto-elevación de permisos incluida
- Manejo de errores en cada paso — si algo falla en un build específico de Windows, avisa y continúa
- Sin dependencias externas, sin telemetría propia, sin conexión a internet

---

## ❓ Preguntas frecuentes

**¿Funciona en Windows 11?**
No está probado ahí. Hecho y probado específicamente para Windows 10.

**¿Por qué se crea un punto de restauración?**
Porque eliminar apps es menos reversible que un simple cambio de registro — es la red de seguridad de un script serio.

**¿Necesito correrlo junto con PURGE?**
No es obligatorio, pero se complementan bien: GHOST limpia y protege una vez, PURGE libera RAM cuando lo necesites.

**¿Recupero espacio en disco?**
Sí, aunque el objetivo principal es privacidad y menos procesos de fondo, no liberar espacio — para eso está PURGE.

---

## 📄 Licencia

MIT — úsalo, modifícalo, compártelo. Ver [LICENSE](LICENSE).

---

<div align="center">

Hecho por **KODE420** 🎬

⭐ Si te sirvió, dale estrella al repo

</div>
