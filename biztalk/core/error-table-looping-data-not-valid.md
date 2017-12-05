---
title: "错误-循环不是有效的数据的表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9478026980ecaf3e2049773737250c56d18262c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---table-looping-data-not-valid"></a><span data-ttu-id="682fd-102">错误-循环不是有效的数据的表</span><span class="sxs-lookup"><span data-stu-id="682fd-102">Error - Table Looping Data Not Valid</span></span>
<span data-ttu-id="682fd-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="682fd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="682fd-104">btm1065</span><span class="sxs-lookup"><span data-stu-id="682fd-104">btm1065</span></span>  
  
 <span data-ttu-id="682fd-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="682fd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="682fd-106">与相关的数据的表**表循环**functoid 不是有效的可能是由于配置不正确到 functoid 或配置不正确表循环网格第二个输入参数。</span><span class="sxs-lookup"><span data-stu-id="682fd-106">The table of data associated with the relevant **Table Looping** functoid is not valid, probably due to an incorrectly configured second input parameter to the functoid, or an incorrectly configured table looping grid.</span></span>  
  
 <span data-ttu-id="682fd-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="682fd-107">**User Action**</span></span>  
  
 <span data-ttu-id="682fd-108">确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid\>Functoid**对话框中，是下表中所示。</span><span class="sxs-lookup"><span data-stu-id="682fd-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="682fd-109">“表循环”functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="682fd-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="682fd-110">Description</span><span class="sxs-lookup"><span data-stu-id="682fd-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="682fd-111">1</span><span class="sxs-lookup"><span data-stu-id="682fd-111">1</span></span>|<span data-ttu-id="682fd-112">从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。</span><span class="sxs-lookup"><span data-stu-id="682fd-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="682fd-113">2</span><span class="sxs-lookup"><span data-stu-id="682fd-113">2</span></span>|<span data-ttu-id="682fd-114">通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="682fd-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="682fd-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="682fd-115">3 – 100</span></span>|<span data-ttu-id="682fd-116">常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。</span><span class="sxs-lookup"><span data-stu-id="682fd-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|  
  
 <span data-ttu-id="682fd-117">此外，请确保正确配置表循环网格中，如通过访问**表循环网格**属性和**表循环配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="682fd-117">Also, ensure that you properly configure the table looping grid, as accessed through the **Table Looping Grid** property and the **Table Looping Configuration** dialog box.</span></span> <span data-ttu-id="682fd-118">一个常数或链接的值必须为将访问每个单元格选择通过一个关联**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="682fd-118">A constant or link value must be chosen for every cell that will be accessed by an associated **Table Extractor** functoid.</span></span>