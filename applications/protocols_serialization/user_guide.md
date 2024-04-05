# Protocols serialization applications testing
- [Protocols serialization applications testing](#protocols-serialization-applications-testing)
  - [Overview](#overview)
  - [Setting up nRF Connect SDK](#setting-up-nrf-connect-sdk)
  - [Install NCS](#install-ncs)
  - [Building application](#building-application)
  - [Flashing and connecting](#flashing-and-connecting)
  - [Testing](#testing)
    - [Testing BLE](#testing-ble)
    - [Testing OpenThread](#testing-openthread)

## Overview

## Setting up nRF Connect SDK

## Install NCS
Please see:
https://developer.nordicsemi.com/nRF_Connect_SDK/doc/2.6.0/nrf/installation/install_ncs.html

To initialize nrf belov command instead the one mentioned in instruction:

`west init -m https://github.com/nrfconnect/sdk-nrf --mr collab-serial-ble-ot`

## Building application

## Flashing and connecting

## Testing

### Testing BLE

In order to test BLE You will need to install `nRF Connect for Mobile`

 - IOS: https://apps.apple.com/pl/app/nrf-connect-for-mobile/id1054362403

 - Android: https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp&pcampaignid=web_share

On client site please invoke in zephyr shell:
```console
 > bt init
 > bt advertise on
```

On mobile Phone open `nRF Connect` app and scan for: `Nordic_UART_Service` as in image below.

<img src="resources/nrf_scan.jpg" alt="image" width="300" height="auto">

Tap connect.

This will connect to nRF52 and You should be able to see in zephyr Shell similar message:

```
LE conn param updated: int 0x0027 lat 0 to 42
```

To Send Data from your phone tap arrow next to Rx characteristic.

<img src="resources/nrf_send.jpg" alt="image" width="300" height="auto">

On `nRF52` you should see:

```
bt_nus: on_receive: Received data, handle 0, conn 0x200023c4
```


### Testing OpenThread
