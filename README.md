# EventHubProject
<div>框架：Spring Boot 3 + Hibernate。<div><br>
<div>數據庫：MySQL（座位、訂單等結構化數據），Redis（庫存、搶票併發控制）。<div><br>
<div>Web 前端：Thymeleaf（處理模板渲染）。<div><br>
安全性：Spring Security（保護敏感操作）。

<pre>
專案預計核心邏輯
    搶票流程：
        使用 Redis 緩存座位庫存，減少 MySQL 壓力。
        通過分佈式鎖避免超賣。

    訂單確認：
        在搶票成功後，生成未支付訂單，設置支付有效期。
        定時任務掃描未支付訂單並釋放座位。

    數據一致性：
        通過 Redis 和 MySQL 雙向更新，確保座位數據準確。
額外拓展
    防作弊：加入驗證碼與 IP 限流功能，防止搶票軟體濫用。
    分布式：引入 Kafka 或 RabbitMQ 處理搶票事件的排隊機制。</pre>
        
