协议场景针对 GET、POST 协议或端口进行监测，监测接口响应性能、可用性，确保用户使用体验和业务可用性。本文将为您介绍如何新建端口性能任务。

## 操作步骤

1. 登录 [云拨测控制台](https://console.cloud.tencent.com/cat/probe/tasklist)。
2. 在左侧菜单栏中单击**任务列表**。
3. 单击任务列表页面上方的**新建任务**。
4. 根据下列说明配置基本信息。
<table>
<tr>
<th> 配置项</th>
<th> 说明</th>
</tr>
<tr>
<td> 拨测类型</td>
<td> 选择“自定义拨测”</td>
</tr>
<tr>
<td> 任务类型</td>
<td> 选择 PC 端或移动端的“端口性能”任务类型。</td>
</tr>
<tr>
<td> 拨测任务名称</td>
<td> 自定义拨测任务名称。</td>
</tr>
<tr>
<td> 拨测频率</td>
<td> 支持1分钟、5分钟、10分钟、15分钟、30分钟、60分钟、120分钟的拨测频率。例如选择5分钟频率，表示每个拨测点每5分钟拨测一次。</td>
</tr>
<tr>
<td> 执行时间</td>
<td> 默认每日按频率执行，您也可根据需求自定义执行计划。例如您可以设置每周上午8点-9点执行拨测任务</td>
</tr>
<tr>
<td> 任务标签</td>
<td>云拨测结合腾讯云资源标签功能，为您提供按标签授予子账号权限和按标签分账功能。详情可参见 <a href="https://www.tencentcloud.com/document/product/1169/52017">资源标签</a> 进行配置 </td>
</tr>
</table>
5. 根据下列说明配置拨测点。
    i.选择方式：选择推荐拨测点组或自定义拨测点组（推荐的拨测节点为常用的节点）。
    ii.选择拨测点：
	- 可用性拨测点组：仅支持网络质量、端口性能任务类型，适用于网络质量监控、接口可用性监控、劫持和封堵检测。
	- 高级场景拨测点组：页面用户体验监控、直播卡顿监控、弱网环境可用性探测、CDN 选型与路径优化。覆盖境内外的 IDC、PC 终端、移动端探测点。
     - 推荐拨测点组：为您推荐常用拨测点。
     - 自定义拨测点组：**选择拨测点地域** > **选择拨测点类型** > 在右侧框中勾选拨测点。拨测点类型说明如下：
<table>
<tr>
	<th> 拨测点类型</th>
	<th> 说明</th>
</tr>
<tr>
<td> 机房（IDC）</td>
<td> 部署在 PC 电脑上的拨测点，代表 PC 用户体验。</td>
</tr>
<tr>
<td> 网民（LastMile）</td>
<td> 部署在终端用户 PC 电脑上的拨测点，代表终端 PC 用户体验。</td>
</tr>
<tr>
<td> 手机端</td>
<td> 部署在终端移动手机上的拨测点，代表终端移动用户。</td>
</tr>
</table>
 - 我的拨测点组：您可以在“高级场景拨测点”中选择常用的拨测点组，并单击右下角的**新建拨测点组**即可。下次创建任务时，直接选择我的拨测点组，即可快速选择您创建的常用拨测点。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/EDsN042_24intl_%E5%A5%BD%E5%8E%8B%E7%9C%8B%E5%9B%BE.png)
<dx-alert infotype="explain" title="选择建议">
由于机房（IDC）和网民（LastMile）网络环境不同，机房（IDC）比网民（LastMile）更稳定。
- 若是要监测业务的可用性，可以选择比较稳定的机房 IDC。
- 若要看终端用户的访问体验、网络情况等建议多选网民 LastMile 或移动端，可以模拟终端用户访问应用的体验。
</dx-alert>
6. 配置拨测参数（可选），系统默认为您配置常用的拨测参数，您也可以自定义拨测规则。配置说明如下：
**HTTP（s）：**
<table>
<tr>
<th> 配置项</th>
<th> 说明</th>
<th> 默认取值</th>
</tr>
<tr>
<td> 协议类型</td>
<td> 支持 HTTP(s)、 SSL、 TCP 和 UDP 协议类型。</td>
<td> 自动</td>
</tr>
<tr>
<td> 拨测地址</td>
<td>填写需要拨测的 Web 应用地址（以 <code>http:// </code>开头）<br>例如：<br>1. 域名：<code>http://www.tencent.com</code><br/>2.
域名端口：<code>http://www.tencent.com:80</code><br/>备注： HTTP(s) 协议类型需要选择请求类型</td>
<td> 纯文本</td>
</tr>
<tr>
<td> 字符编码</td>
<td> 发送内容的编码类型，支持 UTF-8、GBK、GB2312、Unicode。</td>
<td> UTF-8</td>
</tr>
<tr>
<td> 自定义 Host</td>
<td> 支持按 IP 地址轮询或随机监测，多个 IP 请用半角逗号分隔符，<br>例如：<ul style = "margin-bottom: 0px;"><li>IPv4：<code>192.168.2.1,192.168.2.5:img.a.com|192.168.2.1?]:img.a.com|</code></li><li>IPv6：<code>[0:0:0:0:0:0:0:1][8080],[0:0:0:0:0:0:0:2][8081]:www.a.com|]</code></li></ul></td>
<td> -</td>
</tr>
<tr>
<td> IP 类型</td>
<td>访问服务器的类型。自动表示随机测试 IPv4 或者 IPv6 服务器的性能；IPv4 表示指定测试 IPv4 服务器的性能；IPv6 表示指定测试 IPv6 服务器的性能。 </td>
<td>-</td>
</tr>
<tr>
<td> 请求配置</td>
<td>自定义要添加到 HTTP请求中的 Header 、 Authentication（鉴权）、Query Parameters（查询参数）、Cookies。 </td>
<td>-</td>
</tr>
<tr>
<td> 验证方式</td>
<td> 自定义接口数据请求验证方式。可进行 statusCode、body、header 验证方式配置。</td>
<td>-</td>
</tr>
</table>		
<b>SSL、TCP 和 UDP其它配置项：</b>
<table>
<tr>
<th> 配置项</th>
<th> 说明</th>
<th> 默认取值</th>
</tr>
<tr>
<td> 请求类型</td>
<td>可选择用纯文本、二进制流的方式来填写请求内容。请求内容即为协议的请求头信息。</td>
<td>-</td>
</tr>
<tr>
<td> 请求内容</td>
<td>自定义发起端口性能拨测时的请求内容</td>
<td>-</td>
</tr>
<tr>
<td> 验证方式</td>
<td><ul style = "margin-bottom: 0px;">
自定义接口数据请求验证方式。
<li>不验证：不验证数据的完整性。</li>
<li>完全匹配：响应数据必须和填写的数据完全一致。</li>
<li>部分包含：响应数据需要含部分或全部所填写的数据，接收数据大小必须大于所填写数据的字节数。</li>
<li>MD5：把响应数据保存为文件进行 MD5 计算，得到的值和期望值进行比较，要完全一致。</li></ul>
</td>
<td> 不验证</td>
</tr>
</table>						
