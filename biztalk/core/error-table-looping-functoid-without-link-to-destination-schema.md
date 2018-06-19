---
title: 错误-循环 Functoid 而无需链接到目标架构的表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingNoLinkToDestSchema
ms.assetid: cf162e6a-5c61-4adc-978b-af641db67ed2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329e6670288f05382acf0ea014ba9ae84c4cb645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240781"
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a><span data-ttu-id="2dd5f-102">错误-循环 Functoid 而无需链接到目标架构的表</span><span class="sxs-lookup"><span data-stu-id="2dd5f-102">Error - Table Looping Functoid Without Link to Destination Schema</span></span>
<span data-ttu-id="2dd5f-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="2dd5f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2dd5f-104">btm1077</span><span class="sxs-lookup"><span data-stu-id="2dd5f-104">btm1077</span></span>  
  
 <span data-ttu-id="2dd5f-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="2dd5f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2dd5f-106">与大多数 functoid 不同**表循环**functoid 具有多个输出。</span><span class="sxs-lookup"><span data-stu-id="2dd5f-106">Unlike most functoids, the **Table Looping** functoid has multiple outputs.</span></span> <span data-ttu-id="2dd5f-107">除这些输出之一必须连接为独立的实例的第一个输入参数**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="2dd5f-107">All but one of these outputs must be connected as the first input parameter to separate instances of the **Table Extractor** functoid.</span></span> <span data-ttu-id="2dd5f-108">剩余的输出必须连接到**记录**目标架构中的节点 （带有适当的重复设置）。</span><span class="sxs-lookup"><span data-stu-id="2dd5f-108">The remaining output must be connected to a **Record** node (with appropriate recurrence settings) in the destination schema.</span></span> <span data-ttu-id="2dd5f-109">该错误发生时这后者从输出链接**表循环**functoid 没有。</span><span class="sxs-lookup"><span data-stu-id="2dd5f-109">This error occurs when this latter output link from a **Table Looping** functoid is missing.</span></span>  
  
 <span data-ttu-id="2dd5f-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="2dd5f-110">**User Action**</span></span>  
  
 <span data-ttu-id="2dd5f-111">拖动指示**表循环**记录为相应**记录**目标架构创建缺少链接中的节点。</span><span class="sxs-lookup"><span data-stu-id="2dd5f-111">Drag the indicated **Table Looping** record to the appropriate **Record** node in the destination schema to create the missing link.</span></span>