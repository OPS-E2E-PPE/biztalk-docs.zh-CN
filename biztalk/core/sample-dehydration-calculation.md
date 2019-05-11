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
ms.openlocfilehash: 025d83e8a7bd6c5a3c324bd5dae8354ac43321ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393904"
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="dd423-102">示例冻结计算</span><span class="sxs-lookup"><span data-stu-id="dd423-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="dd423-103">下面是示例计算，使用专用字节数，以确定将冻结 BizTalk 的示例。</span><span class="sxs-lookup"><span data-stu-id="dd423-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="dd423-104">它使用默认配置值和一些示例运行时的值。</span><span class="sxs-lookup"><span data-stu-id="dd423-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="dd423-105">假定冻结属性的以下值：</span><span class="sxs-lookup"><span data-stu-id="dd423-105">Assume the following values for the dehydration properties:</span></span>  
  
- <span data-ttu-id="dd423-106">**TimeBlocked** = 60 （示例时间以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="dd423-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
- <span data-ttu-id="dd423-107">**WaitingHistory** = 90 （示例等待历史记录以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="dd423-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
- <span data-ttu-id="dd423-108">**ActualPrivateBytes** = 250 （专用字节数的示例值）</span><span class="sxs-lookup"><span data-stu-id="dd423-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
- <span data-ttu-id="dd423-109">**OptimalUsage** = 50 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="dd423-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
- <span data-ttu-id="dd423-110">**MaximalUsage** = 350 （默认配置值）</span><span class="sxs-lookup"><span data-stu-id="dd423-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
  <span data-ttu-id="dd423-111">由于**ActualPrivateBytes**之间**OptimalUsage**并**MaximalUsage**，所以 alpha 计算为：</span><span class="sxs-lookup"><span data-stu-id="dd423-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="dd423-112">然后计算**TestThreshold** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dd423-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="dd423-113">和最后，决定冻结：</span><span class="sxs-lookup"><span data-stu-id="dd423-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="dd423-114">使用此示例中，可以确定，该业务流程将不会冻结这一次。</span><span class="sxs-lookup"><span data-stu-id="dd423-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>