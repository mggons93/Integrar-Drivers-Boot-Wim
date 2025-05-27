# Integrar Drivers en boot.wim (GUI PowerShell)

Este script en PowerShell proporciona una **interfaz gráfica (GUI)** para integrar drivers en un archivo `boot.wim`, permitiendo elegir entre drivers locales o descargarlos automáticamente desde un servidor remoto.

## Características

- Interfaz gráfica amigable (WPF)
- Soporta dos modos de drivers:
  - **Local**: selecciona una carpeta con drivers.
  - **Descargar**: obtiene un paquete ZIP de drivers desde un servidor.
- Detecta automáticamente los índices en el `boot.wim`.
- Integra drivers usando `DISM`.
- Muestra progreso visual y registro detallado en tiempo real.
- Compatible con versiones de Windows que soportan PowerShell 5.1+ y `DISM`.

## Requisitos

- Windows 10/11 (x64)
- PowerShell 5.1 o superior
- Privilegios de administrador
- Acceso a Internet (solo en modo "Descargar")

## Uso

1. Ejecuta el script **como administrador**.
2. Selecciona el **modo de drivers** (Local o Descargar).
3. En modo "Local", elige la carpeta de drivers.
4. Selecciona el archivo `boot.wim` (ubicado en tu ISO de Windows o entorno WinPE).
5. Haz clic en **"Instalar Drivers"** y espera a que el proceso termine.

## Detalles técnicos

- Los drivers se integran usando:
  ```powershell
  dism /Add-Driver /Driver:<ruta> /Recurse /ForceUnsigned
