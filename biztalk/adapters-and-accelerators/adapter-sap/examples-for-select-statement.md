---
title: 在 BizTalk mySAP 适配器中的 SELECT 语句示例 |Microsoft 文档
description: 选择示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器
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
ms.openlocfilehash: 140e895bf8ec2fb65a848c8752dc8e141530bd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216125"
---
# <a name="examples-for-select-statement"></a><span data-ttu-id="89050-103">SELECT 语句的示例</span><span class="sxs-lookup"><span data-stu-id="89050-103">Examples for SELECT Statement</span></span>
<span data-ttu-id="89050-104">本主题演示各种 SELECT 语句的示例语法。</span><span class="sxs-lookup"><span data-stu-id="89050-104">This topic shows example syntax for various SELECT statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="89050-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="89050-105">Sample statements</span></span> 
  
-   <span data-ttu-id="89050-106">若要列出有关名为 SPFLI 的表中列出的航班的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="89050-106">To list details about flights listed in the table named SPFLI, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   <span data-ttu-id="89050-107">若要将提取的数据存储到一个名为在 flight.txt 文件\\\SAPServer\Extracts，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="89050-107">To store extracted data into a file named flight.txt at \\\SAPServer\Extracts, use the following syntax:</span></span>  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   <span data-ttu-id="89050-108">从纽约到旧金山的所有航班列表详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="89050-108">To list details of all flights from New York to San Francisco, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   <span data-ttu-id="89050-109">到列出的所有详细信息航班从纽约其`connid`字段的值为 1000年到 5000 之间，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="89050-109">To list details of all flights from New York whose `connid` field values are between 1000 and 5000, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   <span data-ttu-id="89050-110">从纽约到用户指定城市的所有航班列表详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="89050-110">To list details of all flights from New York to a user-specified city, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     <span data-ttu-id="89050-111">在此情况下，创建名为的 SAP 参数`@variable`、 指定的值，并将其添加到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="89050-111">In this instance, create an SAP parameter named `@variable`, specify the value, and add it to the corresponding command object.</span></span>  
  
-   <span data-ttu-id="89050-112">LIKE 子句的 SELECT 查询中中的百分号、"%"（对于零个或多个字符的任意字符串） 和下划线"_"（适用于任何单个字符），是允许的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="89050-112">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, "_" (for any single character), are allowable special characters.</span></span> <span data-ttu-id="89050-113">所有其他被视为字符串值，并且将被忽略。</span><span class="sxs-lookup"><span data-stu-id="89050-113">All others are considered string values and are ignored.</span></span>  
  
    -   <span data-ttu-id="89050-114">示例，演示了利用百分比"%"</span><span class="sxs-lookup"><span data-stu-id="89050-114">Example to demonstrate the use of percentage "%"</span></span>  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         <span data-ttu-id="89050-115">在这里，%模式 %提取所有记录其中 Name1 包含字符串"模式"。</span><span class="sxs-lookup"><span data-stu-id="89050-115">Here, %MODE% fetches all records where Name1 contains the string "MODE".</span></span>  
  
    -   <span data-ttu-id="89050-116">示例，演示了利用下划线"_"</span><span class="sxs-lookup"><span data-stu-id="89050-116">Example to demonstrate the use of underscore "_"</span></span>  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         <span data-ttu-id="89050-117">在这里，"D_"提取所有记录其中 Name1 以"D"开头并包含两个字符。</span><span class="sxs-lookup"><span data-stu-id="89050-117">Here, "D_" fetches all records where Name1 starts with "D" and contains two characters.</span></span>  
  
-   <span data-ttu-id="89050-118">示例，演示"之间"谓词子句</span><span class="sxs-lookup"><span data-stu-id="89050-118">Example to demonstrate a "between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="89050-119">示例，演示了"不介于"谓词子句</span><span class="sxs-lookup"><span data-stu-id="89050-119">Example to demonstrate a "not between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="89050-120">更大的示例使用联接和 TOP 子句的 SELECT 语句</span><span class="sxs-lookup"><span data-stu-id="89050-120">Example for SELECT statement using Join and a TOP clause</span></span>  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   <span data-ttu-id="89050-121">更大的示例使用 OPTION 子句的 SELECT 语句</span><span class="sxs-lookup"><span data-stu-id="89050-121">Example for SELECT statement using the OPTION clause</span></span>  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
