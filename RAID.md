# Storage Fundamentals
> Author: Ripple Wu 20, Oct, 2016.

# 各種 RAID 的模式
- raid0, raid1, raid5, raid6, raid10,...

# Storage Pool and Volume

## iSCSI
- 把一台 NAS 上面的儲存空間分配給不同的電腦來使用

### Thin Volumn (LUN)

# File System
- 不同的檔案系統：可以存多少檔案？單檔多大？

# Protocol
File Base:
1. Windows: \\10.8.1.2\Public
2. Mac: smb://alice@10.1.1.1/Public
- 適合分享

#Block Base:
1. ip + iSCSI Qualified Name
2. 速度比 file base 還要快。
3. iSCSI 比 samba 還快，又穩定，讓你像是內置的容量一樣。
適合 DataBase, 應用程式 (由 Client 管理檔案系統)

#Web Base:
1. 透過 HTTP 瀏覽器把資料丟進去

#Object Base
1. AWS S3
2. Facebook 或 Spotify
適合靜態資料（不長更改） as Cloud Storage

#Performance
1. Sequential Access
	適合大量 Read (例如 Media Streaming)
2. Random Access
	適合大量 Write(例如 Exchange Server 或 Workstation)
Latency 都不盡相同

#Backup & Protection
1. Recovery Point Objective
2. Recovery Time Objective

#What's new
### Ceph Storage
Key Features:
1. Distributed, Expansible
2. No RAID, OSD: 1 Process to control 1HDD/1 OSD per Core
3. High Availability Monitor/Management System
4. Self Healing. No single point of failure.
5. Open-Source.

### Dedup（除重）
* Reduce data stored in the NAS.
* 600GB > dedup > 100GB
* Use some algorithms to delete the replica data.
* Data recovery is available.

### Predictive Analysis

# Network Knowledge for NAS
驗證網路速度： iPurf
1. Cable type
  * Fiber, RJ-45, SFP+, QSFP+, Thunderbolt 2(Mac), Thunderbolt 3(USB Type-C)
2. Technical Terms
  * IPv4/6, DNS, DDNS, MTU(Jumbo Frame, 內網調大 VPN調小), DHCP server/client, NAT, STP(Spanning Tree), Port Trunking(Link Aggregation/LACP/NIC Teaming/Bonding), VLAN, Virtual Switch
