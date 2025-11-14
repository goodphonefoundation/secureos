# Device wipe

Device Wipe is the process of deleting all device data and logging out of the user account.

The device Wipe is useful when the user has lost access to their device, or if the user is offboarded from the organization.&#x20;

Secure OS supports the following Wipe flows:



### Automated Wipe

Devices are getting automatically wiped if the user fails to enter the right screenlock PIN/password for 10 consecutive times in a row.&#x20;



### Duress Wipe

The user can use a duress wipe action that triggers a device wipe if they enter a predefined PIN (Wipe PIN) in the lock screen menu. The user can set up their Duress Wipe from their Account Policy in Phone Manager (<mark style="background-color:green;">how to</mark>: [#enable-wipe-password](security-policies.md#enable-wipe-password "mention"))



### Remote Wipe

The device can be remotely wiped by the MDM administrator through an instant Wipe command. The device will be wiped as long as has connectivity.



### Failed Sync Wipe

Users can set up a Failed Sync Wipe flow that will trigger a device Wipe in case the device fails to sync to the server for "n" number of times (also meaning that the device is offline). This feature ensures that the device will get wiped even if it loses connectivity and is unable to receive a remote wipe command from the MDM.&#x20;

(<mark style="background-color:green;">how to:</mark> [#sync-interval-max-failed-sync](security-policies.md#sync-interval-max-failed-sync "mention"))



### Emergency Wipe

The user can also initiate a device wipe from their Emergency menu in Secure OS.&#x20;

(<mark style="background-color:green;">how to:</mark> Hold power button > Emergency > SOS and data reset



{% hint style="info" %}
The combination of device wipe and Re-enrollment disabled by policy (<mark style="background-color:green;">how to:</mark> [#re-enrollment](security-policies.md#re-enrollment "mention")) renders the account no longer accessible, regardless of whether the user enters the right username and password.&#x20;
{% endhint %}

