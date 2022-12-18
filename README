# Windows-QEMU-Passthrough

This project is my series of steps for virtualizing Windows on my home PC, passing through my GPU and games drive to the guest VM.

Inspiration for this project was taken from [joeknock90](https://github.com/joeknock90/Single-GPU-Passthrough). I'm using some of his scripts as a template, but mostly I'm using their README as a jumping off point.

## Relevant Environment Details

### Hardware Info

Paraphrased from `lshw`...

```text
  *-core
       description: Motherboard
       product: MAG B550 TOMAHAWK (MS-7C91)
     *-memory
          description: System Memory
          slot: System board or motherboard
          size: 16GiB
        *-bank:1
             description: DIMM DDR4 Synchronous Unbuffered (Unregistered) 3600 MHz (0.3 ns)
             slot: DIMM 1
             size: 8GiB
             clock: 3600MHz (0.3ns)
        *-bank:3
             description: DIMM DDR4 Synchronous Unbuffered (Unregistered) 3600 MHz (0.3 ns)
             slot: DIMM 1
             size: 8GiB
             clock: 3600MHz (0.3ns)
     *-cpu
          description: CPU
          product: AMD Ryzen 5 5600X 6-Core Processor
          vendor: Advanced Micro Devices [AMD]
          slot: AM4
          capabilities: lm fpu fpu_exception wp vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt pdpe1gb rdtscp x86-64 constant_tsc rep_good nopl nonstop_tsc cpuid extd_apicid aperfmperf rapl pni pclmulqdq monitor ssse3 fma cx16 sse4_1 sse4_2 x2apic movbe popcnt aes xsave avx f16c rdrand lahf_lm cmp_legacy svm extapic cr8_legacy abm sse4a misalignsse 3dnowprefetch osvw ibs skinit wdt tce topoext perfctr_core perfctr_nb bpext perfctr_llc mwaitx cpb cat_l3 cdp_l3 hw_pstate ssbd mba ibrs ibpb stibp vmmcall fsgsbase bmi1 avx2 smep bmi2 erms invpcid cqm rdt_a rdseed adx smap clflushopt clwb sha_ni xsaveopt xsavec xgetbv1 xsaves cqm_llc cqm_occup_llc cqm_mbm_total cqm_mbm_local clzero irperf xsaveerptr rdpru wbnoinvd arat npt lbrv svm_lock nrip_save tsc_scale vmcb_clean flushbyasid decodeassists pausefilter pfthreshold avic v_vmsave_vmload vgif v_spec_ctrl umip pku ospke vaes vpclmulqdq rdpid overflow_recov succor smca fsrm cpufreq
     *-pci:0
          description: Host bridge
          product: Starship/Matisse Root Complex
        *-pci:0
             description: PCI bridge
             capabilities: pci pm pciexpress msi ht normal_decode bus_master cap_list
           *-nvme
                description: NVMe device
                vendor: Micron/Crucial Technology
                logical name: /dev/nvme0
                capabilities: nvme pm msix pciexpress nvm_express bus_master cap_list
              *-namespace:2
                   description: NVMe disk
                   logical name: /dev/nvme0n1
                   size: 1863GiB (2TB)
                   capabilities: gpt-1.00 partitioned partitioned:gpt
                 *-volume:1
                      description: Windows NTFS volume
                      vendor: Windows
                      size: 1862GiB
                      capacity: 1862GiB
                      capabilities: ntfs initialized
        *-pci:2
             description: PCI bridge
           *-pci
                description: PCI bridge
              *-pci
                   description: PCI bridge
                   logical name: /dev/fb0
                   capabilities: pci pm pciexpress msi normal_decode bus_master cap_list fb
                 *-display
                      description: VGA compatible controller
                      product: Navi 21 [Radeon RX 6800/6800 XT / 6900 XT]
                      vendor: Advanced Micro Devices, Inc. [AMD/ATI]
                      logical name: /dev/fb0
                      capabilities: pm pciexpress msi vga_controller bus_master cap_list rom fb
                 *-multimedia
                      description: Audio device
                      product: Navi 21 HDMI Audio [Radeon RX 6800/6800 XT / 6900 XT]
                      vendor: Advanced Micro Devices, Inc. [AMD/ATI]
                      logical name: card0
                      logical name: /dev/snd/controlC0
                      logical name: /dev/snd/hwC0D0
                      logical name: /dev/snd/pcmC0D10p
                      logical name: /dev/snd/pcmC0D11p
                      logical name: /dev/snd/pcmC0D3p
                      logical name: /dev/snd/pcmC0D7p
                      logical name: /dev/snd/pcmC0D8p
                      logical name: /dev/snd/pcmC0D9p
                      capabilities: pm pciexpress msi bus_master cap_list
```

### Software Info

OS version info from `/etc/os-release`...

```text
VERSION="22.04 LTS"
ID_LIKE="ubuntu debian"
PRETTY_NAME="Pop!_OS 22.04 LTS"
VERSION_ID="22.04"
VERSION_CODENAME=jammy
```
Kernel info from `uname -r`:

```text
6.0.6-76060006-generic
```

## Project Setup

To set up for this project, you need to have:

- A downloaded Windows installation ISO

## Project Usage

## Setup

Each script in the `setup` directory is a step in the setup process, intended to be executed in numberical step order (01_, 02_, etc..) to go from zero to running a Windows VM guest and passing my GPU and games drive to it.

## Hooks

Scripts in the `hooks` directory will be run every time the VM starts or stops. They are moved to the appropriate locations to accomplish this during the setup process.

## Exec

Scripts in the `exec` directory are used to start the VM itself.

## Contribution Format

Major OS changes (moving from Pop!_OS to Arch, for example) will be represented by maintaining a new branch. Any sites where commands are gathered from will be cited in the script those commands are used in, to reference in the future.
