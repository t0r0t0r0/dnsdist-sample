# dnsdist-sample
<br>
#
#Practical<br>
Shutodown() : サービス停止<br>
webserver(ipaddress:port, password) : ステータス表示WebServerとその接続パスワードの設定。portは省略可<br>
-- 記述例 --<br>
webserver("192.168.0.1:8083","dnsdist")<br>
<br>
#DNSAction<br>
DNSAction.Allow()<br>
DNSAction.Delay()<br>
DNSAction.Drop()<br>
DNSAction.Nxdomain()<br>
DNSAction.Pool , string poolname<br>
DNSAction.Spoof()<br>
DNSAction.HeaderModify()<br>
DNSAction.None<br>
-- 記述例 --<br>
```
function exampleAllow(remote, qname, qtype, dh, len)
    return DNSAction.Allow()
end

function exampleDelay(remote, qname, qtype, dh, len)
        return DNSAction.Delay()
end

function exampleDrop(remote, qname, qtype, dh, len)
        return DNSAction.Drop()
end

function exampleNxDomain(remote, qname, qtype, dh, len)
        return DNSAction.Nxdomain()
end

function examplePool(remote, qname, qtype, dh, len)
        return DNSAction.Pool, "dnspool1"
end

function exampleSpoof(remote, qname, qtype, dh, len)
        return DNSAction.Spoof()
end

function exampleNone(remote, qname, qtype, dh, len)
        return DNSAction.None()
end
```
<br>
<br>
#DNSHeader<br>
void dnsheader:setRD(bool)<br>
bool dnsheader:getRD()<br>
void dnsheader:setCD(bool)<br>
bool dnsheader:getRD()<br>
void dnsheader:setTC(bool)<br>
void dnsheader:setQR(bool)<br>
<br>
<br>
#TuningParam<br>
setTCPRecvTimeout(2)<br>
setTCPSendTimeout(2)<br>
setMaxUDPOutstanding()<br>
setMaxTCPClientThreads()<br>
setECSSourcePrefixV4()<br>
setECSSourcePrefixV6()<br>
setECSOverride()<br>
<br>
#Logging
void infolog(string)<br>
void warnlog(string)<br>
void errlog(string)<br>
<< sample >><br>
function logging(logtype, remote, qname, qtype, dh, len)<br>
        warnlog(string.format("TYPE:%s IP:%s QNAME:%s QTYPE:%s RD:%s CD:%s", logtype, remote:tostring(), qname:tostring(), qtype, tostring(dh:getRD()), tostring(dh:getCD())))<br>
end<br>
<br>
