# Virtualization on Ubuntu 20.04

* Date: 2020-07-23
* By: Dion Dresschers
* License: CC BY-SA 4.0
* Version: 2020-07-23 16:57:37
* Inspired by: [Linux Foundation Cert Prep: HTTP Services (Ubuntu)](https://www.linkedin.com/learning/linux-foundation-cert-prep-http-services-ubuntu/welcome)

---

# Check

1. Check if the processor supports virtualization:
    * `cat /proc/cpuinfo | grep -E "(vmx|svm)"`
    * [x86 virtualization - Wikipedia](https://en.wikipedia.org/wiki/X86_virtualization#AMD_virtualization_.28AMD-V.29)
    [x86 virtualization - Wikipedia](https://en.wikipedia.org/wiki/X86_virtualization)
    * Result:
        ```
        flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl vmx smx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm cpuid_fault epb pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid fsgsbase smep erms xsaveopt dtherm arat pln pts md_clear flush_l1d
        flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl vmx smx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm cpuid_fault epb pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid fsgsbase smep erms xsaveopt dtherm arat pln pts md_clear flush_l1d
        flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl vmx smx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm cpuid_fault epb pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid fsgsbase smep erms xsaveopt dtherm arat pln pts md_clear flush_l1d
        flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf pni pclmulqdq dtes64 monitor ds_cpl vmx smx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm cpuid_fault epb pti ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid fsgsbase smep erms xsaveopt dtherm arat pln pts md_clear flush_l1d        
        ```

# Installing

1. Installing QEMU and QEMU-KVM
    `apt install qemu qemu-kvm`
1. See all the installed programs:
    * `ls /usr/bin | grep -E "^qemu"`
    * results in:

        ```
        qemu-img
        qemu-io
        qemu-nbd
        qemu-pr-helper
        qemu-system-i386
        qemu-system-x86_64
        qemu-system-x86_64-spice
        ```
1. See the docuement:
    `man qume-system`
1. Create a virtual disk of the type/format QCOW (Copy On Write), which is Thin Provisioned, 60G large and has the filename `my-image.qcow2` :
    `qemu-img create -f qcow2 <my-image.qcow2> 60G`
dion@intel-desktop:~$ qemu-img create -f qcow2 my-image.qcow2 60G
Formatting 'my-image.qcow2', fmt=qcow2 size=64424509440 cluster_size=65536 lazy_refcounts=off refcount_bits=16
dion@intel-desktop:~$ ls my-image.qcow2 
my-image.qcow2


