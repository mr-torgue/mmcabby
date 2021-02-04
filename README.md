# mmcabby
MineMeld stix taxii miner using cabby. The current miners for MineMeld are a bit unstable and difficult to understand.
They also don't support STIX/TAXII 1.0. This implementation uses cabby from eclecticIQ which makes the code for mmcabby cleaner and less prone to errors.

mmcabby should work for all types of minemeld installations. This includes docker.
# Installation
1) Open MineMeld
2) Go to the Admin tab
3) Click Extensions(left sidebar)
4) Click git and enter this repository
5) Select latest release version (v1.0.1). NOTE: sometimes the version is not displayed. Just type the mmcabby version(v1.0.1) and press enter.
6) Restart MineMeld: service minemeld restart OR for docker: docker restart minemeld
# Usage/tutorial
mmcabby comes with 1 new prototype which can be used to create more prototypes. Go to minemeld->config. Click "browse prototypes", the symbol in the lower left corner. Search for the prototype myphishtank and click it. It shows this:

Click on new to create a new prototype. For example if you want to get the abuse.ch collection from hail a taxii:
* click create
* change guest.phishtank_com to guest.Abuse_ch
* [optional] add tags, change the name, or add authentication. For other streams these might be necessary. Parameters are explained below.
* click ok

Click on clone to add a new node with this prototype. Change name and click ok. Click on commit to activate the node.
Verify by going to the nodes tab and check if indicators are coming in.
# Parameters
The following parameters can be specified:
* discovery_service: URL where the discovery service is located.
* poll_service: URL where the poll service is located. If empty discovery will be used.
* use_https: Specifies if https is used. Default: True.
* port: Specifies the port on which it is running. Default: 443.
* version: Specifies the STIX/TAXII version. Default: 1.1.
* cert_file: path to certificate
* key_file: path to key file
