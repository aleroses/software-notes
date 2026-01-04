# Mi hardware

## Procesador (CPU)

```bash
❯ lscpu

Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             39 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      12
  On-line CPU(s) list:       0-11
Vendor ID:                   GenuineIntel
  Model name:                Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    CPU family:              6
    Model:                   165
    Thread(s) per core:      2
    Core(s) per socket:      6
    Socket(s):               1
    Stepping:                5
    CPU(s) scaling MHz:      81%
    CPU max MHz:             4300.0000
    CPU min MHz:             800.0000
    BogoMIPS:                5799.77
    Flags:                   fpu vme de pse tsc msr pae mce cx
                             8 apic sep mtrr pge mca cmov pat 
                             pse36 clflush dts acpi mmx fxsr s
                             se sse2 ss ht tm pbe syscall nx p
                             dpe1gb rdtscp lm constant_tsc art
                              arch_perfmon pebs bts rep_good n
                             opl xtopology nonstop_tsc cpuid a
                             perfmperf pni pclmulqdq dtes64 mo
                             nitor ds_cpl est tm2 ssse3 sdbg f
                             ma cx16 xtpr pdcm pcid sse4_1 sse
                             4_2 x2apic movbe popcnt tsc_deadl
                             ine_timer aes xsave avx f16c rdra
                             nd lahf_lm abm 3dnowprefetch cpui
                             d_fault epb ssbd ibrs ibpb stibp 
                             ibrs_enhanced fsgsbase tsc_adjust
                              bmi1 avx2 smep bmi2 erms invpcid
                              mpx rdseed adx smap clflushopt i
                             ntel_pt xsaveopt xsavec xgetbv1 x
                             saves dtherm ida arat pln pts hwp
                              hwp_notify hwp_act_window hwp_ep
                             p pku ospke md_clear flush_l1d ar
                             ch_capabilities
Caches (sum of all):         
  L1d:                       192 KiB (6 instances)
  L1i:                       192 KiB (6 instances)
  L2:                        1.5 MiB (6 instances)
  L3:                        12 MiB (1 instance)
NUMA:                        
  NUMA node(s):              1
  NUMA node0 CPU(s):         0-11
Vulnerabilities:             
  Gather data sampling:      Mitigation; Microcode
  Indirect target selection: Mitigation; Aligned branch/return thunks
  Itlb multihit:             KVM: Mitigation: VMX unsupported
  L1tf:                      Not affected
  Mds:                       Not affected
  Meltdown:                  Not affected
  Mmio stale data:           Mitigation; Clear CPU buffers; SM
                             T vulnerable
  Reg file data sampling:    Not affected
  Retbleed:                  Mitigation; Enhanced IBRS
  Spec rstack overflow:      Not affected
  Spec store bypass:         Mitigation; Speculative Store Byp
                             ass disabled via prctl
  Spectre v1:                Mitigation; usercopy/swapgs barri
                             ers and __user pointer sanitization
  Spectre v2:                Mitigation; Enhanced / Automatic 
                             IBRS; IBPB conditional; PBRSB-eIB
                             RS SW sequence; BHI SW loop, KVM 
                             SW loop
  Srbds:                     Mitigation; Microcode
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Mitigation; IBPB before exit to userspace
```

## Memoria RAM

```bash
❯ free -h

               total        used        free      shared  buff/cache   available
Mem:           7.7Gi       4.8Gi       745Mi       133Mi       2.5Gi       2.8Gi
Swap:          4.0Gi       730Mi       3.3Gi
```

