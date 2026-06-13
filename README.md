# UAV_Wildlife_Tracking_Integration
Working in conjunction with an EE professor, animal scinece professor, and other EE students at Cal Poly SLO to integrate a UAV mounted system for tracking a VHF beacon emitted from an animal collar using a Raspberry Pi 4, RTL-V4 Software Defined Radio (SDR), and 900 MHz Xbee radios.


## Project Overview
The goal of this project is to integrate a UAV mounted tracking system which can provide distance and heading relative to a VHF beacon emitted from an animal collar. This project builds off a previous team's work who developed the software for reading RSSI using a Raspberry Pi 4 and sending data via XBees but could not fully integrate the overall system. My role on the project was to bring my experience with embedded Linux, Xbee radios, electronics and RF to . I also gave weekly presentations explaining why we made certain design choices and outlining future tasks 

## Hardware
- Raspberry Pi 4: Runs a Python scripts which calculates RSSI from IQ samples provided by an SDR and sends this RSSI values to a GCS. Used a virtual enviorment with libraries such as rtlsdr to interface with the RTL-SDR and pySerial for serial UART communication to XBees.

- 900 MHz Xbee Radios: Configured using Digi XCTU
- RTL-V4 Software Defined Radio
- 
### VHF Transmitter + Tracking System + GCS Block Diagram

<img width="892" height="556" alt="image" src="https://github.com/user-attachments/assets/c3577b0b-bd3e-4095-ab68-a25e59d09b93" />


### First Transmitter Prototype
<img width="872" height="389" alt="image" src="https://github.com/user-attachments/assets/39d78250-2f01-49d3-a6a8-a69582c7da00" />

### Current Transmitter


<img width="491" height="533" alt="image" src="https://github.com/user-attachments/assets/4f1ce704-eeaf-4e55-b41f-e128281ab35a" />

### Current Tracking System

<img width="2880" height="2160" alt="image" src="https://github.com/user-attachments/assets/466d59eb-768f-4b59-8c9a-f447b3aca25f" />

## Software Integration

## Testing

<img width="557" height="344" alt="image" src="https://github.com/user-attachments/assets/e86a66dc-2572-46bf-9fd2-d311444f45cf" />
XCTU console showing RSSI values (dBm) recieved from tracking system

