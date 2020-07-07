# PoCs of URGENT/11

URGENT/11 is a set of vulnerabilities found on the VxWorks TCP/IP stack. It is found by [Armis](https://www.armis.com/) and its white paper can be found [here](https://info.armis.com/rs/645-PDC-047/images/Urgent11%20Technical%20White%20Paper.pdf).

Six of the discovered vulnerabilities are of critical severity, since they are memory corruptions that can lead to remote code execution. The six vulnerabilities were found in three separate subsystems of VxWorks' TCP/IP stack (IPnet):

1. One RCE vulnerability in the IP layer (CVE-2019-12256)
2. Four RCE vulnerabilities in the TCP layer ([CVE-2019-12255](./CVE-2019-12255), [CVE-2019-12260](./CVE-2019-12260/), CVE-2019-12261 & CVE-2019-12263)
3. One RCE vulnerability in the IPnet’s built-in DHCP client, ipdhcpc (CVE-2019-12257)

CVE-2019-12256 depends on sending packets with invalid IP options, so it **can not** be exploited over the Internet. The first router that encounters the packet will drop it.

CVE-2019-12257 exists in VxWorks' DHCP client when parsing incoming DHCP Offer and ACK packets, so it **can not** be exploited over the Internet either.
