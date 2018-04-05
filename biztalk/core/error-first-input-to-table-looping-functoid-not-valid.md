---
title: 错误-第一个输入到循环 Functoid 不是有效的表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputForTableLoopingNotValid
ms.assetid: 3ece2c0c-bcac-42d5-9536-34f073937879
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9ebecbd92b43dd25e6ff3dde04d942b936f40d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---first-input-to-table-looping-functoid-not-valid"></a><span data-ttu-id="4aabf-102">错误-第一个输入到循环 Functoid 不是有效的表</span><span class="sxs-lookup"><span data-stu-id="4aabf-102">Error - First Input to Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="4aabf-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="4aabf-103">**Error Code**</span></span>  
  
 <span data-ttu-id="4aabf-104">btm1071</span><span class="sxs-lookup"><span data-stu-id="4aabf-104">btm1071</span></span>  
  
 <span data-ttu-id="4aabf-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="4aabf-105">**Explanation**</span></span>  
  
 <span data-ttu-id="4aabf-106">到相关的第一个输入的参数**表循环**functoid 无效。</span><span class="sxs-lookup"><span data-stu-id="4aabf-106">The first input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="4aabf-107">此参数必须是来自源架构中的节点的链接-输入的实例消息中的相应元素的出现次数将控制的组的关联的次数**表提取程序**functoid将在运行时调用。</span><span class="sxs-lookup"><span data-stu-id="4aabf-107">This parameter must be a link from a node in the source schema—the number of occurrences of the corresponding element in an input instance message will control the number of times that the set of associated **Table Extractor** functoids will be invoked at run time.</span></span>  
  
 <span data-ttu-id="4aabf-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="4aabf-108">**User Action**</span></span>  
  
 <span data-ttu-id="4aabf-109">确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid\>Functoid**对话框中，是下表中所示。</span><span class="sxs-lookup"><span data-stu-id="4aabf-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="4aabf-110">“表循环”functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="4aabf-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="4aabf-111">Description</span><span class="sxs-lookup"><span data-stu-id="4aabf-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="4aabf-112">1</span><span class="sxs-lookup"><span data-stu-id="4aabf-112">1</span></span>|<span data-ttu-id="4aabf-113">从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。</span><span class="sxs-lookup"><span data-stu-id="4aabf-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="4aabf-114">2</span><span class="sxs-lookup"><span data-stu-id="4aabf-114">2</span></span>|<span data-ttu-id="4aabf-115">通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="4aabf-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="4aabf-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="4aabf-116">3 – 100</span></span>|<span data-ttu-id="4aabf-117">常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。</span><span class="sxs-lookup"><span data-stu-id="4aabf-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|