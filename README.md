# Parrot Disco over 4G/LTE (softmod)

## About
Disco4G is a software modification (softmod) for the Parrot Disco drone. Instead of the built-in regular Wi-Fi, it allows to use a 4G/LTE cellular/mobile network connection to link Skycontroller 2 to the Disco. Control/telemetry and live video stream are routed through the 4G/LTE connection. In other words, range limit becomes your imagination! Ok, to be fair, it's still limited by the battery capacity :stuck_out_tongue_winking_eye:

[![Youtube video](https://uavpal.com/img/yt_thumbail_github.png)](https://www.youtube.com/watch?v=e9Xl3tTwReQ)
![Disco4G softmod](https://image.ibb.co/eP6A3c/disco4glte.jpg)

Pros:
- Range limit is no longer dependent on Wi-Fi signal
- Low hardware cost (around US$ 40.-)
- All stock hardware can be used (standard Parrot Skycontroller 2 with FreeFlight Pro App)
- Return-to-home (RTH) is auto-initiated in case of connection loss
- Allows independent real-time GPS tracking via [Glympse](https://www.glympse.com/get-glympse-app/)
- Easy initiation of 4G/LTE connection via Skycontroller 2 button
- Can be used for manually controlled flights as well as flight plans

Cons:
- Dependent on [4G/LTE mobile network coverage](https://en.wikipedia.org/wiki/List_of_countries_by_4G_LTE_penetration) 
- Might incur mobile data cost (dependent on your mobile network operator)
- Slightly higher latency as compared to Wi-Fi

## Why?
- The Parrot Disco's stock Wi-Fi loses video signal way before the specified 2 km.
- Because we can :grin:

## How does it work?
![High-level connection diagram](https://preview.ibb.co/c8qPP7/disco4g_highlevel_diagram_end2end.png)

In simple terms, the Wi-Fi connection is hijacked and routed via a tethering device (e.g. mobile phone) through a 4G/LTE cellular/mobile network to the Disco. As tethering device, any modern mobile phone can be used (iOS: "Personal Hotspot" or Android: "Portable WLAN hotspot").
The Disco requires a 4G/LTE USB modem to be able to send and receive data via cellular/mobile networks.

![USB Modem inside Disco's canopy](https://preview.ibb.co/g5rgNS/modem_in_disco.jpg)

Initiation of the 4G/LTE connection (and switch back to Wi-Fi) can be done by simply pressing the Settings button twice on Skycontroller 2.

![Settings Button on Skycontroller 2](https://image.ibb.co/iBWcgn/settingsbutton.jpg)

The "Power" LED on Skycontroller 2 will change to solid blue once the 4G/LTE connection to the Disco is established.

[![Skycontroller 2 with blue LED](https://image.ibb.co/f5Uz97/SC2_small_blue.jpg)](https://www.youtube.com/watch?v=SEz70ClCetM)

Once up in the air, everything works in the same manner as with the stock Wi-Fi connection, e.g. flight plans, return-to-home (auto-initiated in case of connection loss), etc.

Note: The mobile device running FreeFlight Pro (the one conneted to Skycontroller 2 via USB) can even be the same as the mobile tethering device/phone.

[ZeroTier](https://zerotier.com) is a free online service, which we use to manage the connection between Disco and Skycontroller 2. This allows to do NAT traversal which is required due to the mobile tethering device and even some modems. Whether direct 4G/LTE-internal connections are allowed depends on your mobile network operator. ZeroTier allows to connect Skycontroller 2 to your Disco via an encrypted channel, regardless of the network topology.

Additionally, [Glympse](https://www.glympse.com/get-glympse-app/), a free App for iOS/Android allows independent real-time GPS tracking of the Disco via 4G/LTE. This can be particularily useful to recover the Disco in the unfortunate event of a crash or flyaway.

![Glympse App showing Disco's location](https://image.ibb.co/kwt4bn/discoglympse.png)

## Requirements
*Hardware:*
- Parrot Disco drone
- Parrot Skycontroller 2
- [Huawei E3372 4G USB modem](https://consumer.huawei.com/en/mobile-broadband/e3372/specs/) and SIM card\
Note: there are different Huawei E3372 models available - please read [this FAQ entry](https://github.com/uavpal/disco4g/wiki/FAQ#e3372models) before buying to ensure your mobile network operator is supported.
- Antennas (2x CRC9) for the modem (optional, but recommended)
- USB OTG cable (ca. 10 cm, [angle cable](https://www.aliexpress.com/wholesale?SearchText=USB+OTG+angle) recommended)
- Mobile device/phone with Wi-Fi tethering and SIM card (for best performance, use the same operator as the USB modem's SIM card)
- PC with Wi-Fi (one-time, required for initial installation)

*Software:*
- FreeFlight Pro App on tablet/phone (can be the same device providing Wi-Fi tethering)
- Zerotier account (free)
- Glympse App for independent real-time GPS tracking (optional) - free Glympse Developer account required

*<a name="supportedhw">Successfully tested using:</a>*
- Mobile tethering device: iPhone X (iOS 11.3)
- 4G/LTE USB Modem: Huawei E3372s-153, E3372h-153, E3372h-510, E3372s-607
- USB-connected device with FreeFlight Pro App: iPad Pro (iOS 11.3), iPhone X (iOS 11.3)
- Parrot Disco, Firmware 1.4.1
- Parrot Skycontroller 2, Firmware 1.0.7
- FreeFlight Pro 5.2.0 on iOS

[Drop us a note](https://github.com/uavpal/disco4g/#contactcontribute) if you have successfully tested different configurations, so we can keep this list updated.

## Installation
Please see Wiki article [Installation](https://github.com/uavpal/disco4g/wiki/Installation).

## How to fly on 4G/LTE? (User Manual)
Please see Wiki article [How to fly on 4G/LTE? (User Manual)](https://github.com/uavpal/disco4g/wiki/How-to-fly-on-4G-LTE%3F-(User-Manual)).

## FAQ
Please see Wiki article [FAQ](https://github.com/uavpal/disco4g/wiki/FAQ).

## Is it really free? Are you crazy?
Yes and yes! This softmod has been developed over countless of days and nights by RC hobbyists and technology enthusiasts with zero commercial intention.
Anyone can download our code for free and transform his/her Disco into a 4G/LTE enabled fixed-wing drone by following the instructions provided.

_However_, we highly appreciate [feedback and active contribution](#contactcontribute) to improve and maintain this project.

![Shut up and take my money!](http://image.ibb.co/cLw9SS/shut_up_and_take_my_money.jpg)

If you insist, feel free to donate any amount you like. We will mainly use donations to acquire new hardware to be able to support a wider range of options (such as more 4G/LTE USB Modems).

[![Donate using Paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=GY3BTZPLPBB2W&lc=US&item_name=UAVPAL&cn=Add%20special%20instructions%3A&no_shipping=1&currency_code=USD&bn=PP-DonationsBF:btn_donateCC_LG.gif:NonHosted)

## Contact/Contribute
Join our [UAVPAL Slack workspace](https://join.slack.com/t/uavpal/shared_invite/enQtMzQ4NDA5NzU0MDM5LTcyNjVjMjdkMDU4ODYwYjJmZjg1MWJmMWQwYzQyOTYzZDJiNTYwNzY3MzFiMjQ1NmIwYWE2YjQ0NzdkYWFiMGQ) or check out the [issue section](https://github.com/uavpal/disco4g/issues) here on GitHub.\
Email: <img valign="bottom" src="https://image.ibb.co/mK4krx/uavpalmail2.png"> (please do not use email for issues/troubleshooting help. Join our Slack community instead!)

## Special Thanks to
- Parrot - for building this beautiful bird, as well as for promoting and supporting Free and Open-Source Software
- ZeroTier - awesome product and excellent support
- Glympse - great app and outstanding API
- Andres Toomsalu
- Brian
- John Dreadwing
- Josh Mason
- Phil

## Disclaimer
This is still an EXPERIMENTAL modification, no thorough testing has been conducted! Mod and fly your Disco at YOUR OWN RISK!!!


