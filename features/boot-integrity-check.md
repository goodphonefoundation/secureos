# Boot integrity check

To ensure that the device is running on an authentic version of Secure OS and that no system applications have been manipulated, the device performs a custom partition validation, starting from the hardware-protected root of trust, continuing with the bootloader, the boot partition, and other partitions such as the system, vendor, and OEM.

Each stage verifies the integrity of the next, by calculating and comparing the current hash value of each partition with the expected one.

If at any point in the verification, the expected hash value doesn’t match the calculated one, the boot-up process will be terminated and the user will not be able to access the device.&#x20;

{% hint style="info" %}
The Boot Integrity Check process is initiated every time the device is booted (after turning it on or restarting it).
{% endhint %}
