---
layout: post
title: Concept of Disk RADI
description: "Understanding about Disk RAID"
modified: 2022-01-03
tags: [System Design]
categories: [System Design]
---


### Disk RAID
> RAID : Redundant Array of Independent Disks


- RAID
    - Multiple disks are used as one disk
    - Cost reduction + reliability improvement + performance improvement

- Hardware RAID
    - Hardware manufacturer makes equipment with several hard disks and supplies itself
    - A bit more stable but expensive

- **Software RAID**
    - Alternative to expensive hardware RAID
    - The method supported by the operating system
    - More secure data storage at low cost


### RAID type
> RAID type


- **Add hdd** : Add simple volume, 1 hdd
- **Linear raid**: At least 2 HDDs, 2 HDDs attached to use as 1, sequential data storage, 100% space utilization
- **raid 0**: at least 2, simultaneous storage on all disks, 100% space utilization
    - RAID 0: A minimum of two hard disks are required, and all disks are simultaneously saved. It has 100% space efficiency and has fast performance. However, if one disk fails, all information becomes unavailable, so reliability is low.

- **raid 1** : mirroring - 1/2 space, low space efficiency, important data storage, high reliability.
    - RAID 1 : Also called mirroring method, the same data is stored equally on two or more hard disks. That is, the space efficiency is reduced by 1/2. Instead of reducing space efficiency, the same data is stored on other hard disks, so even if one device has a defect, it can be used without any problem. There is no difference in storage speed because the same information is input to different disks.


- **raid 5** : 3 or more hdd, 2 HDDs for data, 1 for storing parity values, good data stability, good space efficiency
    - RAID 5: By using a combination of the space efficiency of RAID 0 (100%) and the data stability of RAID 1, you can use Parity to recover defective data. However, if two or more disks fail, recovery is impossible even with parity.
    - Using the parity bit means that, for example, when there are disk 1, disk2, and disk3, if disk1 data is ‘0’ and disk2 data is ‘1’, disk3 has a parity bit by XORing 0 and 1 and returns a value of ‘1’. save
        - For reference, the XOR operation is (0 if equal, 1 if different)

- **raid 6** : improvement of raid5, 4 or more hdd, 2 parity, use of redundant parity information
    - RAID 6 : This is a further improvement of the RAID 5 method, and although the space efficiency is lower than that of RAID 5, the data is not damaged even if two disks fail at the same time.
