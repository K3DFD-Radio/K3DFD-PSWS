## Building an HFRx Personal Space Weather Station  
### Note: This build of the HFRx PSWS does not include the optional TIS-TS1 TimeSync device.

The construction style of an HFRx PSWS is up to the builder. However, the hardware and software must work together to insure that operational performance levels provides quality data to HamSCI.

The RX-888 Mk2 Software Defined Radio is the heart of the HFRx. The BeeLink SER Pro 7i 16-32GB 8-core NUC PC with Linux 24.04.x server with WSPRDaemon installed is the brain. Timing-stabilized by a Leo Bodnar LBE-1420 GPS-disciplined oscillator, the RX888 MkII 16-bit ADC Software-defined Radio provides a full 30Mhz of spectrum coverage - far wider than inexpensive 8-bit RTL-SDR dongles. A Turn Island Systems (Dual) 30Mhz Filter-preamp provide blocking of signals above 30Mhz and a low-noise DX Engineering RSEAV-1 active vertical antenna is used instead of a passive HF antenna.  

The engineering staff at the University of Scranton's HamSCI team has established a construction style where the components are mounted on an 8” x 10” X 1/8” Aluminum sheet with components held in place by 3D printed hold downs. All internal connections consists of high-quality SMA connectors, coax and USB cables. 12VDC is provided to the PSWS components and the active antenna by a Jameco 12V 500mA (or greater) linear power supply. This construction method is highly encouraged but not required.  
## System Block Diagram  
<img width="1153" height="768" alt="Block Diagram" src="https://github.com/user-attachments/assets/197384ec-ade4-4c1e-8027-075bc1146ea6" />  

### Component Connections:  
<img width="1153" height="768" alt="Connection Diagram" src="https://github.com/user-attachments/assets/f65237ec-85c6-49d2-bf90-f165ec6ccf98" />  

### STEP 1: Preparing the Physical System Component Board  
Parts Required -
|  Item  |  Source  |
|------|--------|
| 8" X 10" X 1/8" (3.17mm) Aluminum Sheet | [Source: Amazon](https://a.co/d/0e5haOCW) |
| 8" X 10" X 1/8" (3.17mm) Plexiglas Sheet | [Source: Amazon](https://a.co/d/046o1dCD) |


<img width="1153" height="768" alt="Connection Diagram" src="https://github.com/user-attachments/assets/f65237ec-85c6-49d2-bf90-f165ec6ccf98" />

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

