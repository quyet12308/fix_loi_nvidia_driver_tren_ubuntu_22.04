# fix_nvidia_driver_on_ubuntu_server_22.04

## Hello everyone.

## I'm currently having some problems with my nvidia trx 4060 ti 16gb gpu. 

## Describe: 
- I previously asked everyone for help in finding a suitable gpu so I could build a PC to use as a server to deploy some weak AI (computer vision type) and after a period of research, I chose the rtx 4060 ti 16gb .
- Then I bought it and installed it on my PC with the following parameters:
    - **cpu**

   ```cmd
    Architecture:           x86_64
    CPU op-mode(s):       32-bit, 64-bit
    Address sizes:        39 bits physical, 48 bits virtual
    Byte Order:           Little Endian
    CPU(s):                 8
    On-line CPU(s) list:  0-7
    Vendor ID:              GenuineIntel
    Model name:           Intel(R) Core(TM) i3-10105F CPU @ 3.70GHz
        CPU family:         6
        Model:              165
        Thread(s) per core: 2
        Core(s) per socket: 4
        Socket(s):          1
        Stepping:           3
        CPU max MHz:        4400.0000
        CPU min MHz:        800.0000
        BogoMIPS:           7399.70
        Flags:              fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp lm constant_tsc art
                            arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl est tm2 ssse3 sdbg fma cx16 xtpr pdcm pcid sse4_1 sse
                            4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3dnowprefetch cpuid_fault epb invpcid_single ssbd ibrs ibpb stibp ibrs_enhanced fsgs
                            base tsc_adjust bmi1 avx2 smep bmi2 erms invpcid mpx rdseed adx smap clflushopt intel_pt xsaveopt xsavec xgetbv1 xsaves dtherm ida arat pln pts hwp hwp_notify hwp_ac
                            t_window hwp_epp md_clear flush_l1d arch_capabilities
    Caches (sum of all):
    L1d:                  128 KiB (4 instances)
    L1i:                  128 KiB (4 instances)
    L2:                   1 MiB (4 instances)
    L3:                   6 MiB (1 instance)
    NUMA:
    NUMA node(s):         1
    NUMA node0 CPU(s):    0-7
    Vulnerabilities:
    Gather data sampling: Mitigation; Microcode
    Itlb multihit:        KVM: Mitigation: VMX unsupported
    L1tf:                 Not affected
    Mds:                  Not affected
    Meltdown:             Not affected
    Mmio stale data:      Mitigation; Clear CPU buffers; SMT vulnerable
    Retbleed:             Mitigation; Enhanced IBRS
    Spec rstack overflow: Not affected
    Spec store bypass:    Mitigation; Speculative Store Bypass disabled via prctl and seccomp
    Spectre v1:           Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Spectre v2:           Mitigation; Enhanced IBRS, IBPB conditional, RSB filling, PBRSB-eIBRS SW sequence
    Srbds:                Mitigation; Microcode
    Tsx async abort:      Not affected

   ```

    - **ubuntu-server**

     ```cmd
    PRETTY_NAME="Ubuntu 22.04.4 LTS"
    NAME="Ubuntu"
    VERSION_ID="22.04"
    VERSION="22.04.4 LTS (Jammy Jellyfish)"
    VERSION_CODENAME=jammy
    ID=ubuntu
    ID_LIKE=debian
    HOME_URL="https://www.ubuntu.com/"
    SUPPORT_URL="https://help.ubuntu.com/"
    BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
    PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
    UBUNTU_CODENAME=jammy

    ```

- Of course, I have installed the gpu in my computer and confirmed that it has received it. I use the command:
```cmd
lspci | grep -i nvidia
```
then it returns the following result:
```cmd
01:00.0 VGA compatible controller: NVIDIA Corporation AD106 [GeForce RTX 4060 Ti 16GB] (rev a1)
01:00.1 Audio device: NVIDIA Corporation Device 22bd (rev a1)
```

- So it's clear that the device has recognized the gpu, then I installed the nvidia driver.
    - This is the result when running this command:
    ```cmd
    nvidia-settings --help
    ```
    ```cmd
    nvidia-settings:  version 510.47.03
    The NVIDIA Settings tool.

    This program is used to configure the NVIDIA Linux graphics driver.
    For more detail, please see the nvidia-settings(1) man page.


    nvidia-settings [options]

    ```
    - In addition, I also checked on the system using this command, it came out as follows:
    ```cmd
    cat /proc/driver/nvidia/version
    ```
    ```cmd
    NVRM version: NVIDIA UNIX Open Kernel Module for x86_64  535.161.07  Release Build  (dvs-builder@U16-I1-N08-15-4)  Sat Feb 17 23:21:39 UTC 2024
    GCC version:  gcc version 11.4.0 (Ubuntu 11.4.0-1ubuntu1~22.04)
    ```

- But the problem I encountered is that when I installed the driver and was planning to use the gpu card, I checked the command.
```cmd
nvidia-smi
```
Then it says device not found.
```cmd
No devices were found
```
## Request
-Currently, I'm not very strong in linux (now I'm just starting to learn again, because before in school I only learned a few basic commands and didn't dig deep to build such a system). But right now, my boss is giving me a bit of a rush, so I want to quickly fix this error, and the linux base can be added later (because I've been trying to fix this error for nearly a week now but there's been no progress).
- To be honest, in the past I was a bit subjective and didn't learn linux thoroughly, but searched for how to install nvidia driver for linux server and followed them. (both official sites and some forums). So now it doesn't work and I don't know where the error lies.
- I hope that if you have ever encountered this error, you can suggest me some keys or point me in some directions to find out.

## Guess 
- After learning this, I also understand a bit more about the linux system, so I think it's very possible that when I installed linux on my computer, there was some wrong operation that caused it to not recognize it, or when I installed the nvidia drive, it happened. There's something wrongly installed that's causing it not to recognize it.
- Before switching to a linux server, I installed nvidia drive on Windows 10 of this machine and it worked, so maybe it's not a hardware error and I can still use linux to install python libraries and run docker on it. So maybe Linux also runs fine.


## Thank you everyone for reading.