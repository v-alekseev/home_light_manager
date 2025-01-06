# Light Manager
Прошивка для **ESP32 WROOM DevKit v1** для управления освещением игрушечного домика.

## Сборка
Сборка производится черезn **Ardruino IDE** + драйвера порта Serial https://www.silabs.com/developer-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads

В параметры __ssid__ и __password__ прописать имя и пароль для wifi сети.
```
const char* ssid     = "TP-Link_E92A";
const char* password = "123456";
```

После подключения к сети wifi в Serial порт будет записан IP  адрес по которому можно будет обращаться к плате.
```
- http:/<IP>/on1  - включить освещение. На 16 ножку будет подано напряжение 3,3V
- http:/<IP>/off1  - выключить освещение. На 16 ножке будет убрано напряжение 3,3V
- http:/<IP>/status - узнать включено или нет освещение.  1 - освещение включено. 0 - выклюено.
Функция вернет json

{
    "status": 1
}
```
