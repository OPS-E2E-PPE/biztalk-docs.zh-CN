---
title: "GetUserDataType |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getuserdatatype"></a><span data-ttu-id="17576-102">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="17576-102">GetUserDataType</span></span>
<span data-ttu-id="17576-103">将当前用户数据类型的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="17576-103">Pushes the name of the current user data type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17576-104">语法</span><span class="sxs-lookup"><span data-stu-id="17576-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17576-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="17576-105">Parameters</span></span>  
 <span data-ttu-id="17576-106">无。</span><span class="sxs-lookup"><span data-stu-id="17576-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="17576-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="17576-107">Pushed Value</span></span>  
 <span data-ttu-id="17576-108">包含程序集限定格式的当前用户数据类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="17576-108">String containing the current user data type in assembly-qualified format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17576-109">注释</span><span class="sxs-lookup"><span data-stu-id="17576-109">Remarks</span></span>  
 <span data-ttu-id="17576-110">与不同**GetActivityType**，此操作不使用限定程序集的类名的格式; 相反，它会推送仅的类型名称：</span><span class="sxs-lookup"><span data-stu-id="17576-110">Unlike **GetActivityType**, this operation does not use the assembly-qualified class name format; instead, it pushes only the type name:</span></span>  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  <span data-ttu-id="17576-111">如果比较值时使用程序集限定类名格式作为常数，计算结果将始终为 `false`。</span><span class="sxs-lookup"><span data-stu-id="17576-111">If you use the assembly-qualified class name format as a constant when comparing values it will always evaluate to `false`.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="17576-112">特殊筛选器行为</span><span class="sxs-lookup"><span data-stu-id="17576-112">Special Filter Behavior</span></span>  
 <span data-ttu-id="17576-113">在筛选器内部执行此操作时，还将始终匹配派生的用户数据类型。</span><span class="sxs-lookup"><span data-stu-id="17576-113">When this operation is performed inside of a filter, derived user data types are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17576-114">示例</span><span class="sxs-lookup"><span data-stu-id="17576-114">Example</span></span>  
 <span data-ttu-id="17576-115">以下示例包含的事件筛选器表达式对 `true` 实例和派生自 `MyLibrary.MyObject` 的类的任何实例的计算结果将为 `MyLibrary.MyObject`。</span><span class="sxs-lookup"><span data-stu-id="17576-115">The following sample contains an event filter expression that will evaluate to `true` for `MyLibrary.MyObject` instances and for any instances from classes that derive from `MyLibrary.MyObject`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyLibrary.MyObject</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```