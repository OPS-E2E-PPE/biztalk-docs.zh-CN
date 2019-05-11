---
title: MySAP 适配器在 BizTalk 中的 SELECT 语句示例 |Microsoft Docs
description: 选择示例和示例使用 mySAP 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54a5a4ac-a994-4706-9735-a5a1a82b893b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982ed09e93a43169a3b0b376fba862176a01745c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373463"
---
# <a name="examples-for-select-statement"></a>SELECT 语句示例
本主题演示各种 SELECT 语句的示例语法。

## <a name="sample-statements"></a>示例语句 
  
-   若要列出有关名为 SPFLI 表中列出的航班的详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   若要将提取的数据存储到一个名为在 flight.txt 文件\\\SAPServer\Extracts，使用以下语法：  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   向列出的所有航班为从纽约飞往旧金山的详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   列出的所有详细信息到航班来自纽约的`connid`字段的值为 1000年和 5000 之间，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   向列出的所有航班为从纽约的用户指定城市的详细信息，请使用以下语法：  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     在本例中，创建一个名为 SAP 参数`@variable`、 指定的值，并将其添加到相应的命令对象。  
  
-   在 LIKE 子句的 SELECT 查询中，百分号、 （适用于零个或多个字符的任意字符串），"%"和下划线"_"（适用于任何单个字符），是允许的特殊字符。 所有其他被视为字符串值，将被忽略。  
  
    -   示例演示了如何使用百分比"%"  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         在这里，%模式 %提取所有记录 Name1 其中包含字符串"模式"。  
  
    -   示例演示了如何使用下划线"_"  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         在这里，"D_"提取其中 Name1 以"D"开头并包含两个字符的所有记录。  
  
-   示例，以演示"between"谓词子句  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   示例，以演示"不介于"谓词子句  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   使用联接和 TOP 子句的 SELECT 语句的示例  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   使用 OPTION 子句的 SELECT 语句的示例  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
