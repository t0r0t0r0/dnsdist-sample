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
infolog<br>
warnlog<br>
errlog<br>
<< sample >><br>
-- function logging(logtype,remote, qname, qtype, dh, len)<br>
--        warnlog(string.format("TYPE:%s IP:%s QNAME:%s QTYPE:%s RD:%s CD:%s", logtype, remote:tostring(), qname:tostring(), qtype, tostring(dh:getRD()), tostring(dh:getCD())))<br>
-- end<br>
<br>
