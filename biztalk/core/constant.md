---
title: 常量 |Microsoft Docs
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
ms.openlocfilehash: ba1da4a690ca37a5012f5abb2e31f1229cb1b4bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354651"
---
# <a name="constant"></a><span data-ttu-id="55a2b-102">常量</span><span class="sxs-lookup"><span data-stu-id="55a2b-102">Constant</span></span>
<span data-ttu-id="55a2b-103">将推送到堆栈上的单个常数值。</span><span class="sxs-lookup"><span data-stu-id="55a2b-103">Pushes a single constant value onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="55a2b-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55a2b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="55a2b-105">Parameters</span></span>  
 <span data-ttu-id="55a2b-106">常量值。</span><span class="sxs-lookup"><span data-stu-id="55a2b-106">Constant value.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="55a2b-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="55a2b-107">Pushed Value</span></span>  
 <span data-ttu-id="55a2b-108">包含的常量值的字符串。</span><span class="sxs-lookup"><span data-stu-id="55a2b-108">String containing the constant value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55a2b-109">备注</span><span class="sxs-lookup"><span data-stu-id="55a2b-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="55a2b-110">示例</span><span class="sxs-lookup"><span data-stu-id="55a2b-110">Example</span></span>  
 <span data-ttu-id="55a2b-111">下面的示例筛选器表达式使用**常量**操作将随后可在使用一个值推**等于**操作以确保当前的活动名称是"FoodAndDrinksPolicy"。</span><span class="sxs-lookup"><span data-stu-id="55a2b-111">The following sample filter expression uses the **Constant** operation to push a value that will then be used in an **Equals** operation to ensure that the current activity name is "FoodAndDrinksPolicy".</span></span>  
  
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
  
 <span data-ttu-id="55a2b-112">这是常见的使用模式**常量**操作。</span><span class="sxs-lookup"><span data-stu-id="55a2b-112">This is a common usage pattern for the **Constant** operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a2b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="55a2b-113">See Also</span></span>  
 [<span data-ttu-id="55a2b-114">侦听器运算</span><span class="sxs-lookup"><span data-stu-id="55a2b-114">Interceptor Operations</span></span>](../core/interceptor-operations.md)