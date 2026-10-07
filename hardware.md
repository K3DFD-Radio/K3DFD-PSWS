## Building an HFRx Personal Space Weather Station  
### Note: This build of the HFRx PSWS does not include the optional TIS-TS1 TimeSync device.

The construction style of an HFRx PSWS is up to the builder. However, the hardware and software must work together to insure that operational performance levels provides quality data to HamSCI.

The RX-888 Mk2 Software Defined Radio is the heart of the HFRx. The BeeLink SER Pro 7i 16-32GB 8-core NUC PC with Linux 24.04.x server with WSPRDaemon installed is the brain. Timing-stabilized by a Leo Bodnar LBE-1420 GPS-disciplined oscillator, the RX888 MkII 16-bit ADC Software-defined Radio provides a full 30Mhz of spectrum coverage - far wider than inexpensive 8-bit RTL-SDR dongles. A Turn Island Systems (Dual) 30Mhz Filter-preamp provide blocking of signals above 30Mhz and a low-noise DX Engineering RSEAV-1 active vertical antenna is used instead of a passive HF antenna.  

The engineering staff at the University of Scranton's HamSCI team has established a construction style where the components are mounted on an 8” x 10” X 1/8” Aluminum sheet with components held in place by 3D printed hold downs. All internal connections consists of high-quality SMA connectors, coax and USB cables. 12VDC is provided to the PSWS components and the active antenna by a Jameco 12V 500mA (or greater) linear power supply. This construction method is highly encouraged but not required.  

### Component Connections (PC not shown):  
<img width="1153" height="768" alt="Connection Diagram" src="https://github.com/user-attachments/assets/f65237ec-85c6-49d2-bf90-f165ec6ccf98" />  

## System Block Diagram  
<img width="1153" height="768" alt="Block Diagram" src="https://github.com/user-attachments/assets/197384ec-ade4-4c1e-8027-075bc1146ea6" />  

