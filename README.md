# TCP Testsuite for FreeBSD based on Packetdrill

This TCP testsuite focuses on testing FreeBSD's TCP stack.

## Requirements
It it based on the packetdrill testtool.
The original version is available from [Google's repository](https://github.com/google/packetdrill).
However, this version does not really run on FreeBSD.
An extended version is available from [NPLab's respository](https://github.com/nplab/packetdrill)
and overcomes this limitation and adds support for SCTP and UDPLite.

## Installation
You can get the testsuite by running
```
git clone https://github.com/tuexen/tcp-testsuite.git
```
## Usage
To run all test scripts, execute
```
sudo tcp-testsuite/run-all-tests
```
which runs the `tcsh` script `tcp-testsuite/run-all-tests` with root priviledges.

## Structure of the Testsuite
| Test Group                                                                     | Number of Test Scripts | Status
|:-------------------------------------------------------------------------------|:----------------------:|:-----------:|
| [Sending of SYN-Segments](snd-syn/README.md)                                   | 30                     | Done        |
| [Handling of SYN-Segments](rcv-syn/README.md)                                  | 0                      | In Progress |
| [Handling of RST-Segments](rcv-rst/README.md)                                  | 142                    | Done        |
| [Handling of RST-ACK-Segments](rcv-rst-ack/README.md)                          | 0                      | In Progress |
| [Handling of ICMP Messages](rcv-icmp/README.md)                                | 12                     | In Progress |
| [Socket API](socket-api/README.md)                                             | 10                     | In Progress |

## FreeBSD Fixes
* [r305810](https://svnweb.freebsd.org/changeset/base/305810) ([D7833](https://reviews.freebsd.org/D7833)).
* Under review: [D7904](https://reviews.freebsd.org/D7904).

## Acknowledgement
This work is sponsored by Netflix, Inc.

## References
* [RFC 0793: *Transmission Control Protocol*](https://tools.ietf.org/html/rfc0793)
* [RFC 1122: *Requirements for Internet Hosts -- Communication Layers*](https://tools.ietf.org/html/rfc1122)
* [RFC 1323: *TCP Extensions for High Performance*](https://tools.ietf.org/html/rfc1323)
* [RFC 1337: *TIME-WAIT Assassination Hazards in TCP*](https://tools.ietf.org/html/rfc1337)
* [RFC 2018: *TCP Selective Acknowledgment Options*](https://tools.ietf.org/html/rfc2018)
* [RFC 2883: *An Extension to the Selective Acknowledgement (SACK) Option for TCP*](https://tools.ietf.org/html/rfc2883)
* [RFC 4953: *Defending TCP Against Spoofing Attacks*](https://tools.ietf.org/html/rfc4953)
* [RFC 5461: *TCP's Reaction to Soft Errors*](https://tools.ietf.org/html/rfc5461)
* [RFC 5927: *ICMP Attacks against TCP*](https://tools.ietf.org/html/rfc5927)
* [RFC 5961: *Improving TCP's Robustness to Blind In-Window Attacks*](https://tools.ietf.org/html/rfc5961)
* [RFC 6429: *TCP Sender Clarification for Persist Condition*](https://tools.ietf.org/html/rfc6429)
* [RFC 6691: *TCP Options and Maximum Segment Size (MSS)*](https://tools.ietf.org/html/rfc6691)
