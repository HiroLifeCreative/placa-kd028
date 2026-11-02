# Placa KD028 v1.0 — Proyecto KiCad (INICIO, no fabricación)

Abrir en KiCad 8: `placa-kd028.kicad_pro` (o abrir `placa-kd028.kicad_pcb` y
`placa-kd028.kicad_sch` desde KiCad).

Contenido:
- Esquemático v1.0: U1 ESP32-S3-WROOM-1-N8R8, U2 buck 5V->3.3V 3A,
  U3 boost LED ~17.5V, J1 FPC 40 pines ST7701S, U5 BH1750, U6 TMP117,
  USB, ESD, BOOT/RESET. Conexiones por etiquetas globales de red.
- PCB: contorno redondo Ø70 mm (Edge.Cuts), 1.2 mm, 4 capas
  (F.Cu, In1.Cu, In2.Cu, B.Cu), huellas colocadas según el layout v1.0,
  pistas iniciales RGB (0.25 mm), alimentación 1.5 mm y LED 1.0 mm,
  3 agujeros M3 Ø3.2 mm a radio 31 mm.

Pasos en KiCad:
1. Schematic Editor: Tools > Electrical Rules Check (ERC) — corregir
   pines sin conectar.
2. PCB Editor: Tools > Design Rules Check (DRC), y comprobar
   ancho de pista de alimentación y separación del boost.
3. Vista 3D (Alt+3) para revisar altura de componentes por detrás.

BLOQUEO ANTES DE FABRICAR (no saltar):
- Confirmar hoja de datos / plano del KD028WXFPD075: pinout exacto
  del FPC de 40 pines y cadena de LEDs. El J1 de este proyecto usa
  el pinout genérico ST7701S de la familia; si el KD028 difiere,
  hay que corregir J1 y el ruteo RGB/SPI antes de generar Gerbers.
- Medir en el coche: distancia entre centros de los 2 agujeros del
  emblema, diámetros y grosor de tapa (para la placa trasera, no
  para esta PCB, que ya es Ø70 mm).
- Solo entonces: File > Fabrication Outputs > Gerbers + Drill,
  y revisión DFM del fabricante.

Nada comprado ni fabricado con este proyecto todavía.
