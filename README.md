Repack original f5vpn deb package with files provided in this repo to make it work in dokerized environement since original package has strong dependency on QT version and does not seem anyone is going to fix that.

```
mkdir tmp/
dpkg-deb -R linux_f5vpn.x86_64.deb tmp/
cp -r src/* tmp/
dpkg-dev -b tmp/ f5vpn.deb
dpkg -i f5vpn.deb
```


Rebuilt package will use docker image [strngr/f5vpn-env](https://hub.docker.com/r/strngr/f5vpn-env) with pre-built F5VPN compatible QT environment. You can find sources here: strngr/f5vpn-env.
