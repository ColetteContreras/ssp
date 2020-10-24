# shadowsocks-poseidon
Shadowsocks 单端口多用户，适配多种面板

### 安装

```
(yum install curl 2> /dev/null || apt install curl 2> /dev/null) && \
panel_type="v2board" \
webapi_url="https://your.webapi.host" \
webapi_key="YOUR_NODE_KEY" \
node_id=1 \
poseidon_license="" \
speed_limit=0 \
rule_url="https://raw.githubusercontent.com/ColetteContreras/ssp/main/example-rules.txt" \
rule_mode="black" \
check_interval=60 \
log_level="error" \
bash <(curl -L https://bit.ly/3jyAijB)
```

### 配置文件 `/etc/ssp/config.ini`



### 参数说明

| 参数 | 说明 |
|------|-----|
| panel_type | 面板类型，当前支持的值为 `proxypanel` `v2board` |
| webapi_url | webapi 的地址 `https://你的面板域名` |
| webapi_key | ProxyPanel 为`节点通信密钥` |
| node_id | 面板生成的节点 ID |
| poseidon_license | 从作者处获得的授权码<br />（没有的话空着就行，空着表示使用社区版本|
| speed_limit | 限速，单位 Mbps，0表示不限速 |
| rule_url | 审计规则地址，推荐使用 https:// 这种远程文件，方便后续的更新 |
| rule_mode | 审计模式，支持白名单`white` 黑名单`black` |
| check_interval | 多久与面板交换一次信息（同步用户，上报流量等），默认 60 |
| log_level | 日志级别，日志内容大小排序 `error` <= `warning` <= `info` |


### 操作命令

| Function | command | 
|------------|--------|
| Show logs  | `journalctl -n 100 -f --no-pager -u ssp` |
| Show status  | `systemctl status ssp` |
| Stop  | `systemctl stop ssp` |
| Start  | `systemctl start ssp` |
| Restart  | `systemctl restart ssp` |
| Upgrade | `bash <(curl -L https://bit.ly/3jyAijB)` |
| Uninstall | `bash <(curl -L https://bit.ly/33wXh9j)` |

### 功能列表

| 功能 | 社区版 | 商业授权版 |
|------|------|-----------|
| 根据面板配置自动设置服务端 | √ | √ |
| 用户同步 | √ | √ |
| 用户 IP 上报 | √ | √ |
| 上报结点信息 | √ | √ |
| 随时更新到最新版本 | √ | √ |
| 单端口多用户 | √ | √ |
| 多端口多用户 | x | x |
| 支持用户数 | 88 | 与授权人数一致 |
| ProxyPanel | √ | √ |
| V2board v1.4.0+ | √ | √ |
| SSPanel |√ | √ |
| 用户限速 | √ | √  |
| 审计 | √ | √ |

### 商业授权

<table>
<tr>
<th colspan="7">商业授权价格表</th>
</tr>
<tr>
<td>人数限制</td><td colspan="2">最多 2000 人</td><td colspan="2">最多 6000 人</td><td colspan="2">无限制</td>
</tr>
<tr>
<td>价格</td><td>USDT</td><td>人民币</td><td>USDT</td><td>人民币</td><td>USDT</td><td>人民币</td>
</tr>
<tr>
<td>一年</td><td>65</td><td>455</td><td>130</td><td>910</td><td>200</td><td>1400</td>
</tr>
<tr>
<td>两年</td><td>115</td><td>805</td><td>230</td><td>1610</td><td>330</td><td>2310</td>
</tr>
<tr>
<td>三年</td><td>159</td><td>1113</td><td>310</td><td>2170</td><td>450</td><td>3150</td>
</tr>
<tr>
<td>永久</td><td>220</td><td>1540</td><td>440</td><td>3080</td><td>660</td><td>4620</td>
</tr>
</table>

授权版咨询、购买请联系[作者](https://t.me/ColetteContreras)（可找作者 PY 个一周的试用授权）
