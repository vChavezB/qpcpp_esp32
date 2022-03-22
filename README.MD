# QP/C++ ESP32

Arduino library to use QP/C++ with the ESP32 and the Arduino SDK. Based on the [port ](https://github.com/QuantumLeaps/qpc/tree/master/ports/esp-idf) from QP/C, I have ported the version to its C++ counterpart.

## Changes from ESP-IDF port for QP/C

 - Refactored macros and functions to C++
 - Task creation uses `xTaskCreatePinnedToCore` instead of `xTaskCreateStaticPinnedToCore`. 
     I made this change since I  am working with the Arduino SDK. The Arduino SDK uses a precompiled version of the ESP32 FreeRTOS, which does not include  `xTaskCreateStaticPinnedToCore` . I am not sure what is the downside of not using a preallocated region for stack in terms of the QP framework, but so far the port works fine.
- m_thread is of type `void *`, so this means that its usage in `qf_port.cpp` was lightly changed. 