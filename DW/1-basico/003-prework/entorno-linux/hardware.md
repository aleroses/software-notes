```bash
❯lscpu

Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             39 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      12
  On-line CPU(s) list:       0-11
Vendor ID:                   GenuineIntel
  Model name:                Intel(R) Core(TM) i5-10400F CPU @
                              2.90GHz
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
  Indirect target selection: Mitigation; Aligned branch/return
                              thunks
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
                             ers and __user pointer sanitizati
                             on
  Spectre v2:                Mitigation; Enhanced / Automatic 
                             IBRS; IBPB conditional; PBRSB-eIB
                             RS SW sequence; BHI SW loop, KVM 
                             SW loop
  Srbds:                     Mitigation; Microcode
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Mitigation; IBPB before exit to u
                             serspace
```