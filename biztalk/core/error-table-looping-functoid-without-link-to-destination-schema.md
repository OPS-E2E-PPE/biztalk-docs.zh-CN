---
title: 错误-表循环 Functoid 缺少到目标架构的链接 |Microsoft Docs
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
ms.openlocfilehash: ee53c8317b3b5d36c6856123354aab5746d5e84d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346607"
---
# <a name="error---table-looping-functoid-without-link-to-destination-schema"></a><span data-ttu-id="4a84d-102">错误-表循环 Functoid 缺少到目标架构的链接</span><span class="sxs-lookup"><span data-stu-id="4a84d-102">Error - Table Looping Functoid Without Link to Destination Schema</span></span>
<span data-ttu-id="4a84d-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="4a84d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="4a84d-104">btm1077</span><span class="sxs-lookup"><span data-stu-id="4a84d-104">btm1077</span></span>  
  
 <span data-ttu-id="4a84d-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="4a84d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="4a84d-106">与大多数 functoid 不同**表循环**functoid 有多个输出。</span><span class="sxs-lookup"><span data-stu-id="4a84d-106">Unlike most functoids, the **Table Looping** functoid has multiple outputs.</span></span> <span data-ttu-id="4a84d-107">除其中一个这些输出必须作为第一个输入参数的单个实例连接**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="4a84d-107">All but one of these outputs must be connected as the first input parameter to separate instances of the **Table Extractor** functoid.</span></span> <span data-ttu-id="4a84d-108">剩余的输出必须连接到**记录**目标架构中的节点 （有适当的重复设置）。</span><span class="sxs-lookup"><span data-stu-id="4a84d-108">The remaining output must be connected to a **Record** node (with appropriate recurrence settings) in the destination schema.</span></span> <span data-ttu-id="4a84d-109">此错误发生时这后一种从输出链接**表循环**functoid 缺少。</span><span class="sxs-lookup"><span data-stu-id="4a84d-109">This error occurs when this latter output link from a **Table Looping** functoid is missing.</span></span>  
  
 <span data-ttu-id="4a84d-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="4a84d-110">**User Action**</span></span>  
  
 <span data-ttu-id="4a84d-111">将所指示**表循环**记录到适当**记录**要创建缺少的链接的目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="4a84d-111">Drag the indicated **Table Looping** record to the appropriate **Record** node in the destination schema to create the missing link.</span></span>