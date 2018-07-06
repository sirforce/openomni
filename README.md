# OpenOmni
Documentation and python library for decoding omnipod communications. [Join the Slack channel](https://omniaps.slack.com/) to discuss this work.

[![Build Status](https://travis-ci.org/openaps/openomni.svg?branch=master)](https://travis-ci.org/openaps/openomni)

## Current Status

We have figured out the [RF modulation](https://github.com/openaps/openomni/wiki/RF-Modulation) and [packet/message encoding](https://github.com/openaps/openomni/wiki). We are now working on decoding meaning of the bytes in the body for each of the [Message Types](https://github.com/openaps/openomni/wiki/Message-Types).

## Areas to focus on

There are two ways we could use help, beyond trying to crack the two byte crc at the end of messages (though if you want to tackle that, please do!):
  1. Capture data from different pods and commands using omni_listen_rfcat. If you can document what was being done with the PDM while the packets were recorded, that would be a plus, but raw data can be helpful too.  Submit these as new wiki pages and add your new page to the [Packet Captures](https://github.com/openaps/openomni/wiki/Packet-Captures) page.
  2. Start decoding fields for [individual commands](https://github.com/openaps/openomni/wiki/Message-Types). A good way to start doing this is to repeatedly perform a certain type of action on the PDM tweaking *1* thing each time, and inspecting the generated packets to see which bytes differ.

## What you'll need

One of the following.  If you use the TI stick, you will need to flash firmware onto it using a CC-Debugger.

  * [RFCat](http://int3.cc/products/rfcat)
  * [TI USB Stick](http://www.ti.com/tool/cc1111emk868-915)

## Installation

Prerequisites:
* python 2.7 (already installed on MacOS, for windows, download it [here](https://www.python.org/downloads/release/python-2714/))
* [pip](https://pip.readthedocs.io/en/stable/installing/)
* On mac, you'll need libusb. `brew install libusb` (If you don't have Homebrew installed, go here first: https://brew.sh/)

You can install openomni in editable mode like this:
```
git clone https://github.com/openaps/openomni.git
cd openomni/openomni
pip install -e . --process-dependency-links
```
** Note: You may need to add 'sudo' before the pip install line if you are using a system python install.

** Note: You can capture packets by plugging an RFCat into a USB port -- then go to the command line, and navigate to this directory:
/openomni/bin/  and type:

omni_listen_rfcat

Then issue commands from your PDM and they'll appear at the command line.


=======
##### ** Please note the details below are related to a project created to better understand how the omnipod communicates **


#### Stay Up to Date!
[Join the Slack channel](https://omniapsslack.azurewebsites.net/) to discuss this work.

#### Contributors on Slack: (in no particular order)
(To view, you must be logged into the OmniAPS Slack channel. [Click here](https://omniapsslack.azurewebsites.net/) to join.)
* [@dan](https://omniaps.slack.com/team/dan)
* [@larsonlr](https://omniaps.slack.com/team/larsonlr)
* [@t1djoe](https://omniaps.slack.com/team/t1djoe)
* [@joakimornstedt](https://omniaps.slack.com/team/joakimornstedt)
* [@pete](https://omniaps.slack.com/team/pete)
* [@marius](https://omniaps.slack.com/team/marius) 
* [@DanaMLewis](https://omniaps.slack.com/team/danamlewis)
* [@Garidan](https://omniaps.slack.com/team/garidan)
* [@SeattleBrighton](https://omniaps.slack.com/team/seattlebrighton)
* [@paul](https://omniaps.slack.com/team/paul)
* [@lytrix](https://omniaps.slack.com/team/lytrix)
* [Find out more about the NightScout community here.](https://github.com/nightscout)
* [Find out more about the OpenAPS open source DIY artificial pancreas project here.](https://openaps.org)
* Thanks for supporting this effort!!

#### Rules for Contributing to this Repository

* All code updates require the use of Pull Requests.
* Documentation updates can be made directly on master.

***
https://files.slack.com/files-pri/T0B2X082E-F0D390KTP/download/pod_datacap_23oct2015.odt
***
