---
title: "Data Communication Fundamentals"
date: 2019-01-28
categories: computer networks
tags:
- messaging
- data engineering
- network engineering
- network security
description: "An overview of the basics of data communication concepts"
---
![](/images/data_components.jpg "Diagram showing the fundamental components of a data network, described in this article.")

Concerns the basics of networking, starting with some common terminology of data transmission. This can be summarised as:

1. A sender has some data they want to send to a receiver.
2. That data needs to be converted into a message for sending.
3. The message needs to be transmitted via some form of medium.
4. The receiver needs to be able to turn that signal back into the data that has been sent.
5. Therefore a system is needed to agree on rules between the sender and receiver about how the data will be converted into a signal, transmitted and converted back to data, this is called a *protocol*.

In order for this system to be effective it needs to ensure:

**Delivery**, to the correct destination.
**Accuracy**, to ensure the data received is the same as what was sent.
**Timeliness**, there is a minimum of delay in transmission of the signal.

This effectiveness can be hampered by:

**Attenuation**, the distance between sender and receiver is too far to be effective. (using the example of talking, if the receiver is too far away to hear the sender shouting at them, their signal is suffering from attenuation).
**Noise**, there is interference with the signal. (using the talking example, if there is a stereo on when the sender and receiver are communicating then the receiver may not hear what is being said and has to ask for the sender to repeat themselves).
**Delay**, the signal takes longer than is required to be transmitted. (the sender and receiver are trying to have a quick-fire conversation but can only use postal letters).

## Messaging

For computers and other electronic devices, when messages are sent they take the form of analog or digital signals.
Analog transmissions are broadcast as a wave and the protocol of the signal knows where each part of the wave corresponds to a particular part of data. so the peak of the wave may be an A, the trough of the wave a B.
Digital transmission is via a series of voltage pushes, where a positive ‘push’ equals 1, and no push is 0. The sequence can then be translated to bits.
In both scenarios, the message can be distorted by the three reasons given above resulting in degradation.

## Transmission

Once we know the medium by which the message will be broadcast the next consideration is how to transmit it. There are two ways to transmit:

**Guided**. The message is sent directly to where it is supposed to go. Taking our non-computer analogy, this would be a letter. Only the receiver receives the sent data. In the case of computers. This is primarily via cables, such as Twisted Pair, Coax or Fibre Optics.

**Unguided**. The message is broadcast so that anyone can receive it, For non-computer analogy, this would be talking in a crowded (but quiet room, maybe a library!) anyone within range can receive the signal. For computers, this is primarily WiFi or Bluetooth.

These transmissions can be sent in three different modes:

**Simplex**, only the sender can transmit.

**Half duplex**, the sender and receiver can transmit but not at the same time.

**Full duplex**, both the sender and receiver can send at the same time.