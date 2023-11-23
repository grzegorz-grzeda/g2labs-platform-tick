# g2labs-platform-tick

Platform tick handling library.

This is a [G2EPM](https://github.com/grzegorz-grzeda/g2epm) library.

This library relies on the [g2labs-platform](https://github.com/grzegorz-grzeda/g2labs-platform) library.

## How it works
The `platform_tick_initialize()` takes a pointer to the tick function handler code. The handler is called each `tick`, which lasts 1 ms. The handlers context might be in e.g. an interrupt or another thread, depending on the platform. 

Always use data-barrier guards (like e.g. mutexes) when inside the tick handler!

## Target platforms:
- [x] native (compiled for host)
- [x] ESP32 (S3) (requires the ESP-IDF to be installed and exported)
- [ ] AVR
- [ ] STM32 

## How to compile and link it?

Just include this directory in your CMake project.

Example `CMakeLists.txt` content:
```
...

add_subdirectory(<PATH TO THIS LIBRARY>)
target_link_libraries(${PROJECT_NAME} PRIVATE g2labs-platform-tick)

...
```

# Copyright
This library was written by G2Labs Grzegorz Grzęda, and is distributed under MIT Licence. Check the `LICENSE` file for more details.