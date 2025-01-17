## 操作场景
预算管理功能从客户内部经营管理诉求出发，帮助腾讯云客户设置预算，追踪预算，分析预算。
>? 预算管理目前正在灰度体验中，如需体验，可以联系您的客户经理。

## 操作步骤
1. 登录[费用中心控制台](https://console.intl.cloud.tencent.com/expense)。
2. 在左侧导航栏中，选择**成本管理> 预算管理**，进入预算管理页面。
3. 单击**新建预算**。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/dwQ8962_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_3%E6%96%B0%E5%BB%BA%E9%A2%84%E7%AE%97.png)
4. 在**编辑预算**页面，按需填写相关信息。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/TuF7925_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_4%E7%BC%96%E8%BE%91%E9%A2%84%E7%AE%97.png)
 - **基本信息**：根据需要设置便于区分的预算名称，该名称将会展示在预算列表。
 - **编制信息**：
    - 预算周期：支持按照年度、季度、月度、日设置预算周期。
    - 预算有效期：支持有效期生效和持续性生效。区别是持续性生效没有截止时间，可持续生效。
>! 
>- 持续性生效有无限个周期，编制方式**仅支持固定预算**，不支持计划预算。
>- 计划预算最多设置后12个周期的预算值，取决于您选择的有效期范围。若周期数目更多，则后续预算会沿用第12个周期值。不建议配置过多计划预算。
    - 有效期：设置的预算金额仅在该时间段内生效，如果选择了持续性生效则为某日起永久生效。
    - 编制方式：支持固定预算和计划预算。
    - 每月预算金额：您计划在预算周期内的成本金额。
    - 编制方式为**固定预算**：可设置每月预算为固定金额。
    - 编制方式为**计划预算**：可设置每个周期预算为不同金额。
 - **费用范围**：
     - 默认为全部费用，推荐您为全部费用统一配置预算。
     - 支持自定义费用范围，目前支持的自定义维度有：产品、子产品、地域、可用区、计费模式、交易类型（消耗类型）、项目、标签。每个维度下会基于您历史消费记录拉出清单，支持多选。
 - **高级设置**：
    - 账单口径
      - 费用账单：基于收付制设置预算，腾讯云默使用费用账单口径，基于总费用（即折扣价）配置预算。
      - 消耗账单：基于权责发生制设置预算，消耗账单口径一般用于客户希望管理摊销成本的场景。如需使用消耗账单口径，您需要先开通 [消耗账单](https://www.tencentcloud.com/zh/document/product/555/44227)。
    - 费用类型：支持总费用（折扣价）、原价费用（排除优惠影响）、现金支付、优惠券支付、赠送金支付、分成金支付。
 - **可视化图形介绍**：在配置预算过程中，腾讯云提供相应历史成本的可视化图表，展示在**预览**页签中，可协助您参考历史费用设置预算。
    - 辅助图表与成本分析功能打通，会随您配置参数下自动调整成本范围，展示相应成本。您也可以点击跳转到成本分析页面进行更详细的历史分析。
    - 您配置的预算值，及后续步骤配置的告警阈值，也将体现在其中。
>? 对于日预算，腾讯云展示历史20天的成本；月预算展示历史12个月；季度预算展示历史4个季度；年预算展示历史每年。
5. 以上信息填写完后，单击**下一步：设置提醒**，在**设置提醒**页面，按需填写相关信息。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/2dEz776_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_5%E8%AE%BE%E7%BD%AE%E6%8F%90%E9%86%92.png)
 - **预算提醒**：基于每个预算，最多可设置3组预警。
    - 实际费用：按您的实际消费金额进行预警。
    - 固定值：您可以根据需要设置一个固定的金额，达到或超过该金额时触发预警。
    - 预算金额的百分比：基于您设置好的预算金额，设置百分比阀值；达到或超过该金额时触发预警。
 - **波动提醒**：波动告警用于检查预算生效期间，日或月的异常上升情况，支持同比、环比、固定值比较。最多可设置3组提醒。
    - 日预算中支持检查如下周期波动检查：日环比（与上一天比较）；日同比（与上个月同一日比较）；日固定值。
    - 月及月以上预算支持检查如下周期波动检查：日环比（与上一天比较）；日同比（与上个月同一日比较）；月环比（与上一月比较）。
    - 各波动类型计算公式如下：
| 波动类型 | 计算公式 | 备注 |
|---------|---------|---------|
| 日环比 | （今日金额 - 昨天金额） /上期数*100% | 为避免按量月结费用在1号显著影响分析，日同比环比不覆盖按月结算费用 | 
| 日同比 | （今日金额 -上月今日金额）/上月日×100% |在日同比中，若本日金额找不到上月同一日，例如5月31日找不到4月31日数据，则根据就近原则获取，与4月30日数据比较 |
| 月环比 | （本月金额 - 上月金额） /上月金额*100% |
|日固定值 | 今日金额>固定值 |
>! 对于每条预算，您可配置最多3条阈值类告警，3条波动类告警。
   **提醒接收设置**：您可前往 [消息订阅](https://console.intl.cloud.tencent.com/message/subscription) 选择【费用中心=》编辑=》预算管理通知】设置提醒方式和消息接收人。
  - 若您在触发某条阈值提醒后，编辑调整阈值金额，则会在下次检查时重新检查发送。
  - 若在某次检查中同时触发多次提醒，将聚合为一条消息发送。
  - 同一条提醒在同一重置周期内，只会触发一次。
6. 单击**下一步：确认预算**。
该页面展示您已设置的预算信息，预警阀值、提醒信息等相关配置属性，确认无误后单击**保存**。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/Degm890_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_6%E7%A1%AE%E8%AE%A4%E9%A2%84%E7%AE%97.png)

## 可视化面板介绍
点击预算列表中的预算名称，可进入预算分析面板，进一步分析预算历史达成情况。也可以在此编辑/删除、复制预算。
![](https://staticintl.cloudcachetci.com/yehe/backend-news/ABFs816_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_%E5%8F%AF%E8%A7%86%E5%8C%96%E9%9D%A2%E6%9D%BF1.png)
![](https://staticintl.cloudcachetci.com/yehe/backend-news/QEjX852_%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_%E5%8F%AF%E8%A7%86%E5%8C%96%E9%9D%A2%E6%9D%BF2.png)
- **本期预算面板**：您可以查看本期预算的相关信息：包括预算进度、预算与实际费用对比、本期已触发的提醒次数。
- **预算历史面板**：在预算历史面板中，您可查看该预算在创建以来的历史执行情况。预算历史图表与成本分析打通，以可视化图表的方式展示每个周期的实际成本和预算计划，并支持跳转到成本分析进行进一步分析。
- **提醒记录面板：**在提醒记录面板可以查看历史上触发的所有预警，包括提醒时间和提醒内容。
- **预算信息面板**：在右侧面板可以查看该预算在配置时的所有相关属性，并支持编辑/删除、复制。
>? 为保证预算的连贯性与完整性，如有预算变更诉求，建议您创建新预算，避免编辑预算。