### System Components
|  Item  |  Source  | Information  &  Support |
|------|--------|--------|
| GPS Clock | [Leo Bodner LBE-1420](https://www.leobodnar.com/shop/index.php?main_page=product_info&cPath=107&products_id=393&zenid=0c06e05cfbe1ec87514a52daab4ec452)  | * |
| Filter-Preamp | [Turn Island Systems Low pass filter and preamp](https://turnislandsystems.com/product/filter-preamp-v1/) | [12VDC Linear Power Supply](https://www.jameco.com/z/DDU120100Z7972-Jameco-ReliaPro-AC-to-DC-Wall-Adapter-Transformer-12-Volt-1-Amp-12-Watt_100870.html) |
| Computer | [Beelink](https://www.amazon.com/Beelink-SER5-Computer-Graphics-Support/dp/B0D6G965B)  | [Ubuntu 24.04 Server LTE](https://ubuntu.com/download/server) |
| Integration | [High-quality SMA connection cables](https://www.dxengineering.com/parts/cew-316ds001-2), [hardware](https://www.amazon.com/Saddle-Mounts-Tapping-Organizer-Holders/dp/B09B97326Z) | * |
| RX888 SDR Cooling Fan | [Noctua NF-A4x10 FLX, Premium Quiet Fan](https://www.amazon.com/Noctua-Cooling-Blades-Bearing-NF-A4x10/dp/B009NQLT0M?pd_rd_w=gbwG0&content-id=amzn1.sym.5b28a964-6fd3-4c72-8c58-6450e7d02f5f&pf_rd_p=5b28a964-6fd3-4c72-8c58-6450e7d02f5f&pf_rd_r=0G5C06AR9745D0GVFQWF&pd_rd_wg=Msobs&pd_rd_r=c0dfe18b-ecbe-4a4c-9c6e-7b25a077237f&pd_rd_i=B009NQLT0M&psc=1&ref_=pd_basp_d_rpt_ba_s_1_t) |
| Antenna | [DX Engineering Short Element Active Antenna DXE-RSEAV-1](https://www.dxengineering.com/parts/dxe-rseav-1) | [12VDC Linear Power Supply](https://www.jameco.com/z/DDU120100Z7972-Jameco-ReliaPro-AC-to-DC-Wall-Adapter-Transformer-12-Volt-1-Amp-12-Watt_100870.html)

## Reference and instruction manuals -  
[RX888 MkII SDR Source](https://dc4ku.com/.cm4all/uproc.php/0/SDR%20-%20TEST-BERICHTE/RX888_english.pdf?cdp=a&_=1806ad658e7)  
[TAPR Clock kit and thermal Pad](https://turnislandsystems.com/wp-content/uploads/2024/05/RX888-Kit-2.pdf)    
[Leo Bodnae LBE-1420 GPS Disciplined Oscillator](https://github.com/simontheu/lbe-1420)  
[TIS 30Mhz Filter-preamp](https://turnislandsystems.com/wp-content/uploads/2024/10/Filter-Preamp-v1-rev-6.pdf)  
[DX Engineering DXE-RSEAV1 Active Antenna](https://static.dxengineering.com/global/images/instructions/dxe-rseav-1fvi.pdf?_gl=1*aiifno*_gcl_au*MjY1MDA5NDMzLjE3NzcxMjkxODI.*_ga*ODc1MzkyNjAxLjE3NzcxMjkxODI.*_ga_NZB590FMHY*czE3Nzg1MjAwMzUkbzYkZzEkdDE3Nzg1MjAwNTgkajM3JGwwJGgw)

### Component Layout  
In this instance the system components are mounted on a aluminum plate using thru-hole harware and 3D printed hold-downs. 

### Drill Baseplate Mounting Holes
Use a 4mm drill bit to open holes in the aluminum base plateplate and use M3 screws and nuts to place and affix the 3D hold downs. 
<img width="1143" height="796" alt="image" src="https://github.com/user-attachments/assets/cc9186c5-f339-4bc0-ba5c-c18ac4f96f91" />  

### 3D printed Component Hold Downs
You can use these .stl file to print the component hold down parts that affix the RX888, GPSDO and Filter-Preamp to the aluminum plate. ABS recommended although .20mm layer / 20% infill PLA works well  
[.stl file for RX888 MkII SDR](https://drive.google.com/file/d/11iTI1NAHCLrqhb-Ud5RXdYGEvIffmVQV/view?usp=sharing)  
[.stl file for Leo Bodnar LBE-1420](https://drive.google.com/file/d/18yck0PaMf3_px7qnixWy3uBU1HxInkka/view?usp=sharing)  
[.stl file for Turn Island Systems 30Mhz Filter-Preamp](https://drive.google.com/file/d/1gPSx4msNTrLTgFopmkgazG57UBLr8tAZ/view?usp=sharing)  
<img width="1143" height="767" alt="image" src="https://github.com/user-attachments/assets/6318063e-6c47-48c7-a323-7d009c39c269" />  

## Perform Required RX888 clock-Thermal Kit Installation, DXE-RSEAV1 Antenna Bias-T Disable and LBE-1420 Clock Freq Configuration

### Open up the RX888 MkII SDR and install the TAPR Clock and Thermal Pad kit  

Before connecting the RX888 MkII SDR, some hardware modifications are required. The internal oscillator does not meet the 10 mHz accuracy requirement, so the Leo Bodnar LBE-1420 external clock must be connected and configured for 27MHz. Additionally, a thermal pad should be added to the bottom of the board to address heat dissipation. Refer to the [RX888 Clock Kit - Thermal Pad Manual](https://turnislandsystems.com/wp-content/uploads/2024/05/RX888-Kit-2.pdf) for modification instructions and see below:  

Remove the endplate from the RX888 MkII SDR on the side with the USB socket. As shown below and in the above instructions, install the Clock and Thermal kit to the SDR. Exercise caution when attaching the coax's u.FL connector to the center of the board. Remove the plastic jumper to disable the internal clock and activate the Bodner GPS DO.  

Also, attach the rubber pad to the underside of the SDR's board and the copper tape to the exposed side of the pad. This side will face and press against the body of the SDR to improve heat transfer.   

<img width="1143" height="585" alt="image" src="https://github.com/user-attachments/assets/c923a7ea-6167-4dcb-9652-7dc2c4a7bda2" />

---
## Assemble and Configure the DX Engineering DXE-RSEAV-1 Short Vertical Active Antenna  
1. The first task is to change the internal J2 and J3 jumper settings to disable the Bias-T power source feature. Move both J2 and J3 jumpers from the 1-2 position to the 2-3 position. Then the required 12VDC will be supplied to the type-F connector on the front of the antenna box.  
<img width="1143" height="796" alt="image" src="https://github.com/user-attachments/assets/1a676475-a87c-4fe0-bac0-027ff0272290" />  

2. Modifications to the outside mounting configuration
The antenna's physical design is lacking in sufficient protection from rain, snow or other environmental challenges. I have elected to incorporate the entire unit into a sealed ABS utility box, mounted on a 4X4 pressure-treated post. The ground rod is 1/2" common copper pipe driven into the soil to 4'. Since the Bias-T option is deselected via J2 and J3, 12VDC is provided to the lower F connector via a simple adapter to the DC source. Both the RG6 and the 12ga DC wiring are 50' long and have nominal RF loss or voltage drop.  
<img width="1554" height="738" alt="image" src="https://github.com/user-attachments/assets/2129ecef-f7f8-46fc-a1df-60e4f9b03f78" />

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

This completes the required component modifications  
  
Install Linux Server and WSPRDaemon on the BeeLink SER Pro NUC PC  
<img width="1143" height="796" alt="image" src="https://github.com/user-attachments/assets/2f2aa991-23fe-4a95-b3bd-38fa137843d9" />

## Next Steps -  
### [Follow the HamSCI instructions to configure the Beelink PC with Linux 24.04.n and WSPRDaemon](https://github.com/HamSCI/PSWS_Documentation/wiki/HF-wsprdaemon-Receiver)  
### Then Return Here for: [Operations](https://github.com/K3DFD-Radio/K3DFD-PSWS/blob/main/operation.md)  


