# UAV Wildlife Tracking Integration
Working in conjunction with an EE professor, animal science professor, and other EE students at Cal Poly SLO to integrate a UAV-mounted system for tracking a VHF beacon emitted from an animal collar using a Raspberry Pi 4, RTL-SDR Blog V4 software-defined radio, and 900 MHz XBee radios.


## Project Overview
The goal of this project is to integrate a UAV-mounted tracking system which can provide distance and heading relative to a VHF beacon emitted from an animal collar. The completed prototype of the tracking system consists of a test VHF transmitter, a Raspberry Pi-based tracking system and laptop-based ground control station (GCS). The tracking system works by using a software-defined radio (SDR) to receive a 165 MHz beacon emitted from a VHF transmitter. The SDR sends digital IQ samples to a Raspberry Pi where a Python script computes RSSI from a window of samples. Once RSSI is computed the digital value is transmitted via 900 MHz XBee digital radio to a GCS which will then use the RSSI to compute distance using the Friis transmission equation. Currently, the system only tracks distance between the VHF transmitter and the receiver but future work will involve using a phased antenna array to obtain heading as well. This project builds on a previous team's work who developed the Python script for calculating and transmitting RSSI but could not fully integrate the overall system. 

## Hardware
- Raspberry Pi 4:
  - Runs a Python script that calculates RSSI from IQ samples provided by an SDR and sends these RSSI values to a GCS
  - Used a virtual environment with libraries such as rtlsdr to interface with the RTL-SDR and pySerial for serial UART communication to XBees
  - Runs Tailscale VPN to provide remote SSH access from off-campus locations

- RTL-SDR Blog V4 Software-Defined Radio (SDR)
  - Reciever-only SDR covering 500 kHz to 1.7 GHz
  - Recieves the 165 MHz beacon and streams digital IQ samples to the Raspberry Pi over USB
  
- 900 MHz XBee Radios:
   - Sends RSSI value computed by the Raspberry Pi 4
   - Configured using Digi XCTU

  
### VHF Transmitter + Tracking System + GCS Block Diagram

<img width="892" height="556" alt="image" src="https://github.com/user-attachments/assets/c3577b0b-bd3e-4095-ab68-a25e59d09b93" />


### First Transmitter Prototype
<img width="872" height="389" alt="image" src="https://github.com/user-attachments/assets/39d78250-2f01-49d3-a6a8-a69582c7da00" />

### Current Transmitter

<img width="491" height="533" alt="image" src="https://github.com/user-attachments/assets/4f1ce704-eeaf-4e55-b41f-e128281ab35a" />

### Current Tracking System

<img width="2880" height="2160" alt="image" src="https://github.com/user-attachments/assets/466d59eb-768f-4b59-8c9a-f447b3aca25f" />

## Testing

<img width="557" height="344" alt="image" src="https://github.com/user-attachments/assets/e86a66dc-2572-46bf-9fd2-d311444f45cf" />

XCTU console showing RSSI values (dBm) received from the tracking system via XBee radios

