# Security policies

### About the feature

One of the core features of Secure OS is the capability to manage device policies, allowing users to configure the device to address their cyber threat profile.&#x20;

Security Policies allow users to enable and/or disable device sensors, services, and different functions based on their preferences.&#x20;



### How to access the feature

Device users can interact and set up their security policies via the Phone Manager system application. Only users with a "Power user" account level can manage their own security policies through the device.

{% hint style="info" %}
The Security Policies can be accessed in one of the following ways:

1. Upon initial enrollment: the user is prompted to set up their security policies upon initial enrollment. Users can decide to skip it and set up their policies later
2. Accessed via: Settings > My Account > Phone Manager
3. Accessed via: Phone Manager widget on the home screen (available for some device models)
{% endhint %}



Below is the list of Security Policies users can manage.

### Hardware Policies

Includes settings related to the availability of functions delivered by hardware components. When disabled, applications will not be able to provide functions that require the use of these components even if applications are granted access to these components.

{% hint style="success" %}
How to access: Phone Manager > Manage Hardware
{% endhint %}

<details>

<summary>Camera</summary>

Allows users to disable device cameras. Users can disable both rear and front cameras or disable only front or rear cameras.&#x20;

</details>

<details>

<summary>Location access</summary>

Allows users to disable access to location services by the device.&#x20;

#### Extension:

As an extension to the function, a spoof location can be set which will use a predefined and fixed location value instead of the real device location.

</details>

<details>

<summary>USB</summary>

Allows users to disable USB functions including File Transfer, MIDI, PTP for connected devices. Disabling the USB will not prevent the device from charging through it.

</details>

<details>

<summary>Bluetooth</summary>

Allows users to disable Bluetooth connection on the device.

</details>

<details>

<summary>WiFi</summary>

Allows users to disable WiFi connectivity functions on the device.

</details>

<details>

<summary>Screenshots</summary>

Allows users to disable screenshot taking on the device. The screenshot-taking permissions affect screenshot-taking through any application, including system or third-party applications.

</details>

<details>

<summary>Microphone</summary>

Allows users to disable the usage of the microphone on the device. Disabling the microphone will prevent all voice functionality including calls, push-to-talk messages, audio recording, and audio feed on recorded videos.

</details>

<details>

<summary>Fingerprint</summary>

Allows users to disable the usage of the fingerprint sensor on the device.

</details>

<details>

<summary>Developer options</summary>

Allows users to disable the Developer options on the device.

</details>



### Device Policies

Includes settings related to the availability of different device functions. When disabled the functions will not be accessible by any application.

{% hint style="success" %}
How to access: Phone Manager > Manage Device
{% endhint %}

<details>

<summary>Phone/Voice services</summary>

Allows users to disable voice services on the device. When disabled it restricts all incoming and outgoing telephony calls on the device. VoIP calls made through apps (such as Secure Chat) are not restricted.&#x20;

</details>

<details>

<summary>SMS/MMS</summary>

Allows users to disable SMS and MMS services on the device. When disabled it restricts all incoming and outgoing SMS or MMS messages, including silent SMS or MMS. Chat messages made through apps (such as Secure Chat) are not restricted.&#x20;

</details>

<details>

<summary>Micro G Services</summary>

Allows users to disable Micro G services on the device. When disabled, the following services will be affected:

* Location services will not be provided
* Push notifications will not be provided for third-party apps that do not have a dedicated notification delivery service.

</details>

<details>

<summary>Manage Screen timeout</summary>

Allows users to disable the capability to change the screen timeout on the device. Devices with disabled screen timeout will use the default screen timeout.

</details>

<details>

<summary>Scrambled Lockscreen Numpad</summary>

Allows users to enable a scrambled lock screen numpad feature. The scrambled numpad is affecting the device lock screen.

</details>

<details>

<summary>Sync interval / Max failed sync</summary>

Allows users to change the frequency of the sync between device and server.&#x20;

The Sync interval in combination with Max failed sync determines the threshold set by the user for the maximum allowed time for the device to be "offline". When the threshold is reached, an automated device wipe flow will trigger and delete all of the device data.&#x20;

For example, if the Sync interval is 4 hours, and the Max Failed Sync is set to 50, the device will wipe if it fails to sync 50 times in a row, with an attempt to sync every 4 hours (wiping the phone if it is offline for 200 hours).

</details>

<details>

<summary>Can download updates on Mobile Data</summary>

Allows users to disable OS updates downloading via Mobile Data, requiring a WiFi connection to download the OS update.&#x20;

</details>

<details>

<summary>Allow installation of 3rd party apps</summary>

Allows users to disable installation of any software outside of the System App Store. When disabled, no software can be installed through any third-party App Store or a local install (e.g. APK file).

</details>

<details>

<summary>Allow apps full device access</summary>

Allows users to restrict third-party applications from getting device access. Enabling this will not automatically grant access to third-party applications. To do that, users should enable this policy and also grant each app the accesses they need, from Settings > Privacy > Permission Manager or from Settings > Apps & notifications > (select app) > Permissions

</details>



### Account Policies

Includes settings related to the user account on devices.

{% hint style="success" %}
How to access: Phone Manager > Manage Account
{% endhint %}

<details>

<summary>Re-enrollment</summary>

Users can disable account re-enrollment, which will prevent enrollment with the same account on the same or another device.&#x20;

</details>

<details>

<summary>Enable WIPE password</summary>

Allows users to set a WIPE PIN used for instant device wipe when the selected PIN is entered on device unlock.

</details>

<details>

<summary>Update account password</summary>

Allows users to restrict the change of their user account password.

</details>



### Sensor Policies

Includes settings related to the availability and functionality of the device sensors.&#x20;

{% hint style="success" %}
How to access: Phone Manager > Manage Sensor
{% endhint %}

<details>

<summary>Accelerometer</summary>

Allows users to disable the accelerometer sensor used to measure the acceleration force in m/s2 that is applied to a device on all three physical axes (x, y, and z), including the force of gravity.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Geomagnetic field</summary>

Allows users to disable the geomagnetic field sensor used to measure the ambient geomagnetic field for all three physical axes (x, y, z) in μT.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Gravity</summary>

Allows users to disable the gravity sensor used to measure the force of gravity in m/s2 that is applied to a device on all three physical axes (x, y, z).

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Gyroscope</summary>

Allows users to disable the gyroscope sensor used to measure a device's rate of rotation in rad/s around each of the three physical axes (x, y, and z).

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Light</summary>

Allows users to disable the light sensor used to measure the ambient light level (illumination) in lx.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Linear acceleration</summary>

Allows users to disable the linear acceleration sensor used to measure the acceleration force in m/s2 that is applied to a device on all three physical axes (x, y, and z), excluding the force of gravity.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Orientation</summary>

Allows users to disable the orientation sensor used to measure degrees of rotation that a device makes around all three physical axes (x, y, z).&#x20;

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Proximity</summary>

Allows users to disable the proximity sensor used to measure the proximity of an object relative to the view screen of a device. This sensor is typically used to determine whether a handset is being held up to a person's ear.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>

<details>

<summary>Rotation vector</summary>

Allows users to disable the rotation vector sensor used to measure the orientation of a device by providing the three elements of the device's rotation vector.

#### Extension:

As an extension to the function, the user can spoof the values of the sensor.

</details>
