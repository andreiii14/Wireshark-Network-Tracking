# Wireshark Network Tracking

## Overview

This Python script leverages Wireshark for network packet analysis and Google Maps for visualizing the geographical locations of IP addresses within the captured network traffic. The process involves capturing network packets using Wireshark, exporting the relevant packets to a .pcap file, and then running the provided script to generate a KML (.kml) file. This .kml file can be uploaded to Google Maps, providing a visual representation of the network traffic.

## Prerequisites

Before using this script, ensure you have the following prerequisites installed:

- [dpkt](https://github.com/kbandla/dpkt): Python library for decoding packet capture data.
- [pygeoip](https://pypi.org/project/pygeoip/): Python API for MaxMind GeoIP databases.
- GeoIP database file (e.g., GeoLiteCity.dat,)

## Script Explanation

- The script utilizes the `dpkt` library for packet parsing and the `pygeoip` library for IP geolocation.
- The `retKML` function retrieves the longitude and latitude of source and destination IP addresses and formats the data into KML.
- The `plotIPs` function iterates through the packets in the .pcap file, calls `retKML` for each packet, and aggregates the KML data.
- The `main` function reads the .pcap file, generates the KML header and footer, and prints the complete KML document.


## Steps

1. **Capture Packets**: Use Wireshark to capture and export specific network packets to a .pcap file (e.g., `wire.pcap`).
<img width="961" alt="wireshark1" src="https://github.com/andreiii14/Wireshark-Network-Tracking/assets/128039153/1abf171e-6056-452d-a75b-3b6d20a5c1f5">

2. **Run the Script**: Execute the Python script using the command:
    ```bash
    python main.py
    ```
    Watch as the script decodes the packets, revealing their geographical paths.

<img width="953" alt="python" src="https://github.com/andreiii14/Wireshark-Network-Tracking/assets/128039153/957dbab3-bbae-4e59-b244-44450d61ed65">

3. **Save the output, paste it into Notepad++ and save as a .kml file**

<img width="693" alt="notepad" src="https://github.com/andreiii14/Wireshark-Network-Tracking/assets/128039153/bc0cacdb-9cc2-4b68-86c1-0b84f1a7e2f6">


4. **Visualize on Google Maps**: Upload the generated KML file to [Google Maps](https://www.google.com/mymaps") and witness the network tracking mapped out.

<img width="615" alt="maps" src="https://github.com/andreiii14/Wireshark-Network-Tracking/assets/128039153/7003117c-9c11-4d60-a73a-dd2ef2db3ecf">



## Conclusion

In conclusion, the Wireshark Network Tracking project offers a streamlined approach to analyzing and visualizing network traffic using Wireshark and Google Maps. By combining packet analysis with geolocation data, this script enhances the understanding of network communication patterns and allows for a geographical representation of IP addresses involved in the traffic.
