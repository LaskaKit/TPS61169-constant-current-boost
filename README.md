# LaskaKit TPS61169 Constant Current Boost LED Driver

A compact DC-DC converter designed for powering [high-power LEDs](https://www.laskakit.cz/vyhledavani/?string=LED) or [LED filaments](https://www.laskakit.cz/vyhledavani/?string=LED%20vl%C3%A1kno) from a low-voltage source. The module uses the **TPS61169** integrated circuit, which boosts the input voltage while **maintaining a constant current through the LED**.  

The load connected to the output must require a **higher voltage than the input voltage** for proper current regulation.

Unlike typical boost converters, this device **regulates current instead of output voltage**. The output voltage automatically increases (above the input voltage) to ensure that the LED draws the set current.

Typical applications:

- powering high-power LEDs  
- LED filaments  
- driving multiple LEDs in series from a Li-ion / 5 V source  
- panel backlighting  

The integrated converter can reach efficiencies of up to **90 %**, depending on input voltage and load.

---

# Key Features

- constant current boost LED driver  
- input voltage **2.7 – 5.5 V**  
- output voltage up to **≈38 V**  
- adjustable LED current up to **≈400 mA** using a **DIP switch**  
- open-LED protection  
- soft-start and thermal protection  
- switching frequency approx. **1.2 MHz**

---

# Electrical Limits (Very Important)

These values represent the limits of the chip. Always keep a safety margin when designing your application.

## Input Voltage

**2.7 V – 5.5 V**

Typical sources:

- Li-ion cell  
- 3×AA batteries  
- (USB) 5 V  

---

## Output Voltage

- automatically regulated, the load must require a higher voltage than the input
- maximum approximately **38 V**

The voltage is not fixed – the converter increases it only as much as needed for the LED current to reach the configured value.

---

## Output Current

Typical range:

**25 – 400 mA**

The LED current is set using a resistor connected to the FB pin.  
For easy current adjustment, this module uses a **DIP switch**.

---

## Maximum Power

The real output power is limited by:

- switch current (~1.2 A)  
- efficiency  
- input voltage  

Typical **approximate** values:

| Vin | ILED | Vout max (approx.) |
|----|----|----|
| 5 V | 100 mA | ~30 V |
| 5 V | 200 mA | ~20 V |
| 5 V | 400 mA | ~10 V |

⚠ **Maximum current and maximum voltage cannot be reached simultaneously.**

---

# Connection

Typical usage:

- Connect an LED filament or a series LED string to the output  
- Set the required current using the DIP switch  
- Connect a suitable power source to the input (3×AA batteries, Li-ion battery, or DC adapter)  
- Adjust the brightness of the LED filament using the DIP switch (current can be changed even while the LED is on)  

If you disconnect the LED filament while the input voltage is present, the **over-voltage protection may activate**. After reconnecting the LED filament, it will likely be necessary to **disconnect and reconnect the input power (restart the driver)**.

---

# Important Notes

## 1. This is NOT a voltage source

This module **is not a standard boost converter**.

Without an LED connected, the output voltage may rise until the **over-voltage protection** is triggered.

Use this driver only with LEDs or other loads designed for **constant current operation**.

---

## 2. Do not exceed the power limits

A common mistake:

400 mA × 30 V = 12 W

This driver **cannot deliver that much power**.

With higher voltage differences, the current must be reduced. See the table of typical values above.

---

## 3. Do not disconnect the output while the input is powered

As mentioned above, disconnecting the load while the input power is present may trigger the chip's **over-voltage protection**. This can shut down the driver.

If you reconnect the LED filament and it does not turn on, the chip must be **restarted** by disconnecting and reconnecting the input power while the load is connected.

---

# Buy the module

https://www.laskakit.cz/laskakit-tps61169-boost-led-driver-s-konstantnim-proudem/
