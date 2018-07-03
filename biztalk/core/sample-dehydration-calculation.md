---
title: 示例冻结计算 |Microsoft Docs
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
ms.openlocfilehash: 77701083272da9e09c21cb05daf3c4e9764b604c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993038"
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="ab863-102">示例冻结计算</span><span class="sxs-lookup"><span data-stu-id="ab863-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="ab863-103">下面是一个计算示例，它使用专用字节来确定 BizTalk 是否将冻结计算。</span><span class="sxs-lookup"><span data-stu-id="ab863-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="ab863-104">它使用默认配置值以及一些示例运行时值。</span><span class="sxs-lookup"><span data-stu-id="ab863-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="ab863-105">假定冻结属性值如下：</span><span class="sxs-lookup"><span data-stu-id="ab863-105">Assume the following values for the dehydration properties:</span></span>  
  
- <span data-ttu-id="ab863-106">**TimeBlocked** = 60 （示例时间以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ab863-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
- <span data-ttu-id="ab863-107">**WaitingHistory** = 90 （示例等待历史记录以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ab863-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
- <span data-ttu-id="ab863-108">**ActualPrivateBytes** = 250 （专用字节数的示例值）</span><span class="sxs-lookup"><span data-stu-id="ab863-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
- <span data-ttu-id="ab863-109">**OptimalUsage** = 50 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="ab863-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
- <span data-ttu-id="ab863-110">**MaximalUsage** = 350 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="ab863-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
  <span data-ttu-id="ab863-111">由于**ActualPrivateBytes**之间**OptimalUsage**并**MaximalUsage**，所以 alpha 计算为：</span><span class="sxs-lookup"><span data-stu-id="ab863-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="ab863-112">然后计算**TestThreshold** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ab863-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="ab863-113">最终，决定是否冻结：</span><span class="sxs-lookup"><span data-stu-id="ab863-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="ab863-114">使用此示例，您可以确定在此时将不冻结业务流程。</span><span class="sxs-lookup"><span data-stu-id="ab863-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>