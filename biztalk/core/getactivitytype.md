---
title: GetActivityType | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded881aa0d7e952ed9fd425c2006982973f3ac5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387697"
---
# <a name="getactivitytype"></a><span data-ttu-id="6e003-102">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="6e003-102">GetActivityType</span></span>
<span data-ttu-id="6e003-103">将推送到堆栈上的当前活动类型的名称。</span><span class="sxs-lookup"><span data-stu-id="6e003-103">Pushes the name of the current activity type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e003-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e003-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e003-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6e003-105">Parameters</span></span>  
 <span data-ttu-id="6e003-106">无。</span><span class="sxs-lookup"><span data-stu-id="6e003-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="6e003-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="6e003-107">Pushed Value</span></span>  
 <span data-ttu-id="6e003-108">包含程序集限定类名格式中的当前活动类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="6e003-108">String containing the current activity type in assembly-qualified class name format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e003-109">备注</span><span class="sxs-lookup"><span data-stu-id="6e003-109">Remarks</span></span>  
 <span data-ttu-id="6e003-110">`GetActivityType`操作检索当前活动类型，并将其放在程序集限定类名格式中的堆栈：</span><span class="sxs-lookup"><span data-stu-id="6e003-110">The `GetActivityType` operation retrieves the current activity type and places it on the stack in assembly-qualified class name format:</span></span>  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 <span data-ttu-id="6e003-111">在比较时，您可以指定尽可能多的类型，以满足您的特定搜索需求。</span><span class="sxs-lookup"><span data-stu-id="6e003-111">When comparing, you can specify as much of the type as necessary to satisfy your specific search needs.</span></span> <span data-ttu-id="6e003-112">例如，您可以比较常量与 GetActivityType 的结果：</span><span class="sxs-lookup"><span data-stu-id="6e003-112">For example, you might compare the result of GetActivityType with the constant:</span></span>  
  
 <span data-ttu-id="6e003-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span><span class="sxs-lookup"><span data-stu-id="6e003-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span></span>  
  
 <span data-ttu-id="6e003-114">这是限制性比程序集限定类名格式。</span><span class="sxs-lookup"><span data-stu-id="6e003-114">This is less restrictive than the assembly-qualified class name format.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="6e003-115">特殊筛选器行为</span><span class="sxs-lookup"><span data-stu-id="6e003-115">Special Filter Behavior</span></span>  
 <span data-ttu-id="6e003-116">在筛选器内部执行此操作时，也始终匹配派生的活动。</span><span class="sxs-lookup"><span data-stu-id="6e003-116">When this operation is performed inside of a filter, derived activities are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e003-117">示例</span><span class="sxs-lookup"><span data-stu-id="6e003-117">Example</span></span>  
 <span data-ttu-id="6e003-118">下面的示例包含的事件筛选器表达式的计算结果将为`true`有关`System.Workflow.ComponentModel.Activity`实例和派生的类中的任何实例`System.Workflow.ComponentModel.Activity`。</span><span class="sxs-lookup"><span data-stu-id="6e003-118">The following sample contains an event filter expression that will evaluate to `true` for `System.Workflow.ComponentModel.Activity` instances and any instances from classes that derive from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```