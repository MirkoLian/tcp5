电信移动 策略路由规则

ip段信息取自 http://www.tcp5.com/

由Github Action自动构建于此。

策略路由分流有两种实现方法：

/file remove [find name="unicom.rsc"]
/tool fetch url="https://ghproxy.com/https://github.com/MirkoLian/tcp5/blob/main/unicom.rsc"
:if ([:len [/file find name=unicom.rsc]] > 0) do={
/ip firewall address-list remove [find list="List_ChinaUnicom"]
/import unicom.rsc
}
