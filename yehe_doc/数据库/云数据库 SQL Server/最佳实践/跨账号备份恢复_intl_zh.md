云数据库 SQL Server 支持同地域跨账号进行备份恢复，即从账号 A 下的一个实例获取备份文件下载链接，在账号 B 上进行数据恢复，本文为您介绍同地域跨账号备份恢复操作。

## 注意事项
- 从账号 A 下的一个实例获取备份文件下载链接后，在账号 B 上去做备份恢复，账号A 和 B 需要在同一个地域。
- 此备份恢复方式，目前支持的备份文件格式为 bak 文件。
- 在控制台获取的备份文件链接，需注意备份文件形式为单库的备份文件才支持跨同地域跨账号备份恢复。
- 备份恢复功能将支持 .tar 和 .zip 等其他格式的备份文件，功能测试中，预计在1月发布，请以控制台实际支持时间为准。
- 当前需对下载的备份链接做解码，具体请参考 [解码说明](#jmcz)。

## 步骤1：从账号 A 获取备份文件下载链接
1. 使用账号 A 登录 [SQL Server 控制台](https://console.cloud.tencent.com/sqlserver#/)，在实例列表，单击实例 ID，进入实例管理页面。
2. 在实例管理页，单击**备份管理**，在数据备份列表找到目标单库备份文件，单击其**操作**列的**查看详情**。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/3Tm8501_29.png)
3. 在弹窗中单击**下载**，然后复制下载地址。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/fuY9370_30.png)

## 步骤2：解码链接

从账号 A 获取到备份文件下载链接后，需要对此链接进行调整。

>?仅需要对下载链接的前面部分进行调整。
>**示例**：假设某个下载链接为：
>`https://sqlserver-bucket-bj-1258415541.cos.ap-beijing.myqcloud.com/1312368346%2fsqlserver%2fmssql-8e5hjaiq%2fbackup%2fautoed_instance_58013012_AdventureWorksDW2012_2022_12_29023915.bak?**********`
>我们仅需要选取直到 .bak？的部分地址去做调整，调整后再和后半部分组合即可获取到用于跨账号去做备份恢复的链接。
>针对以上示例链接，我们取做解码的部分地址为：
>`https://sqlserver-bucket-bj-1258415541.cos.ap-beijing.myqcloud.com/1312368346%2fsqlserver%2fmssql-8e5hjaiq%2fbackup%2fautoed_instance_58013012_AdventureWorksDW2012_2022_12_29023915.bak?`
>将链接中 **%2f** 换成 **/** 即可：
>`https://sqlserver-bucket-bj-1258415541.cos.ap-beijing.myqcloud.com/1312368346/sqlserver/mssql-8e5hjaiq/backup/autoed_instance_58013012_AdventureWorksDW2012_2022_12_29023915.bak?`
>则最终用于跨账号备份恢复的链接为：
>`https://sqlserver-bucket-bj-1258415541.cos.ap-beijing.myqcloud.com/1312368346/sqlserver/mssql-8e5hjaiq/backup/autoed_instance_58013012_AdventureWorksDW2012_2022_12_29023915.bak?**********`


## 步骤3：在账号 B 进行数据恢复
复制步骤2的最终用于备份恢复的链接。
1. 使用账号 B 登录 [SQL Server 控制台](https://console.cloud.tencent.com/sqlserver#/)，在实例列表，单击实例 ID，进入实例管理页面。
2. 在实例管理页，选择**备份恢复** > **新建**。
3. 在窗口下，完成如下配置，单击**创建任务**。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/ECHh168_33.png)
<table>
<thead><tr><th>参数</th><th>说明</th></tr></thead>
<tbody><tr>
<td>任务名称</td>
<td>输入任务名称，任务名称由字母，数字、下划线组成，最长60个字符。</td></tr>
<tr>
<td>备份上传方式</td>
<td>选择从 COS 下载文件。</td></tr>
<tr>
<td>恢复方式</td>
<td>选择全量备份文件。</td></tr>
</tbody></table>
4. 在备份文件上传窗口，粘贴链接，单击**保存**。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/Rs4w297_34.png)
5. 跳转至备份恢复页面，找到刚才创建的备份任务，在其**操作**列单击**启动**。
6. 在备份恢复列表，查看到迁移任务状态显示迁移成功即完成跨账号备份恢复操作。
