# SpareAlim #
## An hybrid power supply, Arduino compatible, using spare parts left available during this shelter in place time. ##
Coronalim is a poject to build the best lab power supply possible using the spare parts while being “sheltered in place”, thanks to her majesty Coronavirus.

## "Base brick" ##
I stored for quite a long time a nice LF ferrite transformer. It has these outputs

![Alt Text](https://github.com/mrguen/SpareAlim/blob/master/images/Transformer.jpg)

* power 13,5V – 0 - 13,5V
* power 10V – 0 – 10V
* aux 0 - 8,5V
* aux 14V – 0 – 14V


I don't remember the power rating. Given the size of the transformer it must be around 150W.

Given this I would like to provide has high voltage as I can, symmetrical power or single line with the less noise as possible  and the best efficiency as possible

## Possible specifications ##
 
Now all this sounds incoherent. I would like low noise for sensitive applications like audio amplifiers but I don't want to waste 100W in heatsinks etc... it since I have many outputs, I think I will make an hybrid power supply, that is

* One symmetrical output. Using the 13,5v – 0 – 13,5V It could produce a variable dual rail using LDO (low noise) regulators up to +/- 12V. Since this power will be low noise I would also like to use it as single supply when needed.
* One single output. Using the 10V – 0 – 10V. But I think I might need more than 20V. So for this one I consider using a sepic circuit to produce any voltages between 0 and let say 48V. This one will be quite noisy but will probably be usefull in many situations.
* One fixed 5V low power using a small SMPS chip
* One fixed 3,3V low power  using a small SMPS chip

I will need to add some current limit circuit, over current protection, over temperature protection etc. 

Regarding the control and monitoring circuits, I have been using INA226 chips on former projects to measure voltage and current and think it will be nice associated with an STM32 (bluepill board) or an Atmega644 MCU.

The human interface will feature a color TFT a couple of buttons ad a selector.

## Some of the parts I have ##
* bridges, diodes, inductors, low ESR caps 
* small transformers
* a couple of DC/DC chips: CS5173 that can do SEPIC but up to 1,5A “only”, buck chips AP3502 and AOZ1280 and others but not for SEPIC and or not powerful enough. Or we could use the STM32F103 PWM or another oscillator circuit.
* INA226/INA233 current measurement chips, 
* standard linear regulators (I consider using LD1117 types), standard op amps MOSFET (N, P), triacs
* TFT screens, one selector, STM32F103 chips (a bluepill board), or Atmega328/644/1284 (Nano, Narrow) etc.


## Some basic circuits ##

For the symmetrical low noise circuit :
https://www.hackster.io/Joao_Claro/symmetric-power-supply-controlled-by-arduino-pwm-aa2422 

Another source of inspiration
https://github.com/eez-open/psu-hw

## Call for collaboration ##

Since I think this project will be interesting to many, for once I will propose to the electronic hobbyist community and particularly to the Arduino user's to work together on this.

So let me know your views on this and work together!