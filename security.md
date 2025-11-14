---
description: >-
  This section covers how Secure OS addresses techniques used by adversaries to
  gain access to the mobile device and its data on.
---

# Security

An attack technique can be addressed in the following ways:

* Prevention - building mechanisms that prevent the success of the technique. This is a preferred way to address the issue;
* Detection - building mechanisms to detect once the technique has succeeded. This is needed in case there are no preventative mechanisms in place, or in case the preventative mechanisms fail.

### Collection attacks

Collection attacks consist of techniques used to identify and gather information, such as sensitive files, from a target network prior to exfiltration. This category also covers locations on a system or network where the adversary may look for information to exfiltrate.

<details>

<summary>Keylogging</summary>

**Description of attack**

Adversaries may log user keystrokes to intercept credentials or other information from the user as the user types them.

Mostly that’s done through masquerading as a legitimate third-party keyboard to record user keystrokes.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed by the MDM thus ensuring that no untrusted keyboard app gets installed. \
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users will be alerted if a third-party keyboard, not distributed by the organization, has been installed on the device. \
  &#x20;<mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Location capture</summary>

**Description of attack**

Adversaries may track a device’s physical location through use of standard operating system APIs via malicious or exploited applications on the compromised device.

**Prevention**

* Security policy: Users can disable the location services on OS API framework level, preventing any application from accessing the function.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Location Access_ from [#hardware-policies](features/security-policies.md#hardware-policies "mention")

- Device Integrity report: Users will be alerted if a malicious app collecting screen feed has been installed on the device.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Adversary-in-the-Middle</summary>

**Description of attack**

Adversaries may attempt to position themselves between two or more networked devices to support follow-on behaviors such as Transmitted Data Manipulation or Endpoint Denial of Service.

Adversary-in-the-Middle can be achieved through several mechanisms. The most common is through a malicious application that registers itself as a VPN client, effectively redirecting device traffic to adversary-owned resources. A malicious application with escalation privileges can gain access to network traffic.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed by the MDM thus ensuring that no untrusted VPN app gets installed.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users will be alerted if a VPN app, not distributed by the organization, has been installed on the device.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Audio capture</summary>

**Description of attack**

Adversaries may capture audio to collect information by leveraging standard operating system APIs of a mobile device. Examples of audio information adversaries may target include user conversations, surroundings, phone calls, or other sensitive information

**Prevention**

* Security policy: Users can disable the use of the microphone on OS hardware abstraction level, preventing any applications from accessing it.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Microphone_ from [#hardware-policies](features/security-policies.md#hardware-policies "mention")

**Detection**

* Device Integrity report: Users will be alerted if a malicious app collecting audio feed has been installed on the device.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Screen capture</summary>

**Description of attack**

Adversaries may use screen capture to collect additional information about a target device, such as applications running in the foreground, user data, credentials, or other sensitive information. Applications running in the background can capture screenshots or videos of another application running in the foreground by using the Android `MediaProjectionManager.`

**Prevention**

* Security policy: Users can disable the screenshot function on OS level, preventing any application from accessing the function.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Screenshots_ from [#hardware-policies](features/security-policies.md#hardware-policies "mention")

**Detection**

* Device Integrity report: Users will be alerted if a malicious app collecting screen feed has been installed on the device.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Sensor values capture</summary>

**Description of attack**

Adversaries may collect a device’s sensor values (accelerometer, gravity, orientation, etc.) through use of standard operating system APIs via malicious or exploited applications on the compromised device. With the information, the adversaries can get more contextual information about the user's device.

**Prevention**

* Security policy: Users can disable or spoof the device sensors on OS hardware abstraction level, preventing any application from accessing the data. \
  <mark style="background-color:green;">How to prevent:</mark> Disable _Sensors_ from [#sensor-policies](features/security-policies.md#sensor-policies "mention") \
  :warning:Disabling sensors is not recommended due to the effect it may have on services.&#x20;

**Detection**

* Device Integrity report: Users will be alerted if a malicious app collecting sensor values has been installed on the device.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Silent SMS</summary>

**Description of attack**

The adversary sends a spoofed or silent SMS to retrieve the subscriber profile identifier and thus track the device's location. Silent SMS attacks are initiated without notifying the user.

**Prevention**

* Security policy: Users can disable the voice and SMS services on OS framework level, preventing silent SMS and silent calls from executing.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _SMS/MMS_ from [#device-policies](features/security-policies.md#device-policies "mention")

</details>

<details>

<summary>Silent call</summary>

**Description of attack**

The adversary initiaties a silent Call to retrieve the subscriber profile identifier and thus track the device's location. Silent Call attacks are initiated without notifying the user.

**Prevention**

* Security policy: Users can disable the voice and SMS services on OS framework level, preventing silent SMS and silent calls from executing.\
  <mark style="background-color:green;">How to prevent</mark>: Disable Phone/Voice services from [#device-policies](features/security-policies.md#device-policies "mention")

</details>



### Initial access attacks

The initial access tactic represents the vectors adversaries use to gain an initial foothold onto a mobile device.

<details>

<summary>Drive-by compromise</summary>

**Description of attack**

Adversaries may gain access to a device through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is typically targeted for exploitation. The technique works by installing malicious software on the device used to spy on the user by recording information such as: keystrokes, screen recording, etc.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed by the MDM. \
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users can access a report comparing the application version installed on the phone and the application version permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Application versioning</summary>

**Description of attack**

An adversary may push an update to a previously benign application to add malicious code. This can be accomplished by pushing an initially benign, functional application to a trusted application store, such as the Google Play Store or the Apple App Store. This allows the adversary to establish a trusted user base that may grant permissions to the application before introducing malicious code. Then, an application update could be pushed to introduce malicious code.

**Prevention**

* Security policy: The allowed applications are updated only from the MDM, preventing any unwanted application updates. \
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

**Detection**

* Device Integrity report: Users can access a report comparing the application version installed on the phone and the application version permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Lock screen bypass</summary>

**Description of attack**

An adversary with physical access to a mobile device may seek to bypass the device’s lock screen. Several methods exist to accomplish this, including:

* Brute force: An adversary could attempt to brute-force the device password.
* Thermal: Thermal cameras can capture the heat left by fingers on a touchscreen. The residual heat pattern can reveal the sequence of touches or the shape of a pattern.

**Prevention**

* Scrambled PIN: the OS introduces a scrambled PIN pad used for unlocking the device. The scrambled PIN pad ensures that patterns through Thermal images can not be identified\
  <mark style="background-color:green;">How to prevent:</mark> Enable Scrambled Lockscreen Numpad from [#device-policies](features/security-policies.md#device-policies "mention")
* Security policy: The user is allowed for a maximum of 10 unsuccessful attempts to unlock the device. After reaching the 10th unsuccessful attempt in a row, the device will get wiped. \
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

</details>

<details>

<summary>Phishing</summary>

**Description of attack**

Adversaries may send malicious content to users in order to gain access to their mobile devices. All forms of phishing are electronically delivered social engineering. Adversaries can conduct both non-targeted phishing, such as in mass malware spam campaigns, as well as more targeted phishing tailored for a specific individual, company, or industry, known as "spearphishing". The technique works by installing malicious software on the device used to spy on the user by recording information such as keystrokes, screen recording, etc.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed through the MDM. \
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users can access a report comparing applications installed on the phone and applications permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Replication Through Removable Media</summary>

**Description of attack**

Adversaries may move onto devices by exploiting or copying malware to devices connected via USB. In the case of Lateral Movement, adversaries may utilize the physical connection of a device to a compromised or malicious charging station or PC to bypass application store requirements and install malicious applications directly.

**Prevention**

* Locked bootloader: Secure OS-powered devices are with locked bootloaders, preventing arbitrary operating system code from being flashed onto the device.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.
* Security policy: users can restrict the file transfer functionality of the USB port, thus preventing the ability of adversaries from transferring malicious software to the device.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _USB_ from [#hardware-policies](features/security-policies.md#hardware-policies "mention")
* Remote device wipe: Users can remotely wipe the device, either by initiating a device wipe command (available when the device is online) or by setting an automated wipe flow triggering when the device has been offline for a period selected by the user.\
  <mark style="background-color:green;">How to wipe:</mark> [device-wipe.md](features/device-wipe.md "mention")

</details>

<details>

<summary>Impersonalization attack</summary>

**Description of attack**

Adversaries may use the victim's credentials to log into their user account from another device. Through that adversaries obtain information backed by the user in the cloud.&#x20;

**Prevention**

* Device backup encryption: The optional device backup is fully encrypted, requiring the user to enter a backup password requiring the adversary with an enrolled user account to guess the backup password as well.
* Security policy: users can forbid account re-enrollment, preventing anyone else from enrolling their account on a new device or on the same device after the device wipe, technically making the account completely inaccessible. \
  <mark style="background-color:green;">How to prevent:</mark> Disable Re-enrollment from [#account-policies](features/security-policies.md#account-policies "mention")

</details>



### Execution attacks

Execution consists of techniques that result in adversary-controlled code running on a mobile device. Techniques that run malicious code are often paired with techniques from all other tactics to achieve broader goals, like exploring a network or stealing data.

<details>

<summary>Command scripting</summary>

**Description of attack**

Adversaries may abuse command and script interpreters to execute commands, scripts, or binaries. These interfaces and languages provide ways of interacting with computer systems and are a common feature across many different platforms. Most systems come with some built-in command-line interface and scripting capabilities, for example, Android is a UNIX-like OS and includes a basic Unix Shell that can be accessed via the Android Debug Bridge (ADB) or Java’s Runtime package.

**Prevention**

* Hardware-based attestation: Secure OS utilizes a hardware-based device attestation designed to prevent the device from starting in case it has been rooted or jailbroken.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

</details>

<details>

<summary>Exploitation of client execution</summary>

**Description of attack**

Adversaries may exploit software vulnerabilities in client applications to execute code. Vulnerabilities can exist in software due to insecure coding practices that can lead to unanticipated behavior. Adversaries may take advantage of certain vulnerabilities through targeted exploitation for the purpose of arbitrary code execution. Oftentimes the most targeted applications are system applications since they come preinstalled with full device access.

**Mitigation**

* System apps: Secure OS contains a very limited amount of system applications (8-12 depending on policies), in comparison to Samsung and iPhone devices with over 50 preinstalled apps. \
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

</details>



### Persistence attacks

Persistence is any access, action, or configuration change to a mobile device that gives an attacker a persistent presence on the device. Attackers often will need to maintain access to mobile devices through interruptions such as device reboots and potentially even factory data resets.

<details>

<summary>Boot or Logon Initialization Scripts</summary>

**Description of attack**

Adversaries may use scripts automatically executed at boot or logon initialization to establish persistence. Initialization scripts are part of the underlying operating system and are not accessible to the user unless the device has been rooted or jailbroken.

**Prevention**

* Hardware-based attestation: Secure OS utilizes a hardware-based device attestation designed to prevent the device from starting in case it has been rooted or jailbroken.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.
* Locked bootloader: Secure OS-powered devices are with locked bootloaders, preventing arbitrary operating system code from being flashed onto the device.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

**Detection**

* Device Integrity report: Users can access a report comparing device settings and settings permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Compromise Client Software Binary</summary>

**Description of attack**

Adversaries may modify system software binaries to establish persistent access to devices. System software binaries are used by the underlying operating system and users over adb or terminal emulators.

Adversaries may make modifications to client software binaries to carry out malicious tasks when those binaries are executed. For example, malware may come with a pre-compiled malicious binary intended to overwrite the genuine one on the device. Since these binaries may be routinely executed by the system or user, the adversary can leverage this for persistent access to the device.

**Prevention**

* Hardware-based attestation: Secure OS utilizes a hardware-based device attestation designed to prevent the device from starting in case it has been rooted or jailbroken.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.
* Locked bootloader: Secure OS-powered devices are with locked bootloaders, preventing arbitrary operating system code from being flashed onto the device.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

**Detection**

* Device Integrity report: Users can access a report comparing device settings and settings permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Event Triggered Execution</summary>

**Description of attack**

Adversaries may establish persistence using system mechanisms that trigger execution based on specific events. Mobile operating systems have means to subscribe to events such as receiving an SMS message.

Adversaries may abuse these mechanisms as a means of maintaining persistent access to a victim via automatically and repeatedly executing malicious code. After gaining access to a victim’s system, adversaries may create or modify event triggers to point to malicious content that will be executed whenever the event trigger is invoked.

**Prevention**

* Security policy: users can limit the device attack surface by disabling device services, including SMS, Voice calls, etc.\
  <mark style="background-color:green;">How to prevent:</mark> disable SMS/MMS and Voice services from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users can access a report comparing device settings and settings permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Foreground persistence</summary>

**Description of attack**

Adversaries may abuse Android's startForeground() API method to maintain continuous sensor access, including camera, microphone, gyroscope, etc.. Applications can retain sensor access by running in the foreground, using Android’s startForeground() API method.

**Prevention**

* Security policy: users can limit the device attack surface by disabling device sensors, including WiFi, Bluetooth, Locations, USB, fingerprint, accelerometer, gyroscope, etc.\
  <mark style="background-color:green;">How to prevent:</mark> Disable unused _Hardware_ and _Sensors_ from [#hardware-policies](features/security-policies.md#hardware-policies "mention") and [#sensor-policies](features/security-policies.md#sensor-policies "mention")

**Detection**

* Device Integrity report: Users can access a report comparing device settings and settings permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>



### Privilege escalation attacks

Privilege escalation includes techniques that allow an attacker to obtain a higher level of permissions on the mobile device. Attackers may enter the mobile device with very limited privileges and may be required to take advantage of a device weakness to obtain higher privileges necessary to successfully carry out their mission objectives.

<details>

<summary>Exploitation for Privilege Escalation</summary>

**Description of attack**

Adversaries may exploit software vulnerabilities in order to elevate privileges. Exploitation of a software vulnerability occurs when an adversary takes advantage of a programming error in an application, service, within the operating system software, or kernel itself to execute adversary-controlled code. Security constructions, such as permission levels, will often hinder access to information and the use of certain techniques. Adversaries will likely need to perform privilege escalation to include the use of software exploitation to circumvent those restrictions.

**Prevention**

* Hardware-based attestation: Secure OS utilizes a hardware-based device attestation designed to prevent the device from starting in case it has been rooted or jailbroken.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

**Detection**

* Device Integrity report: Users can access a report comparing device settings and settings permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>



### Defense evasion attacks

Defense evasion consists of techniques an adversary may use to evade detection or avoid other defenses. Sometimes these actions are the same as or variations of techniques in other categories that have the added benefit of subverting a particular defense or mitigation. Defense evasion may be considered a set of attributes the adversary applies to all other phases of the operation.

<details>

<summary>Hooking</summary>

**Description of attack**

Adversaries may utilize hooking to hide the presence of artifacts associated with their behaviors to evade detection. Hooking can be used to modify return values or data structures of system APIs and function calls. This process typically involves using 3rd party root frameworks, with either a system exploit or pre-existing root access.

**Prevention**

* Hardware-based attestation: Secure OS utilizes a hardware-based device attestation designed to prevent the device from starting in case it has been rooted or jailbroken.\
  How to prevent: Native OS feature.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.
* Locked bootloader: Secure OS powered devices are with locked bootloaders, preventing arbitrary operating system code from being flashed onto the device.\
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

</details>

<details>

<summary>Impair Defenses</summary>

**Description of attack**

Adversaries may maliciously modify components of a victim's environment in order to hinder or disable defensive mechanisms. This not only involves impairing preventative defenses, such as anti-virus, but also detection capabilities that defenders can use to audit activity and identify malicious behavior. This may span both native defenses as well as supplemental capabilities installed by users or mobile endpoint administrators.

**Prevention**

* Boot integrity check: Secure OS initiates a boot integrity check that verifies that no unauthorized modification of system files has been done. The device does not start if the boot integrity check doesn't pass. \
  <mark style="background-color:green;">How to prevent:</mark> Initiated automatically by design.

</details>

<details>

<summary>Obfuscated Files or Information</summary>

**Description of attack**

Adversaries may attempt to make a payload or file difficult to discover or analyze by encrypting, encoding, or otherwise obfuscating its contents on the device or in transit. This is common behavior that can be used across different platforms and the network to evade defenses.

Payloads may be compressed, archived, or encrypted in order to avoid detection. These payloads may be used during Initial Access or later to mitigate detection. Portions of files can also be encoded to hide the plaintext strings that would otherwise help defenders with discovery. Payloads may also be split into separate, seemingly benign files that only reveal malicious functionality when reassembled.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed by the MDM thus ensuring that no untrusted apps get installed.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Device Integrity report: Users can access a report comparing the application version installed on the phone and the application version permitted by the MDM. Discrepancies are triggering alerts for administrators and users.\
  <mark style="background-color:orange;">How to detect:</mark> [device-integrity-report.md](features/device-integrity-report.md "mention")

</details>

<details>

<summary>Code Signing Policy Modification</summary>

**Description of attack**

Adversaries may modify code signing policies to enable the execution of applications signed with unofficial or unknown keys. Code signing provides a level of authenticity on an app from a developer, guaranteeing that the program has not been tampered with and comes from an official source. Security controls can include enforcement mechanisms to ensure that only valid, signed code can be run on a device.

**Prevention**

* Security policy: Users can forbid the installation of any software outside of the app store managed by the MDM thus ensuring that no untrusted apps get installed. All applications distributed through the MDM require a trusted certificate prior to whitelisting the app.\
  <mark style="background-color:green;">How to prevent:</mark> Disable _Allow installation of 3rd party apps_ from [#device-policies](features/security-policies.md#device-policies "mention")

**Detection**

* Certificates report: Users can use the device settings menu to view trusted CA certificates and look for unexpected or unknown certificates.\
  <mark style="background-color:orange;">How to detect:</mark> Settings > Security > Encryption & credentials > Trusted credentials

</details>
