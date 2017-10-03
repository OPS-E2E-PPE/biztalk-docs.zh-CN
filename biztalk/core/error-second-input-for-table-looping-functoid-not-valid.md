---
title: "错误-为第二个输入表不是有效循环 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caab1e1cac77dda276398fcc0331b2bfac2bcbd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a><span data-ttu-id="72e6f-102">错误-为第二个输入表不是有效循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="72e6f-102">Error - Second Input for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="72e6f-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="72e6f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="72e6f-104">btm1072</span><span class="sxs-lookup"><span data-stu-id="72e6f-104">btm1072</span></span>  
  
 <span data-ttu-id="72e6f-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="72e6f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="72e6f-106">第二个输入参数相关**表循环**functoid 无效。</span><span class="sxs-lookup"><span data-stu-id="72e6f-106">The second input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="72e6f-107">此参数必须是正整数，用于指示相关联的表循环网格中的列数。</span><span class="sxs-lookup"><span data-stu-id="72e6f-107">This parameter must be a positive integer that indicates the number of columns in the associated table looping grid.</span></span>  
  
 <span data-ttu-id="72e6f-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="72e6f-108">**User Action**</span></span>  
  
 <span data-ttu-id="72e6f-109">确保的输入的参数**表循环**functoid，如通过访问**输入参数**属性和**配置\<Functoid > Functoid**对话框中，是下表中所示。</span><span class="sxs-lookup"><span data-stu-id="72e6f-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="72e6f-110">“表循环”functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="72e6f-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="72e6f-111">Description</span><span class="sxs-lookup"><span data-stu-id="72e6f-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="72e6f-112">1</span><span class="sxs-lookup"><span data-stu-id="72e6f-112">1</span></span>|<span data-ttu-id="72e6f-113">从记录的链接或源架构中的字段，其中的次数输入的实例消息控制的次数的一套关联**表提取程序**functoid 运行。</span><span class="sxs-lookup"><span data-stu-id="72e6f-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="72e6f-114">2</span><span class="sxs-lookup"><span data-stu-id="72e6f-114">2</span></span>|<span data-ttu-id="72e6f-115">通过配置的数据表中的列数**表循环网格**的相关属性**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="72e6f-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="72e6f-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="72e6f-116">3 – 100</span></span>|<span data-ttu-id="72e6f-117">常量和链接 （来自源架构或从其他 functoid 的输出中） 将成为可能的与循环网格表的数据源。</span><span class="sxs-lookup"><span data-stu-id="72e6f-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|