### STEP 1: Preparing the aluminum component board & Plexiglas cover 
Parts Required -
|  Item  |  Source  |
|---------|----------|
| 8" X 10" X 1/8" (3.17mm) Aluminum Sheet | [Amazon](https://a.co/d/0e5haOCW) |
| 8" X 10" X 1/8" (3.17mm) Plexiglas Sheet | [Amazon](https://a.co/d/046o1dCD) |
| *4 5X M4 hex brass spacer 50mm (or 40+10mm) female to female | [Amazon](https://a.co/) |
| 4 QTY Rubber 'feet' | [Amazon](https://a.co/) |  
If sourcing a 50mm hex brass spacer is difficult, use a combination of a 40mm + 10mm hex space to provide the sufficient headroom  
<img width="1153" height="768" alt="PSWS Plexiglass" src="https://github.com/user-attachments/assets/da7244e0-6868-4dbc-8efb-c34c8fd7941f" />
[ ]

### STEP 2 Printing the component mounts and hold-downs  
Parts Required -
|  Item  |  Source  |
|---------|----------|
| 40mm Fan Holder | [GDrive](https://drive.google.com/file/d/1ZR34g1ZgH7q--fjzyhHHjl_GkNwuVO9y/view?usp=sharing) |
| TIS 30Mhz Filter | [GDrive](https://drive.google.com/file/d/1IrFu1ZWpXSL4lWpJRmOSIEOuSLvdFMrz/view?usp=sharing) |
| Leo Bodner LBE-1420 | [GDrive](https://drive.google.com/file/d/1xLlqFm57mBD5PPnAO138lJIPyoZd7v_A/view?usp=sharing) |
| RX-888 Mk II SDR | [GDrive](https://drive.google.com/file/d/1ySCSn3g5AbmjJ8bsmYNKOUIU5xIs7jpk/view?usp=sharing) |  
PLA works fine for these components. While you can use ABS, there are no heavy structural requirements. 15% infill is sufficient.  
<img width="1153" height="768" alt="image" src="https://github.com/user-attachments/assets/78566f5b-1802-4ac2-9dab-d14514dd2a59" />
[ ] Step 1: Download the required .stl files from this repository: [HRFx PSWS .stl files](https://drive.google.com/drive/folders/1YeJeeC-uSJrnpS0maQg5exwwV9ubscKA?usp=sharing)  

### STEP 3: Modifying the RX888 MkII SDR  
Parts Required -
|  Item  |  Source  | Information  &  Support |
|------|--------|--------|
| RX888 MkII SDR | [OpenSourceLabs](https://opensourcesdrlab.com/products/rx888-mkii-16bit-sdr-receiver-radio-ltc2208-adc-upgrade-rx888-1) | [Instructions](https://github.com/ik1xpv/ExtIO_sddc) [Linux Drivers](https://github.com/cozycactus/SoapyRX888) |
| GPS Clock+Thermal kit | [TAPR RX-888 Clock kit and thermal pad](https://tapr.org/product/rx888-clock-kit-and-thermal-pad/) | [Instructions](https://turnislandsystems.com/wp-content/uploads/2024/05/RX888-Kit-2.pdf) |

[ ] Step 1: Open the RX888 MkII and remove the board.    
[ ] Step 2: Remove the two white pads from the non-component side  
<img width="740" height="488" alt="pads" src="https://github.com/user-attachments/assets/031d3a64-56fa-4f1e-a52c-d24328f6e6bd" />  
[ ] Step 3: Place the blue foam cooling pad that came with the GPS Clock+Thermal kit on the non-component side of the SDR board, copper foil side up.   
<img width="740" height="488" alt="Thermal Pad" src="https://github.com/user-attachments/assets/50c9989b-edc1-4cc8-878a-d6f8b7c2d508" />  
[ ] Step 4: Remove or open internal timing clock jumper to disable internal clock. Attach the coax from the TAPR Clock+Thermal kit antenna to the U.FL socket next to the jumper   
<img width="740" height="413" alt="GPS_timing_connect" src="https://github.com/user-attachments/assets/ef435490-7ea6-43c3-960f-3f56e7807f60" />  
[ ] Step 5: Carefully slide the SDR board about 3/4 of the way back into the case. Do not damage the copper foil.  
<img width="488" height="740" alt="Slide TAPR pad into RX888" src="https://github.com/user-attachments/assets/140f98f3-94b2-46de-8986-50746bd41b3e" />  
[ ] Step 6: Place the SMA female TAPR Clock+Thermal kit connector through the provided end plate and tighten with provided nut.   
<img width="940" height="562" alt="TAPR GPS Adapter" src="https://github.com/user-attachments/assets/7a14f2a0-31b8-4d86-9a5c-cf59cf80b3aa" />  
[ ] Step 7: Slide the board completely into the SDR case and affix the new endplate to the SDR  
<img width="410" height="489" alt="TAPR GPS Adapter in-place" src="https://github.com/user-attachments/assets/64c58919-6650-4212-849b-a20278f6dd6d" />  

## Assemble and Configure the DX Engineering DXE-RSEAV-1 Short Vertical Active Antenna  
1. The first task is to change the internal J2 and J3 jumper settings to disable the Bias-T power source feature. Move both J2 and J3 jumpers from the 1-2 position to the 2-3 position. Then the required 12VDC will be supplied to the type-F connector on the front of the antenna box.  
<img width="1153" height="768" alt="image" src="https://github.com/user-attachments/assets/1a676475-a87c-4fe0-bac0-027ff0272290" />  

2. Modifications to the outside mounting configuration
The antenna's physical design is lacking in sufficient protection from rain, snow or other environmental challenges. I have elected to incorporate the entire unit into a sealed ABS utility box, mounted on a 4X4 pressure-treated post. The ground rod is 1/2" common copper pipe driven into the soil to 4'. Since the Bias-T option is deselected via J2 and J3, 12VDC is provided to the lower F connector via a simple adapter to the DC source. Both the RG6 and the 12ga DC wiring are 50' long and have nominal RF loss or voltage drop.  
<img width="1153" height="768" alt="image" src="https://github.com/user-attachments/assets/2129ecef-f7f8-46fc-a1df-60e4f9b03f78" />

### Configure the Leo Bodnard LBE-1420 GPS clock output

1. Visit the [Leo Bodnar website](http://www.leobodnar.com/shop/) and select your GPS Disciplined Oscillator model and download the configuration software for your operating system. Note: Use a different PC  than the PSWS Beelink to run the Bodnar configuration software.  
3. Connect the GPS to your PC — the LED will light up and start the configuration software  

<img width="452" height="582" alt="image" src="https://github.com/user-attachments/assets/2811b0fa-656c-4631-af6c-79cc22c9bde3" />  

4. In the `Hz` box, enter `27000000` and click **Set Frequency** > This sets the output to **27 MHz**, which is the required clock frequency for the RX-888  
5. Disconnect the GPS from your PC  
### Confirm LBE-1420 GPSDO via the `Diagnostics` button

<img width="543" height="445" alt="image" src="https://github.com/user-attachments/assets/9160507b-0668-4c48-b2ff-e8ed64deb28a" />

Connect the LBE-1420 GPS clock's SMA output to the RX-888 TAPR clock-modified GPS-in on the new end board, then connect both the RX888 and the LBE-1420 devices to the PSWS Beelink computer via their USB cables to a USB-3 port (blue tab).

> 📷 **Receiver Setup Schematic:** The Beelink PC, RX-888 Receiver, and GPS Disciplined Oscillator are connected as follows:
> - 🟡 Yellow — GPS Oscillator to RX-888
> - 🔴 Red — GPS Oscillator to PC
> - 🟢 Green — RX-888 to PC

## This completes the hardware building process  


