# tcp5
电信移动联通策略路由规则

ip段信息取自 tcp5.com

由Github Action自动构建于此。

策略路由分流实现方法：
```
/file remove [find name="unicom.rsc"]
/tool fetch url="https://github.com/MirkoLian/tcp5/blob/main/unicom.rsc"
:if ([:len [/file find name=unicom.rsc]] > 0) do={
/ip firewall address-list remove [find list="List_ChinaUnicom"]
/import unicom.rsc
}
```
