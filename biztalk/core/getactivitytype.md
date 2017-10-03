---
title: "GetActivityType |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67e6f31331907e20e810c11e82002fb08b89abe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getactivitytype"></a><span data-ttu-id="c2102-102">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="c2102-102">GetActivityType</span></span>
<span data-ttu-id="c2102-103">将当前活动类型的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c2102-103">Pushes the name of the current activity type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2102-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2102-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2102-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c2102-105">Parameters</span></span>  
 <span data-ttu-id="c2102-106">无。</span><span class="sxs-lookup"><span data-stu-id="c2102-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c2102-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="c2102-107">Pushed Value</span></span>  
 <span data-ttu-id="c2102-108">包含当前活动类型且采用了程序集限定类名格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="c2102-108">String containing the current activity type in assembly-qualified class name format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2102-109">注释</span><span class="sxs-lookup"><span data-stu-id="c2102-109">Remarks</span></span>  
 <span data-ttu-id="c2102-110">`GetActivityType`操作检索当前的活动类型，并将其放在程序集限定类名的格式中的堆栈：</span><span class="sxs-lookup"><span data-stu-id="c2102-110">The `GetActivityType` operation retrieves the current activity type and places it on the stack in assembly-qualified class name format:</span></span>  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 <span data-ttu-id="c2102-111">进行比较时，您可以指定尽可能多的类型，以满足您的特定搜索需求。</span><span class="sxs-lookup"><span data-stu-id="c2102-111">When comparing, you can specify as much of the type as necessary to satisfy your specific search needs.</span></span> <span data-ttu-id="c2102-112">例如，您可以将 GetActivityType 的结果与常数比较：</span><span class="sxs-lookup"><span data-stu-id="c2102-112">For example, you might compare the result of GetActivityType with the constant:</span></span>  
  
 <span data-ttu-id="c2102-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span><span class="sxs-lookup"><span data-stu-id="c2102-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span></span>  
  
 <span data-ttu-id="c2102-114">这比程序集限定类名格式的限制更少。</span><span class="sxs-lookup"><span data-stu-id="c2102-114">This is less restrictive than the assembly-qualified class name format.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="c2102-115">特殊筛选器行为</span><span class="sxs-lookup"><span data-stu-id="c2102-115">Special Filter Behavior</span></span>  
 <span data-ttu-id="c2102-116">在筛选器内部执行此操作时，还将始终匹配派生的活动。</span><span class="sxs-lookup"><span data-stu-id="c2102-116">When this operation is performed inside of a filter, derived activities are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2102-117">示例</span><span class="sxs-lookup"><span data-stu-id="c2102-117">Example</span></span>  
 <span data-ttu-id="c2102-118">下面的示例包含计算结果将为事件筛选器表达式`true`为`System.Workflow.ComponentModel.Activity`实例和从其中派生类中的所有实例`System.Workflow.ComponentModel.Activity`。</span><span class="sxs-lookup"><span data-stu-id="c2102-118">The following sample contains an event filter expression that will evaluate to `true` for `System.Workflow.ComponentModel.Activity` instances and any instances from classes that derive from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```