---
title: 常量 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237789"
---
# <a name="constant"></a><span data-ttu-id="c262e-102">常量</span><span class="sxs-lookup"><span data-stu-id="c262e-102">Constant</span></span>
<span data-ttu-id="c262e-103">将单一常数值推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c262e-103">Pushes a single constant value onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c262e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c262e-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c262e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c262e-105">Parameters</span></span>  
 <span data-ttu-id="c262e-106">常量值。</span><span class="sxs-lookup"><span data-stu-id="c262e-106">Constant value.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c262e-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="c262e-107">Pushed Value</span></span>  
 <span data-ttu-id="c262e-108">包含常数值的字符串。</span><span class="sxs-lookup"><span data-stu-id="c262e-108">String containing the constant value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c262e-109">注释</span><span class="sxs-lookup"><span data-stu-id="c262e-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="c262e-110">示例</span><span class="sxs-lookup"><span data-stu-id="c262e-110">Example</span></span>  
 <span data-ttu-id="c262e-111">下面的示例筛选器表达式使用**常量**操作以将一个值，然后将使用在推送**等于**操作以确保当前的活动名称是"FoodAndDrinksPolicy"。</span><span class="sxs-lookup"><span data-stu-id="c262e-111">The following sample filter expression uses the **Constant** operation to push a value that will then be used in an **Equals** operation to ensure that the current activity name is "FoodAndDrinksPolicy".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="c262e-112">这是常用的使用情况模式**常量**操作。</span><span class="sxs-lookup"><span data-stu-id="c262e-112">This is a common usage pattern for the **Constant** operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c262e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c262e-113">See Also</span></span>  
 [<span data-ttu-id="c262e-114">拦截器操作</span><span class="sxs-lookup"><span data-stu-id="c262e-114">Interceptor Operations</span></span>](../core/interceptor-operations.md)