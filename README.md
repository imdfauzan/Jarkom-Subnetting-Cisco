# Tugas Jarkom Subnetting

| Nama | NRP |
| -----|-----|
| Imam Mahmud Dalil Fauzan | 5027241100 |

# Topologi
![topologi](/src/topologi.png)

# Subnetting
**Base IP:** `10.140.0.0`

**Total Host:** 766 host

**IP Prefix:** `10.140.0.0/22`  

| Subnet                             | Kebutuhan Host| Netmask |
|------------------------------------|---------------|---------|
| Bidang Guru & Tendik               | 95 host       | /25     | 
| Bidang Kurikulum                   | 220 host      | /24     |
| Bidang Sarana Prasarana            | 45 host       | /26     | 
| Bidang Pengawas Sekolah (Cabang)   | 18 host       | /27     | 
| Server & Admin                     | 6 host        | /28     | 
| Sekretariat                        | 380 host      | /23     | 
| Tunnel / VPN                       | 2 host        | /30     | 
| **TOTAL**                          | **766 host**  | **/22** | 
![]()

## VLSM
![vlsm](/src/vlsm.png)

| **Jaringan / Ruang**            | Kebutuhan Host | Alokasi Host (2^n - 2) | Prefix (/n) | Network      | Subnet Mask      | Range Host (IP yang bisa dipakai)   | Broadcast      | Gateway (Saran) |
|---------------------------------|-----------------|-------------------------|-------------|--------------|------------------|-------------------------------------|----------------|-----------------|
| **Sekretariat**                 | 380             | 510 (n=9)               | /23         | 10.140.0.0   | 255.255.254.0    | 10.140.0.1 - 10.140.1.254          | 10.140.1.255   | 10.140.0.1      |
| **B. Kurikulum**                | 220             | 254 (n=8)               | /24         | 10.140.2.0   | 255.255.255.0    | 10.140.2.1 - 10.140.2.254          | 10.140.2.255   | 10.140.2.1      |
| **B. Guru & Tendik**            | 95              | 126 (n=7)               | /25         | 10.140.3.0   | 255.255.255.128  | 10.140.3.1 - 10.140.3.126          | 10.140.3.127   | 10.140.3.1      |
| **B. Sarana Prasarana**         | 45              | 62 (n=6)                | /26         | 10.140.3.128 | 255.255.255.192  | 10.140.3.129 - 10.140.3.190        | 10.140.3.191   | 10.140.3.129    |
| **B. Pengawas (Cabang)**        | 18              | 30 (n=5)                | /27         | 10.140.3.192 | 255.255.255.224  | 10.140.3.193 - 10.140.3.222        | 10.140.3.223   | 10.140.3.193    |
| **Server & Admin**              | 6               | 6 (n=3)                 | /29         | 10.140.3.224 | 255.255.255.248  | 10.140.3.225 - 10.140.3.230        | 10.140.3.231   | 10.140.3.225    |
| **Link WAN (Pusat-Cabang)**     | 2               | 2 (n=2)                 | /30         | 10.140.3.232 | 255.255.255.252  | 10.140.3.233 - 10.140.3.234        | 10.140.3.235   | (IP di Router)   |

## CIDR
![cidr](/src/cidr.png)

| Nama Agregasi  | Jaringan (Supernet)    | Prefix          | Netmask    | Range Alamat yang Diringkas        |
|----------------------------------------|----------------|----------------------------------|----------------------|-----|
| **Menuju Pusat**               | 10.140.0.0      | /22          | 255.255.252.0 | 10.140.0.0 - 10.140.0.255      |
