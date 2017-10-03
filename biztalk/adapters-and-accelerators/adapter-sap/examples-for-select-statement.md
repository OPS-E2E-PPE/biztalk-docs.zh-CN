---
title: "在 BizTalk mySAP 适配器中的 SELECT 语句示例 |Microsoft 文档"
description: "选择示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54a5a4ac-a994-4706-9735-a5a1a82b893b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140e895bf8ec2fb65a848c8752dc8e141530bd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="examples-for-select-statement"></a>SELECT 语句的示例
本主题演示各种 SELECT 语句的示例语法。

## <a name="sample-statements"></a>示例语句 
  
-   若要列出有关名为 SPFLI 的表中列出的航班的详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   若要将提取的数据存储到一个名为在 flight.txt 文件\\\SAPServer\Extracts，使用以下语法：  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   从纽约到旧金山的所有航班列表详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   到列出的所有详细信息航班从纽约其`connid`字段的值为 1000年到 5000 之间，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   从纽约到用户指定城市的所有航班列表详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     在此情况下，创建名为的 SAP 参数`@variable`、 指定的值，并将其添加到相应的命令对象。  
  
-   LIKE 子句的 SELECT 查询中中的百分号、"%"（对于零个或多个字符的任意字符串） 和下划线"_"（适用于任何单个字符），是允许的特殊字符。 所有其他被视为字符串值，并且将被忽略。  
  
    -   示例，演示了利用百分比"%"  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         在这里，%模式 %提取所有记录其中 Name1 包含字符串"模式"。  
  
    -   示例，演示了利用下划线"_"  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         在这里，"D_"提取所有记录其中 Name1 以"D"开头并包含两个字符。  
  
-   示例，演示"之间"谓词子句  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   示例，演示了"不介于"谓词子句  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   更大的示例使用联接和 TOP 子句的 SELECT 语句  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   更大的示例使用 OPTION 子句的 SELECT 语句  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
