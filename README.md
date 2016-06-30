# PKGBUILD for odroidc2-mptcp 

https://github.com/amyznikov/odroidc2-mptcp

This odroidc2-mptcp kernel is derived as merge of MultiPath TCP https://github.com/multipath-tcp/mptcp.git into odroidc2 kernel https://github.com/hardkernel/linux/tree/odroidc2-3.14.y

The remotes used:

 1  remotes/hardkernel/odroidc2-3.14.y https://github.com/hardkernel/linux.git
 
 
 2  remotes/mptcp/mptcp_v0.89 https://github.com/multipath-tcp/mptcp.git
 


The mptcp_v0.89 was selected as closest merge base for odroidc2-3.14.y: mptcp_v0.89 is based on v3.14.33 revision, 
odroidc2-3.14.y is based on odroidc2-3.14.65 revision.

The merge was done after checkout of odroidc2-3.14.y and merging with mptcp_v0.89 branch:

```
$ git merge --no-commit --no-ff  mptcp_v0.89 
```


Several conflicts caused by mptcp-specific code and by discrepancy of kernel revisions 3.14.33 and 3.14.65 were solved manually 
using kdiff3 tool.

Several additional manual changes was made mainly to silence intensive default console debug logging.


Resulting kernel was packaged using this PKGBUILD script 
and tested on OdroidC2 board using two 3G-modems and mobile phones in GPRS/3G networks.

To use the OdroidC2 board as application server, the OpenVPN connection from the board to second MPTCP-capable host was configured to run on the top of MPTCP.







