[← Volver al índice](index.md)

# 01, Hardware y pinout

Componentes del microsumo **Centeno** según el esquemático
[`pcb_files/centeno_v1.0_schematic.pdf`](../pcb_files/centeno_v1.0_schematic.pdf).

## Componentes

| Ref. | Componente | Notas |
|---|---|---|
| `ARD1` | **Arduino Mini** (ATmega328P) | Cerebro del robot |
| `U1` | **L293D** | Driver de motores (doble puente H) |
| `D1` | LED rojo | Estado (R1 = 330 Ω) |
| `D2` | LED verde | Estado (R2 = 330 Ω) |
| `D3` | LED amarillo | Estado (R3 = 330 Ω) |
| `D4` | LED azul | Estado (R4 = 330 Ω) |
| `C1`, `C2`, `C3` | 10 µF | Filtrado de alimentación |
| `J1`–`J9` | Conectores de 3 pines | Sensores (VCC / señal / GND) |
| `J10` | Entrada de alimentación | `6VDC` |
| `J11`, `J12` | Conectores de motor | `M1` / `M2` |

## Sensores

Centeno usa **módulos infrarrojos chinos** de reflexión, con **sensibilidad
regulable**. No van soldados: se conectan por los **conectores de 3 pines**
`J1`–`J9`, mapeados a estos pines del Arduino Mini:

| Conector | Pin Arduino |
|---|---|
| `J1` | `D5` |
| `J2` | `D6` |
| `J3` | `D7` |
| `J4` | `D8` |
| `J5` | `D9` |
| `J6` | `A0` |
| `J7` | `A1` |
| `J8` | `A2` |
| `J9` | `A3` |

## Alimentación

- Entrada **`J10` `6VDC`**: alimenta la placa a 6 V.
- La entrada de la placa llega al `RAW` del Arduino Mini y al `VS` del L293D
  (motores).
- `VSS` del L293D y la lógica del Arduino van a 5 V (regulador del propio Mini).

## Motores (`U1` L293D)

| Pin L293D | Función |
|---|---|
| `EN1` (1), `IN1` (2), `IN2` (7) | Motor 1 (`OUT1`=3, `OUT2`=6) → `J11` `M1` |
| `EN2` (9), `IN3` (10), `IN4` (15) | Motor 2 (`OUT3`=11, `OUT4`=14) → `J12` `M2` |
| `VS` (8) | Alimentación de motores |
| `VSS` (16) | Alimentación de lógica (5 V) |
| `GND` (4, 5, 12, 13) | Masa |

## Curiosidad: la firma del autor

En la placa, Esdrufao dejó su nombre **al revés** como guiño:
**"Eirabella Miguel"** (Miguel Eirabella).

---

[Siguiente: 02 - PCB →](02-pcb.md)
