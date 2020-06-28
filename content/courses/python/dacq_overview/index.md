---
title: Data Acquistion General Concepts
linktitle: General Concepts

toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false

menu:
  python:
    parent: python_dacq
    weight: 600

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 600
--- 


## Introduction

The Stage 3 and Stage 4 Advanced Laboratories use Python
for computer control and acquistion of data from a variety of experiments.

This section provides an introduction to the some computer interfacing and
data acquisition in general as well as the specific systems used
in the Advanced Laboratories.

## Analogue and Digital

Computers are digital systems and they must interface with analogue systems
in the real world. This ultimately involves sending a digital number from the
computer to a device which converts it into an analogue signal, or taking an
analogue signal and converting it into a digital signal which is sent
to the computer. Sometimes direct digital signals are sent to control
devices which have on/off states or to provide 'clock' signals for example to
move stepper motors. Thus, the common nomenclature is:

| Term | Acronym | Meaning |
|------|---------|---------|
| Digitial-to-Analogue Converter | DAC | Takes a digital signal (from computer) and convert to an analogue output signal|
| Analogue-Digital Converter | ADC | Converts an analogue signal to digital for recording by the computer  |

<br/>

## Bits and Binary Numbers

Internally computers manipulate bits, which are voltages that represent either a '1' or a '0'. Individual
bits are grouped together to store information (a colection of 8 bits is called a 'byte'). For examples, ADCs
may be 8 bit, 12 bit, 16 bit etc. The bits when combined form a binary number since each location has only
two possible stages.

For example, consider a byte consisting of 8 bits as shown below. Each bit has a weight based on its position; the
lowest weight ("least significant bit") is on the right and the weights double with each place to the left since
each position can have two possibilities (a 1 or 0). The number of possible values is given by $2^8=256$ (0 to 255)

{{< figure src="binary.png" title="Figure: Binary Numbers" lightbox="true" width="500" >}}

## Binary in Python

* entering and printing binary numbers

* bit manipulation

test including python code:

```python
from pydaqmx_helper.adc import ADC

myADC = ADC()
myADC.addChannels([0])
val = myADC.readVoltage()
print(val)
```



## Resolution
Since computers only store digital values digitised values are discrete. The number of bits combined with the range of the ADC or DAC determines the resolution. For example, an 8-bit ADC with a range of 5V has a resolution of ~0.0195V (5V/256) while a 12-bit ADC with a range of 5V has a resolution of 0.0012V (5V/4096).

## Sampling
Nyquist, sample rate, alasing etc + figure/movie




{{< figure src="DigitalDAQv2.png" title="src: Wikipedia" link="https://en.wikipedia.org/wiki/File:DigitalDAQv2.pdf"
lightbox="false">}}





