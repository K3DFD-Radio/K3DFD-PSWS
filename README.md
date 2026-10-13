# HamSCi HFRx Personal Space Weather Station  

<img width="1043" height="960" alt="image" src="https://github.com/user-attachments/assets/8c96f2ba-9deb-4760-a0e7-90ccf70e9ea5" />  

### Project Overview  
The goal of the HFRx PSWS project is to create a geographically distributed, multi-instrument network of special receivers (nodes) for ground-based space environment measurements. Data collected from nodes in the PSWS network are aggregated into a central HamSCI database for space science research, specifically for analyzing phenomena like [**Traveling Ionospheric Disturbances (TIDs)**](https://glossary.ametsoc.org/wiki/traveling-ionospheric-disturbances/). Technically, it is a wide-spectrum receiving system that reports WSPR/FST4w and WWV/WWVH time standard signal Doppler-shift in the Digital RF _DRF_ format.  This data is useful for studying the behavior of the ionosphere.  

HamSCI's research & collaboration is coordinated by Dr. Nathaniel Frissell [W2NAF](https://www.qrz.com/db/W2NAF) at the University of Scranton [W3USR](https://www.qrz.com/db/W3USR) and supports a global network of "Citizen Science" monitors. Key partners include: TAPR [Tucson Amateur Packet Radio](https://tapr.org/) - NJIT [Center for Solar-Terrestrial Research](https://research.njit.edu/cstr/) - MIT - [Haystack Observatory](https://www.haystack.mit.edu/) - Case Western Reserve University [Case Western Reserve University](https://case.edu/) et.al.  

The software that processes the Digital RF _DRF_ format information received by the RX888 SDR is [WSPRDeamon](https://wsprdaemon.readthedocs.io/en/master/index.html) by Rob Robinette [AI6VN](https://www.qrz.com/db/AI6VN); which incorporates Phil Karn's [ka9q-radio](https://ka9q-radio.org). It is a Linux-based 'daemon' service designed to operate along with the hardware as a reliable 'appliance' for Amateur Radio operators and researchers. Its primary function is to decode WSPR and FST4W and reliably upload the data to public databases like [wsprnet.org](https://wsprnet.org) and [wspr.rocks](https://wspr.rocks). The project emphasizes high reliability, advanced features, and scientific data collection that goes beyond the capabilities of applications like WSJT-X.  

### HFRx PSWS System Diagram - 
<img width="1126" height="883" alt="image" src="https://github.com/user-attachments/assets/7aa3be83-437b-482b-9f17-ad3fe38da1c9" />  

### The Components of an HFRx PSWS
|  Item     |  Source     | Information  &  Support      |
|---------|-----------|-----------|
| RX888 MkII SDR | [OpenSourceLabs](https://opensourcesdrlab.com/products/rx888-mkii-16bit-sdr-receiver-radio-ltc2208-adc-upgrade-rx888-1) | [Instructions](https://github.com/ik1xpv/ExtIO_sddc) [Linux Drivers](https://github.com/cozycactus/SoapyRX888) |
| GPS Disciplined Oscillator | [Leo Bodner LBE-1420](https://www.leobodnar.com/shop/index.php?main_page=product_info&cPath=107&products_id=393&zenid=0c06e05cfbe1ec87514a52daab4ec452)  | * |
| 30Mhz Filter-Preamp | [Turn Island Systems Low pass filter and preamp](https://turnislandsystems.com/product/filter-preamp-v1/) | [Instructions](https://turnislandsystems.com/wp-content/uploads/2024/10/Filter-Preamp-v1-rev-6.pdf) |
| TS1 Time Sync | [Turn Island Systems Time Sync](https://turnislandsystems.com/product/tis-ts1-timesync/) | [Instructions](https://turnislandsystems.com/wp-content/uploads/2026/03/TimeSync-1.pdf) | 
| GPS Clock+Thermal kit | [TAPR RX-888 Clock kit and thermal pad](https://tapr.org/product/rx888-clock-kit-and-thermal-pad/) | [Instructions](https://tapr.org/product/rx888-clock-kit-and-thermal-pad/) |
| Computer | [Beelink](https://www.amazon.com/Beelink-SER5-Computer-Graphics-Support/dp/B0D6G965B)  | [Ubuntu 24.04 Server LTE](https://ubuntu.com/download/server) |
| Integration | [High-quality SMA connection cables](https://www.dxengineering.com/parts/cew-316ds001-2), [hardware](https://www.amazon.com/Saddle-Mounts-Tapping-Organizer-Holders/dp/B09B97326Z) | * |
| RX888 SDR Cooling Fan | [Noctua NF-A4x10 FLX, Premium Quiet Fan](https://www.amazon.com/Noctua-Cooling-Blades-Bearing-NF-A4x10/dp/B009NQLT0M?pd_rd_w=gbwG0&content-id=amzn1.sym.5b28a964-6fd3-4c72-8c58-6450e7d02f5f&pf_rd_p=5b28a964-6fd3-4c72-8c58-6450e7d02f5f&pf_rd_r=0G5C06AR9745D0GVFQWF&pd_rd_wg=Msobs&pd_rd_r=c0dfe18b-ecbe-4a4c-9c6e-7b25a077237f&pd_rd_i=B009NQLT0M&psc=1&ref_=pd_basp_d_rpt_ba_s_1_t) |
| Antenna | [DX Engineering Short Element Active Antenna DXE-RSEAV-1](https://www.dxengineering.com/parts/dxe-rseav-1) | [Instructions](https://www.dxengineering.com/parts/dxe-rseav-1#documentation) |
| Power Supply | [12VDC Linear Power Supply](https://www.jameco.com/z/DDU120100Z7972-Jameco-ReliaPro-AC-to-DC-Wall-Adapter-Transformer-12-Volt-1-Amp-12-Watt_100870.html) |  

---
## Building your HFRx PSWS consists of three phases: build the device, install and configuration of software and administration of the node as a valuable member of the HamSCI network.
### [STEP 1 Hardware - Build your HRFx PSWS](https://github.com/K3DFD-Radio/K3DFD-PSWS/blob/main/hardware.md)  
### [STEP 2 Software - System Installation & Configuration](https://github.com/HamSCI/PSWS_Documentation/wiki/HF-wsprdaemon-Receiver)  
### [STEP 3 Use and Admin - How to use and maintain your HFRx PSWS](https://github.com/K3DFD-Radio/K3DFD-PSWS/blob/main/operation.md)  
---
## More Information, Sources and Links 
### [Links and Information Sources](https://github.com/K3DFD-Radio/K3DFD-PSWS/blob/main/sources_links.md)    
