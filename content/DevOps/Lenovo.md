---
title: Lenovo
type: docs
math: false
weight: 5
prev: docs/folder/
---

# Laptop Lenovo

Model: Lenovo ThinkPad E14 Ultra 7-155H/32GB/512/Win11P , E14 Gen 6 (Type 21M3, 21M4) Laptops (ThinkPad) - Type 21M3


## Problemy

### Keyboard speed and delay

Często konfiguracja wbudowanej klawitury się kasuje.
Trzeba wtedy przywrócić ustawiania. Zapis (zmiana) ustawień (c++):

```cpp
#include <windows.h>
#include <iostream>

int main()
{
    // Desired keyboard speed (range 0-31)
    // 0 is the slowest, and 31 is the fastest
    int newKeyboardSpeed = 31; // Example speed value

    // Desired keyboard delay (range 0-3)
    // 0 is the shortest delay, 3 is the longest
    int newKeyboardDelay = 0; // Example delay value (medium-long delay)

    // Change the keyboard speed
    BOOL success = SystemParametersInfo(SPI_SETKEYBOARDSPEED, newKeyboardSpeed, (PVOID)nullptr, SPIF_UPDATEINIFILE | SPIF_SENDCHANGE);
    if (success) {
        std::cout << "Keyboard speed changed successfully!" << std::endl;
    }
    else {
        std::cout << "Failed to change keyboard speed. Error code: " << GetLastError() << std::endl;
    }

    // Change the keyboard delay
    success = SystemParametersInfo(SPI_SETKEYBOARDDELAY, newKeyboardDelay, (PVOID)nullptr, SPIF_UPDATEINIFILE | SPIF_SENDCHANGE);
    if (success) {
        std::cout << "Keyboard delay changed successfully!" << std::endl;
    }
    else {
        std::cout << "Failed to change keyboard delay. Error code: " << GetLastError() << std::endl;
    }

    return 0;
}
```

Odczy ustawień (c#):

```cs
        private void button1_Click(object sender, EventArgs e)
        {
            int key_speed = SystemInformation.KeyboardSpeed;
            int key_delay = SystemInformation.KeyboardDelay;
            label1.Text = key_speed.ToString();
            label1.Text = $"speed={key_speed} (31) delay={key_delay} (0)";
        }
```

### Dźwięk

Po wyłączniu mute, przez krótki czas (100-200ms) dźwię gra z maksymalną głośnością.



