---
title: GetActivityName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597b08fc9ea9f19b6c3d7f7e3488ae7f77b2c62f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387743"
---
# <a name="getactivityname"></a><span data-ttu-id="d17d3-102">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="d17d3-102">GetActivityName</span></span>
<span data-ttu-id="d17d3-103">将推送到堆栈上当前活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d17d3-103">Pushes the name of the current activity onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d17d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d17d3-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d17d3-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d17d3-105">Parameters</span></span>  
 <span data-ttu-id="d17d3-106">无。</span><span class="sxs-lookup"><span data-stu-id="d17d3-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="d17d3-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="d17d3-107">Pushed Value</span></span>  
 <span data-ttu-id="d17d3-108">包含当前活动名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d17d3-108">String containing the current activity name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d17d3-109">备注</span><span class="sxs-lookup"><span data-stu-id="d17d3-109">Remarks</span></span>  
 <span data-ttu-id="d17d3-110">Windows Workflow Foundation 作为一系列由开发人员配置的活动执行其工作。</span><span class="sxs-lookup"><span data-stu-id="d17d3-110">Windows Workflow Foundation performs its work as a series of activities configured by the developer.</span></span> <span data-ttu-id="d17d3-111">每个活动分配在工作流中的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d17d3-111">Each of these activities is assigned a unique name within the workflow.</span></span> <span data-ttu-id="d17d3-112">通过筛选根据其唯一名称，可以拦截特定活动的数据。</span><span class="sxs-lookup"><span data-stu-id="d17d3-112">You can intercept data for a specific activity by filtering based on its unique name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d17d3-113">示例</span><span class="sxs-lookup"><span data-stu-id="d17d3-113">Example</span></span>  
 <span data-ttu-id="d17d3-114">下面的示例包含配置为查找特定活动的事件筛选器表达式-FoodAndDrinksPolicy — 关闭的工作流中。</span><span class="sxs-lookup"><span data-stu-id="d17d3-114">The following sample contains an event filter expression configured to find a specific activity—FoodAndDrinksPolicy—in a Closed workflow.</span></span> <span data-ttu-id="d17d3-115">这是通过使用的操作，包括组合`GetActivityName`， `GetActivityEvent`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="d17d3-115">This is done by using a combination of operations including `GetActivityName`, `GetActivityEvent`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="d17d3-116">此筛选器模式非常常见的 Windows Workflow Foundation 侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="d17d3-116">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d17d3-117">参数不需要引号，除非您明确尝试匹配包含引号的字符串。</span><span class="sxs-lookup"><span data-stu-id="d17d3-117">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>