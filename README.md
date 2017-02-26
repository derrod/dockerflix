Dockerflix w/ OpenVPN client
========

Info on Dockerflix + its configuration: https://github.com/trick77/dockerflix

Info on the OpenVPN part and how to add services: https://github.com/schmas/docker-openvpn-client

Main difference to Dockerflix is that this uses OpenVPN to tunnel all proxied requests. This means you don't need a VPS or worry about IP whitelisting etc. It comes preconfigured for a bunch of VPN providers (see openvpn/conf) and should be super simple to set up as long as you already have an existing subscription to any of those providers.

Currently it doesn't have the UK configuration from the original dockerflix but I might add it in the future.

## Getting started:
* `git clone https://github.com/derrod/dockerflix-openvpn.git`
* Edit VPN settings in `docker-compose.yml`
	* if your VPN service does not exist see [this](https://github.com/schmas/docker-openvpn-client#adding-new-providers) for instructions on how to add it
* `docker-compose up`
* Do `python ./gendns-conf.py --remoteip <PUBLIC_IP_OF_YOUR_VPS_SERVER> [-t bind]` to generate config for your DNS server
* Reload dns server and you're good to go!
