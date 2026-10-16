---
title: Component Selection Example
---

## Examples

### Style 1

> This is the example found in the assignment, uses more html

*Table 1: Example component selection*

**External Clock Module**

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> XC1259TR-ND surface mount crystal<br>$1/each<br>[link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)                 | \* Inexpensive[^1]<br>\* Compatible with PSoC<br>\* Meets surface mount constraint of project                                               | \* Requires external components and support circuitry for interface<br>\* Needs special PCB layout. |
| ![](image3.png)<br>\* Option 2. <br>\* CTX936TR-ND surface mount oscillator <br>\* $1/each <br>\* [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940) | \* Outputs a square wave <br>\* Stable over operating temperature <br> \* Direct interface with PSoC (no external circuitry required) range | * More expensive <br>\* Slow shipping speed                                                         |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.

### Style 2

> Also acceptable, more markdown friendly

**External Clock Module**

1. XC1259TR-ND surface mount crystal

    ![](image1.png)

    * $1/each
    * [link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Compatible with PSoC                      | Needs special PCB layout.                                        |
    | Meets surface mount constraint of project |

1. CTX936TR-ND surface mount oscillator

    ![](image3.png)

    * $1/each
    * [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940)

    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Outputs a square wave                                             | More expensive      |
    | Stable over operating temperature                                 | Slow shipping speed |
    | Direct interface with PSoC (no external circuitry required) range |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.


**Light Sensor**

1. PDV-P8103 surface mount photoresistor

    ![](image1.png)

    * $0.72/each
    * [PDV-P8103](https://www.digikey.com/en/products/detail/advanced-photonix/PDV-P8103/480610?s=N4IgTCBcDaIAoBEBqBaOAOAjABgMwgF0BfIA)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Low unit cost                               | Moderate resistance range may provide less sensitivity in very dim conditions |
    | Documented rise and fall times for ease of calibration                      | Its sensitivity only lists typical, making it hard to estimate variance (min and max)                                        |
    | Resistance range of 16–33 kΩ at 10 lux is suitable for a voltage-divider circuit | Slow response makes it unsuitable for tracking rapid light changes |

1. BPW34S-ND surface mount photodiode

    ![](image1.png)

    * $2.11/each
    * [BPW34S](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/BPW34S/4071244)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Fast response makes it suitable for detecting rapid changes in light                               | Its output is current, requiring a resistor or transimpedance amplifier to produce a useful analog voltage |
    | Wide viewing angle helps capture light from different directions                      | Near-infrared response means its output won't directly give plant-usable data without suitable filtering and calibration                                        |
    | Detects visible light as well as near-infrared radiation, making it versatile for optical sensing | Can be especially sensitive to placement |

1. QSD123 surface mount phototransistor

    ![](image1.png)

    * $2.11/each
    * [QSD123](https://www.digikey.com/en/products/detail/onsemi/QSD123/187443)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Transistor action amplifies the light-generated signal                              | It is optimized for near-infrared light, not the visible spectrum used to assess typical plant lighting |
    | Its typical rise and fall times are around 7 μs, much faster than an LDR                      | Doesn’t require amplifying circuit as per requirements                                        |
    | Its narrow reception angle can help measure light from a specific direction | Its output depends on the infrared spectrum, geometry, and circuit design so must be designed especially carefully |
**Choice:** PDV-P8103 surface mount photoresistor

**Rationale:** The PDV-P8103 is the best choice for our plant monitor because it is inexpensive, has a practical resistance range, and has documented response-time specifications. These characteristics allow us to detect changes in light intensity and compare the readings with thresholds based on the plant’s lighting requirements. Additionally, its variable resistance can be easily converted into an analog voltage using a simple voltage divider, allowing the sensor to interface directly with a microcontroller’s analog input. It is also the simplest to implement while following course guidelines. 