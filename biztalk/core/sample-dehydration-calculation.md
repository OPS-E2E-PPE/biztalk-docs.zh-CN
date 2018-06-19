---
title: 示例冻结计算 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ff231b630a5848494c45cd8d4d05f89e764eb41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268877"
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="2ab9f-102">示例冻结计算</span><span class="sxs-lookup"><span data-stu-id="2ab9f-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="2ab9f-103">下面是一个计算示例，它使用专用字节来确定 BizTalk 是否将冻结计算。</span><span class="sxs-lookup"><span data-stu-id="2ab9f-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="2ab9f-104">它使用默认配置值以及一些示例运行时值。</span><span class="sxs-lookup"><span data-stu-id="2ab9f-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="2ab9f-105">假定冻结属性值如下：</span><span class="sxs-lookup"><span data-stu-id="2ab9f-105">Assume the following values for the dehydration properties:</span></span>  
  
-   <span data-ttu-id="2ab9f-106">**TimeBlocked** = 60 （以秒为单位阻止示例时间）</span><span class="sxs-lookup"><span data-stu-id="2ab9f-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
-   <span data-ttu-id="2ab9f-107">**WaitingHistory** = 90 （示例等待历史记录以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="2ab9f-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
-   <span data-ttu-id="2ab9f-108">**ActualPrivateBytes** = 250 （专用字节示例值）</span><span class="sxs-lookup"><span data-stu-id="2ab9f-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
-   <span data-ttu-id="2ab9f-109">**OptimalUsage** = 50 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="2ab9f-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
-   <span data-ttu-id="2ab9f-110">**MaximalUsage** = 350 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="2ab9f-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
 <span data-ttu-id="2ab9f-111">由于**ActualPrivateBytes**之间**OptimalUsage**和**MaximalUsage**，字母的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="2ab9f-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="2ab9f-112">然后你计算**TestThreshold** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ab9f-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="2ab9f-113">最终，决定是否冻结：</span><span class="sxs-lookup"><span data-stu-id="2ab9f-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="2ab9f-114">使用此示例，您可以确定在此时将不冻结业务流程。</span><span class="sxs-lookup"><span data-stu-id="2ab9f-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>