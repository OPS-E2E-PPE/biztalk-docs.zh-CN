---
title: GetActivityName |Microsoft 文档
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
ms.openlocfilehash: 55e8f35746f5f4ed1bbbe10a4d45300895340869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246341"
---
# <a name="getactivityname"></a><span data-ttu-id="ad409-102">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="ad409-102">GetActivityName</span></span>
<span data-ttu-id="ad409-103">将当前活动的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="ad409-103">Pushes the name of the current activity onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad409-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad409-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad409-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ad409-105">Parameters</span></span>  
 <span data-ttu-id="ad409-106">无。</span><span class="sxs-lookup"><span data-stu-id="ad409-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="ad409-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="ad409-107">Pushed Value</span></span>  
 <span data-ttu-id="ad409-108">包含当前活动名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="ad409-108">String containing the current activity name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad409-109">注释</span><span class="sxs-lookup"><span data-stu-id="ad409-109">Remarks</span></span>  
 <span data-ttu-id="ad409-110">Windows Workflow Foundation 所执行的工作为开发人员配置的一系列活动。</span><span class="sxs-lookup"><span data-stu-id="ad409-110">Windows Workflow Foundation performs its work as a series of activities configured by the developer.</span></span> <span data-ttu-id="ad409-111">在工作流中将为每个活动分配唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="ad409-111">Each of these activities is assigned a unique name within the workflow.</span></span> <span data-ttu-id="ad409-112">根据活动的唯一名称进行筛选，您可以侦听特定活动的数据。</span><span class="sxs-lookup"><span data-stu-id="ad409-112">You can intercept data for a specific activity by filtering based on its unique name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad409-113">示例</span><span class="sxs-lookup"><span data-stu-id="ad409-113">Example</span></span>  
 <span data-ttu-id="ad409-114">下面的示例包含一个配置为在关闭的工作流中查找特定活动 FoodAndDrinksPolicy 的事件筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="ad409-114">The following sample contains an event filter expression configured to find a specific activity—FoodAndDrinksPolicy—in a Closed workflow.</span></span> <span data-ttu-id="ad409-115">这可通过使用的操作包括组合`GetActivityName`， `GetActivityEvent`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="ad409-115">This is done by using a combination of operations including `GetActivityName`, `GetActivityEvent`, and logical operations.</span></span>  
  
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
  
 <span data-ttu-id="ad409-116">该筛选模式常用于 Windows Workflow Foundation 侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="ad409-116">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad409-117">参数不需要使用引号，除非您明确尝试匹配包含引号的字符串。</span><span class="sxs-lookup"><span data-stu-id="ad409-117">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>