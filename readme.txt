# ESP32 CAN Sniffer

Проект для чтения и отправки CAN-кадров через ESP32. Поддерживает два варианта:
- **MCP2515** — внешний CAN-контроллер + трансивер, работает с **CANHacker** на ПК.
- **SN65HVD230** — трансивер для встроенного CAN (TWAI) ESP32, автономная работа.

## Схемы подключения

### ESP32 + MCP2515

| MCP2515 | ESP32 |
|---------|-------|
| VCC | 5V (VIN) |
| GND | GND |
| CS | GPIO 5 |
| SCK | GPIO 18 |
| SI (MOSI) | GPIO 23 |
| SO (MISO) | GPIO 19 |
| INT | GPIO 21 |

### ESP32 + SN65HVD230

| SN65HVD230 | ESP32 |
|------------|-------|
| VCC | 3V3 |
| GND | GND |
| CTX (D) | GPIO 5 |
| CRX (R) | GPIO 4 |
| CANH | CAN-H |
| CANL | CAN-L |

## Прошивки

- `firmware/canhacker_mcp2515/` — скетч для работы с CANHacker
- `firmware/twai_sn65hvd230_rx/` — только приём через TWAI
- `firmware/twai_sn65hvd230_tx_rx/` — приём и передача через TWAI

## Требования

- ESP32 DevKit V1 (или совместимая)
- Arduino IDE с поддержкой ESP32
- Библиотеки: `autowp-mcp2515`, `CanHacker`

## Лицензия

MIT
