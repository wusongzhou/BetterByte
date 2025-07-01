---
date: '2025-07-01T13:23:21+08:00'
draft: true
title: '项目常用SQL'
tags: [ "SQL" ]
author: "Me"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
disableHLJS: false      # 必须设为 false 以启用代码高亮（Highlight.js）
disableShare: true      # 设为 true 彻底隐藏社交分享按钮
UseHugoToc: true
cover:
  image: "<image path/url>" # image path/url
  alt: "<alt text>" # alt text
  caption: "<text>" # display caption under cover
  relative: false # when using page bundles set this to true
  hidden: true # only hide on current single page
editPost:
  URL: "https://github.com/<path_to_repo>/content"
  Text: "Suggest Changes" # edit text
  appendFilePath: true # to append file path to Edit link
---

---
<!-- 从这里开始写你的正文内容 -->

# 项目常用SQL

## 每日销售

```每日销售
select t1.SaleDate,
       SUM(t2.OrderMoney)                                                   AS OrderTotalAmount,
       SUM(t2.OrderMoney - t2.ReturnAmount) AS ActualAmount
from SL_Order t1
         inner join SL_OrderDetail t2 on t1.Id = t2.OrderId
where (1 = 1)
  and (t1.RecordStatus = 1 and t2.RecordStatus = 1 and t1.OrderStatus > 0)
  and (t1.SaleDate >= '2024-11-01' and t1.SaleDate <= '2024-12-01')
GROUP BY t1.SaleDate
ORDER BY t1.SaleDate
```

```每日销售额（午场和晚场)
SELECT
    t1.SaleDate,
    SUM(t2.OrderMoney) AS '销售金额',
    SUM(t2.OrderMoney - t2.ReturnAmount) AS '有效金额',
    CASE
        WHEN t1.OrderType = 4 THEN '晚场'
        ELSE '午场'
        END AS OrderType
FROM
    SL_Order t1
        INNER JOIN
    SL_OrderDetail t2 ON t1.Id = t2.OrderId
WHERE
    t1.RecordStatus = 1
  AND t2.RecordStatus = 1
  AND t1.OrderStatus > 0
  AND t1.SaleDate >= '2024-11-01'
  AND t1.SaleDate <= '2024-12-01'
GROUP BY
    t1.SaleDate,
    CASE
        WHEN t1.OrderType = 4 THEN '晚场'
        ELSE '午场'
        END
ORDER BY
    t1.SaleDate;
```

---