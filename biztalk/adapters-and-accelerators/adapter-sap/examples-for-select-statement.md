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
# <a name="examples-for-select-statement"></a><span data-ttu-id="9b376-103">SELECT 语句示例</span><span class="sxs-lookup"><span data-stu-id="9b376-103">Examples for SELECT Statement</span></span>
<span data-ttu-id="9b376-104">本主题演示各种 SELECT 语句的示例语法。</span><span class="sxs-lookup"><span data-stu-id="9b376-104">This topic shows example syntax for various SELECT statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="9b376-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="9b376-105">Sample statements</span></span> 
  
-   <span data-ttu-id="9b376-106">若要列出有关名为 SPFLI 表中列出的航班的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b376-106">To list details about flights listed in the table named SPFLI, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   <span data-ttu-id="9b376-107">若要将提取的数据存储到一个名为在 flight.txt 文件\\\SAPServer\Extracts，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b376-107">To store extracted data into a file named flight.txt at \\\SAPServer\Extracts, use the following syntax:</span></span>  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   <span data-ttu-id="9b376-108">向列出的所有航班为从纽约飞往旧金山的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b376-108">To list details of all flights from New York to San Francisco, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   <span data-ttu-id="9b376-109">列出的所有详细信息到航班来自纽约的`connid`字段的值为 1000年和 5000 之间，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b376-109">To list details of all flights from New York whose `connid` field values are between 1000 and 5000, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   <span data-ttu-id="9b376-110">向列出的所有航班为从纽约的用户指定城市的详细信息，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b376-110">To list details of all flights from New York to a user-specified city, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     <span data-ttu-id="9b376-111">在本例中，创建一个名为 SAP 参数`@variable`、 指定的值，并将其添加到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="9b376-111">In this instance, create an SAP parameter named `@variable`, specify the value, and add it to the corresponding command object.</span></span>  
  
-   <span data-ttu-id="9b376-112">在 LIKE 子句的 SELECT 查询中，百分号、 （适用于零个或多个字符的任意字符串），"%"和下划线"_"（适用于任何单个字符），是允许的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9b376-112">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, "_" (for any single character), are allowable special characters.</span></span> <span data-ttu-id="9b376-113">所有其他被视为字符串值，将被忽略。</span><span class="sxs-lookup"><span data-stu-id="9b376-113">All others are considered string values and are ignored.</span></span>  
  
    -   <span data-ttu-id="9b376-114">示例演示了如何使用百分比"%"</span><span class="sxs-lookup"><span data-stu-id="9b376-114">Example to demonstrate the use of percentage "%"</span></span>  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         <span data-ttu-id="9b376-115">在这里，%模式 %提取所有记录 Name1 其中包含字符串"模式"。</span><span class="sxs-lookup"><span data-stu-id="9b376-115">Here, %MODE% fetches all records where Name1 contains the string "MODE".</span></span>  
  
    -   <span data-ttu-id="9b376-116">示例演示了如何使用下划线"_"</span><span class="sxs-lookup"><span data-stu-id="9b376-116">Example to demonstrate the use of underscore "_"</span></span>  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         <span data-ttu-id="9b376-117">在这里，"D_"提取其中 Name1 以"D"开头并包含两个字符的所有记录。</span><span class="sxs-lookup"><span data-stu-id="9b376-117">Here, "D_" fetches all records where Name1 starts with "D" and contains two characters.</span></span>  
  
-   <span data-ttu-id="9b376-118">示例，以演示"between"谓词子句</span><span class="sxs-lookup"><span data-stu-id="9b376-118">Example to demonstrate a "between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="9b376-119">示例，以演示"不介于"谓词子句</span><span class="sxs-lookup"><span data-stu-id="9b376-119">Example to demonstrate a "not between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="9b376-120">使用联接和 TOP 子句的 SELECT 语句的示例</span><span class="sxs-lookup"><span data-stu-id="9b376-120">Example for SELECT statement using Join and a TOP clause</span></span>  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   <span data-ttu-id="9b376-121">使用 OPTION 子句的 SELECT 语句的示例</span><span class="sxs-lookup"><span data-stu-id="9b376-121">Example for SELECT statement using the OPTION clause</span></span>  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
