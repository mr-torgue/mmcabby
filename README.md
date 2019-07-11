# mmcabby
MineMeld stix taxii miner using cabby. The current miners for MineMeld are a bit unstable and difficult to understand.
They also don't support STIX/TAXII 1.0. This implementation uses cabby from eclecticIQ.
# Installation
1) Open MineMeld
2) Go to the Admin tab
3) Click Extensions(left sidebar)
4) Click git and enter this repository
5) Restart MineMeld: service minemeld restart
# Parameters
The following parameters can be specified:
[discovery_service] URL where the discovery service is located.
[poll_service] URL where the poll service is located. If empty discovery will be used.
[use_https] Specifies if https is used. Default: True.
[port] Specifies the port on which it is running. Default: 443.
[version] Specifies the STIX/TAXII version. Default: 1.1.