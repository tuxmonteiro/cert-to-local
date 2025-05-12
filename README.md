# cert-to-local

This is a simple DNS server in Python3 to provide TLS to webservices on local addresses. In short, it resolves addresses such as `192-168-0-1.yourdomain.net` to `192.168.0.1` and has a valid TLS certificate for them.

This was written to circumvent the problem that current browsers require a secure context for a number of operations, such as opening the camera with `getUserMedia`, but the web service is running on a local network, where it is difficult to get a certificate or handling the local DNS servers is difficult or impossible (aham users aham). It can also be used to easily develop and debug web applications that require secure contexts other than in localhost.

Technically, it's a very simple DNS server written in Python, which uses [Let's Encrypt](https://letsencrypt.org/) to generate a wildcard certificate for *.yourdomain.net on a real public server. This certificate, both private and public keys, is available for download via both a  `REST` call as well as two `GET` calls on a simple HTTP server, also provided.

	

# About and credits

* Developed by [Corollarium](https://corollarium.com) and released under the MIT license.
* Inspiration from [nip.io](https://nip.io), [SSLIP](https://sslip.io) and [XIP](http://xip.io/)
* [Blog post explaining how to generate certificates per server](https://blog.heckel.io/2018/08/05/issuing-lets-encrypt-certificates-for-65000-internal-servers/)
