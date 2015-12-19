# dnsdist-sample
<br>
#
<br>
#DNSAction<br>
DNSAction.Drop<br>
DNSAction.Nxdomain<br>
DNSAction.Spoof<br>
DNSAction.Allow<br>
DNSAction.HeaderModify<br>
DNSAction.Pool<br>
DNSAction.None<br>
<br>
#DNSHeader<br>
dnsheader:setRD(bool)<br>
bool dnsheader:getRD()<br>
dnsheader:setCD(bool)<br>
bool dnsheader:getRD()<br>
dnsheader:setTC(bool)<br>
dnsheader:setQR(bool)<br>
<br>
<br>
#TuningParam<br>
setTCPRecvTimeout<br>
setTCPSendTimeout<br>
setMaxUDPOutstanding<br>
setMaxTCPClientThreads<br>
setECSSourcePrefixV4<br>
setECSSourcePrefixV6<br>
setECSOverride<br>
<br>
#Logging
infolog(string)<br>
warnlog(string)<br>
errlog(string)<br>
<< sample >><br>
function logging(logtype, remote, qname, qtype, dh, len)<br>
        warnlog(string.format("TYPE:%s IP:%s QNAME:%s QTYPE:%s RD:%s CD:%s", logtype, remote:tostring(), qname:tostring(), qtype, tostring(dh:getRD()), tostring(dh:getCD())))<br>
end<br>
<br>
