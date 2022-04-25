# QP/C++ ESP32

Arduino library to use QP/C++ with the ESP32 and the Arduino SDK. 
Arduino library based on the [port](https://github.com/vChavezB/qpcpp/tree/esp32) developed for the ESP32.

## How to test

Open any of the examples and upload to an ESP32. 

### QPSY

[QSPY](https://www.state-machine.com/qtools/qspy.html) can be activated by defining `QS_ON`in `bsp.cpp` of both examples.

```bash
qspy -c YOUR_SERIAL_PORT -b 115200
```

### QView

DPP example can be tested with [QView™](https://www.state-machine.com/qtools/qview.html) example located in `examples/dpp_bsp-esp32/qview`. There are two bat scripts (Windows) which can run the QView scripts.


Note: QSpy must be running before using QView.




