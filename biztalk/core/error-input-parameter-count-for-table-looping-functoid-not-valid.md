---
title: "错误-循环 Functoid 不是有效的表的输入参数计数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 137ee97363adce49bfce6e74c3e154832e70471e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a><span data-ttu-id="31ee2-102">错误-循环 Functoid 不是有效的表的输入参数计数</span><span class="sxs-lookup"><span data-stu-id="31ee2-102">Error - Input Parameter Count for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="31ee2-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="31ee2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="31ee2-104">btm1070</span><span class="sxs-lookup"><span data-stu-id="31ee2-104">btm1070</span></span>  
  
 <span data-ttu-id="31ee2-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="31ee2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="31ee2-106">指定相关的输入参数的数目**表循环**functoid 无效。</span><span class="sxs-lookup"><span data-stu-id="31ee2-106">The number of input parameters specified for the relevant **Table Looping** functoid is not valid.</span></span>  
  
 <span data-ttu-id="31ee2-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="31ee2-107">**User Action**</span></span>  
  
 <span data-ttu-id="31ee2-108">确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid > Functoid**对话框中，是下表中所示。</span><span class="sxs-lookup"><span data-stu-id="31ee2-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ee2-109">“表循环”functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="31ee2-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="31ee2-110">Description</span><span class="sxs-lookup"><span data-stu-id="31ee2-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="31ee2-111">1</span><span class="sxs-lookup"><span data-stu-id="31ee2-111">1</span></span>|<span data-ttu-id="31ee2-112">从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。</span><span class="sxs-lookup"><span data-stu-id="31ee2-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="31ee2-113">2</span><span class="sxs-lookup"><span data-stu-id="31ee2-113">2</span></span>|<span data-ttu-id="31ee2-114">通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="31ee2-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="31ee2-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="31ee2-115">3 – 100</span></span>|<span data-ttu-id="31ee2-116">常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。</span><span class="sxs-lookup"><span data-stu-id="31ee2-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|