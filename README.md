# lanparty
LanParty Infrastructure

This is repository that can be used to spin up infrastructure to host a LAN Party

Citadel Oasis Single Machine Config:

- Hardware:
  - CPU: 2x Intel Xeon E5 2680v2
  - Memory: 128GB
  - Storage:
      - Boot: 256 SATA SSD
      - Webcache:
          - Cache: 2TB NVME
          - Rotational: 2x5TB (Raid 1)
      - UserFiles:
          - 2x 1TB (RAID 1)
- Software:
    - Kubernetes
        - lancachenet/monolithic WebCache/DNS
        - nginx FileUpload FileServer
        - hurlenko/filebrowser FileUpload Interface
        - mthenw/frontail View Cache Logging
        - mbentley/omada-controller Wifi Controller
        - dhcp server w/ UI
    - BareMetal (Ubuntu Server 20.04)
        - Router/Masquerade
        - DHCP forwarder into cluster
    - KVM
        - Security Onion Security Appliance