```bash
❯ sudo dmidecode -t memory

[sudo] password for ghost: 
# dmidecode 3.6
Getting SMBIOS data from sysfs.
SMBIOS 3.2.0 present.

Handle 0x003E, DMI type 16, 23 bytes
Physical Memory Array
        Location: System Board Or Motherboard
        Use: System Memory
        Error Correction Type: None
        Maximum Capacity: 64 GB
        Error Information Handle: Not Provided
        Number Of Devices: 4

Handle 0x003F, DMI type 17, 84 bytes
Memory Device
        Array Handle: 0x003E
        Error Information Handle: Not Provided
        Total Width: Unknown
        Data Width: Unknown
        Size: No Module Installed
        Form Factor: Unknown
        Set: None
        Locator: ChannelA-DIMM1
        Bank Locator: BANK 0
        Type: Unknown
        Type Detail: None

Handle 0x0040, DMI type 17, 84 bytes
Memory Device
        Array Handle: 0x003E
        Error Information Handle: Not Provided
        Total Width: 64 bits
        Data Width: 64 bits
        Size: 8 GB
        Form Factor: DIMM
        Set: None
        Locator: ChannelA-DIMM2
        Bank Locator: BANK 1
        Type: DDR4
        Type Detail: Synchronous
        Speed: 2666 MT/s
        Manufacturer: Hewlett-Packard
        Serial Number: 00000000
        Asset Tag: 9876543210
        Part Number: 7EH61AA#            
        Rank: 2
        Configured Memory Speed: 2666 MT/s
        Minimum Voltage: 1.2 V
        Maximum Voltage: 1.2 V
        Configured Voltage: 1.2 V
        Memory Technology: DRAM
        Memory Operating Mode Capability: Volatile memory
        Firmware Version: Not Specified
        Module Manufacturer ID: Bank 1, Hex 0x54
        Module Product ID: Unknown
        Memory Subsystem Controller Manufacturer ID: Unknown
        Memory Subsystem Controller Product ID: Unknown
        Non-Volatile Size: None
        Volatile Size: 8 GB
        Cache Size: None
        Logical Size: None

Handle 0x0041, DMI type 17, 84 bytes
Memory Device
        Array Handle: 0x003E
        Error Information Handle: Not Provided
        Total Width: Unknown
        Data Width: Unknown
        Size: No Module Installed
        Form Factor: Unknown
        Set: None
        Locator: ChannelB-DIMM1
        Bank Locator: BANK 2
        Type: Unknown
        Type Detail: None

Handle 0x0042, DMI type 17, 84 bytes
Memory Device
        Array Handle: 0x003E
        Error Information Handle: Not Provided
        Total Width: Unknown
        Data Width: Unknown
        Size: No Module Installed
        Form Factor: Unknown
        Set: None
        Locator: ChannelB-DIMM2
        Bank Locator: BANK 3
        Type: Unknown
        Type Detail: None
```

## Placa madre (Motherboard)

```bash
❯ sudo dmidecode -t baseboard

# dmidecode 3.6
Getting SMBIOS data from sysfs.
SMBIOS 3.2.0 present.

Handle 0x0002, DMI type 2, 15 bytes
Base Board Information
        Manufacturer: ASUSTeK COMPUTER INC.
        Product Name: PRIME B460M-A
        Version: Rev 1.xx
        Serial Number: 200974465305219
        Asset Tag: Default string
        Features:
                Board is a hosting board
                Board is replaceable
        Location In Chassis: Default string
        Chassis Handle: 0x0003
        Type: Motherboard
        Contained Object Handles: 0

Handle 0x0024, DMI type 10, 6 bytes
On Board Device Information
        Type: Video
        Status: Enabled
        Description:    To Be Filled By O.E.M.

Handle 0x004F, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 1
        Bus Address: 0000:00:00.0

Handle 0x0050, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 2
        Bus Address: 0000:00:14.0

Handle 0x0051, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 3
        Bus Address: 0000:00:16.0

Handle 0x0052, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - SATA
        Type: SATA Controller
        Status: Enabled
        Type Instance: 1
        Bus Address: 0000:00:17.0

Handle 0x0053, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 4
        Bus Address: 0000:00:1f.0

Handle 0x0054, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 5
        Bus Address: 0000:00:1f.2

Handle 0x0055, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Sound
        Type: Sound
        Status: Enabled
        Type Instance: 1
        Bus Address: 0000:00:1f.3

Handle 0x0056, DMI type 41, 11 bytes
Onboard Device
        Reference Designation: Onboard - Other
        Type: Other
        Status: Enabled
        Type Instance: 6
        Bus Address: 0000:00:1f.4
```

## Disco duro / SSD / NVMe

```bash
❯ lsblk -o NAME,MODEL,SIZE,TYPE

NAME   MODEL                   SIZE TYPE
sda    KINGSTON SA400S37960G 894.3G disk
├─sda1                         100M part
├─sda2                          16M part
├─sda3                         180G part
├─sda4                         556M part
├─sda5                       181.6G part
├─sda6                         314M part
├─sda7                       175.1G part
└─sda8                       356.6G part
```

## Tarjeta gráfica

```bash
❯ lspci | grep -i vga

01:00.0 VGA compatible controller: NVIDIA Corporation GF108 [GeForce GT 730] (rev a1)
```

```bash
❯ lspci -nnk | grep -A3 -E "VGA|3D"

01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GF108 [GeForce GT 730] [10de:0f02] (rev a1)
        Subsystem: Micro-Star International Co., Ltd. [MSI] Device [1462:8a9f]
        Kernel driver in use: nouveau
        Kernel modules: nouveau
```

## 

```bash
```


## 

```bash
```

## 

```bash
```

## 

```bash
```