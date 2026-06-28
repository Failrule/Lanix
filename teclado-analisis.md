# Análisis de Compra — Teclado Split para Lanix Neuron V (Arch Linux)

## Contexto

Equipo: Lanix Neuron V (Clevo 2012), Arch Linux, kernel 7.0.9, Hyprland (Wayland).
Presupuesto: $250–$400 USD. Requisito ergonómico prioritario: **split mecánico**.
Linux compatible (software). Hardware lo resuelve el usuario.

Nota importante para ALGUIEN por ahí. Estoy intentando buscar una opción de teclado dividido porque ALGUIEN no tiene existencias, o por lo menos eso veo en el internet.

---

## Compatibilidad Software en Linux

| Firmware | Linux support | Notas |
|---|---|---|
| **QMK/VIA** | Nativo total | `qmk` en AUR, VIA vía web — sin drivers |
| Bazecor (Dygma) | Bueno | App Linux disponible, código abierto |
| Kinesis SmartSet | Bueno | On-device, sin software. `keyd` para extras. |

---

## Candidatos ($250–$400)

### 🥇 Recomendación — ZSA Moonlander

- **Precio**: ~$365 — zsa.io
- **Tipo**: Mecánico, columnar, split real, hotswap
- **Conexión**: USB-C wired
- **Firmware**: **QMK nativo** — el mejor soporte Linux posible
- **Ergonomía**: columnar stagger + thumb cluster + inclinación ajustable — diseño referente del mercado
- **Linux**: plug & play, VIA/Oryx (configurador web de ZSA) funciona en Linux
- **Contra**: curva de aprendizaje ~2–3 semanas por layout columnar

---

### 🥈 Si quieres layout familiar — Dygma Raise 2

- **Precio**: ~$329 — dygma.com
- **Tipo**: Mecánico, layout estándar staggered + split, hotswap
- **Conexión**: USB-C wired + Bluetooth
- **Firmware**: Bazecor (open source, app Linux nativa)
- **Ergonomía**: split con layout QWERTY convencional — curva de aprendizaje mínima
- **Por qué**: mejor opción si vienes de teclado normal y no quieres reaprender columnar

---

### 🥉 Alternativa económica en rango — Keychron Q11

- **Precio**: ~$190–$210 — amazon.com o keychron.com
- **Tipo**: Mecánico, aluminio CNC, gasket mount, hotswap, TKL staggered
- **Conexión**: USB-C wired
- **Firmware**: **QMK/VIA nativo**
- **Ergonomía**: split real, layout familiar, sin thumb cluster
- **Por qué**: ahorra ~$150 vs Moonlander con QMK igual de bueno; sacrifica ergonomía avanzada

---

### Mención — Kinesis Advantage360 Pro

- **Precio**: ~$349 — amazon.com o kinesis-ergo.com
- **Tipo**: Mecánico, columnar con bowl shape (pocillo), QMK
- **Por qué no es #1**: diseño más nicho, menos comunidad QMK activa que ZSA

---

## Decisión Final Recomendada

```
ZSA Moonlander Mark I
zsa.io — configurador incluido (Oryx)
~$365
```

**Razonamiento**:
1. Referente absoluto del mercado split ergonómico
2. QMK nativo — máximo soporte Linux, sin drivers, programable al detalle
3. Hotswap — cambias switches sin soldar
4. Comunidad enorme en Linux (r/ErgoMechKeyboards, ZSA forums)
5. Si cambias de computador: sigue siendo el mejor teclado disponible
6. Oryx (configurador web) funciona nativo en Linux/Chromium

**Si quieres cero curva de aprendizaje**: Dygma Raise 2 a $329, mismo nivel de calidad con layout familiar.

---

## Setup en Arch Linux post-compra

```bash
# Verificar detección:
lsusb   # debe mostrar ZSA o Dygma como HID

# Moonlander — configurar via Oryx (web, sin instalar):
# → configure.zsa.io

# O via VIA local:
# → usevia.app en Chromium/Firefox

# QMK CLI para firmware custom:
paru -S qmk
qmk setup
```

---

## Verificación

- `lsusb` muestra dispositivo HID
- Ambas mitades responden correctamente
- Oryx/VIA detecta el teclado automáticamente para programar layouts
