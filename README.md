# mmcabby
MineMeld stix taxii miner using cabby. The current miners for MineMeld are a bit unstable and difficult to understand.
They also don't support STIX/TAXII 1.0. This implementation uses cabby from eclecticIQ which makes the code for mmcabby cleaner and less prone to errors.
Cabby relies on pytz>=2017.2 and libtaxii>=1.1.111, which don't match the versions for the minemeld-core. See dependency fixes for how to solve this.
# Installation
1) Open MineMeld
2) Go to the Admin tab
3) Click Extensions(left sidebar)
4) Click git and enter this repository
5) Select latest version
6) Restart MineMeld: service minemeld restart
# Parameters
The following parameters can be specified:
* discovery_service: URL where the discovery service is located.
* poll_service: URL where the poll service is located. If empty discovery will be used.
* use_https: Specifies if https is used. Default: True.
* port: Specifies the port on which it is running. Default: 443.
* version: Specifies the STIX/TAXII version. Default: 1.1.
* cert_file: path to certificate
* key_file: path to key file
# Dependency fixes
The libtaxii and pytz libraries needed for cabby don't match the versions for minemeld-core. This can be fixed by changing the requirements.txt in /opt/minemeld/engine/core.
After that run the setup.py file in the same directory:
1) cd /opt/minemeld/engine/core/
2) nano requirements.txt -- change requirements to libtaxii>=1.1.111 and pytz>=2017.2
3) /opt/minemeld/engine/current/bin/python setup.py install
4) service minemeld restart
You can also do a manual installation of the pytz and libtaxii packages:
1) /opt/minemeld/engine/current/bin/pip uninstall pytz libtaxii -- uninstall old packages
2) /opt/minemeld/engine/current/bin/pip install pytz libtaxii -- install new packages
3) service minemeld restart
