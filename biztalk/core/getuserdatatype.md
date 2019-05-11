---
title: GetUserDataType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78fb7766363b212e6d913565d43f07500b0d1340
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387642"
---
# <a name="getuserdatatype"></a><span data-ttu-id="3525d-102">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="3525d-102">GetUserDataType</span></span>
<span data-ttu-id="3525d-103">将推送到堆栈上的当前用户数据类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3525d-103">Pushes the name of the current user data type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3525d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3525d-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3525d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3525d-105">Parameters</span></span>  
 <span data-ttu-id="3525d-106">无。</span><span class="sxs-lookup"><span data-stu-id="3525d-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="3525d-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="3525d-107">Pushed Value</span></span>  
 <span data-ttu-id="3525d-108">包含程序集限定格式中的当前用户数据类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="3525d-108">String containing the current user data type in assembly-qualified format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3525d-109">备注</span><span class="sxs-lookup"><span data-stu-id="3525d-109">Remarks</span></span>  
 <span data-ttu-id="3525d-110">与不同**GetActivityType**，此操作不使用程序集限定类名格式; 相反，它将推送仅类型名称：</span><span class="sxs-lookup"><span data-stu-id="3525d-110">Unlike **GetActivityType**, this operation does not use the assembly-qualified class name format; instead, it pushes only the type name:</span></span>  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  <span data-ttu-id="3525d-111">如果使用程序集限定类名格式，如常量比较值时将计算结果始终为`false`。</span><span class="sxs-lookup"><span data-stu-id="3525d-111">If you use the assembly-qualified class name format as a constant when comparing values it will always evaluate to `false`.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="3525d-112">特殊筛选器行为</span><span class="sxs-lookup"><span data-stu-id="3525d-112">Special Filter Behavior</span></span>  
 <span data-ttu-id="3525d-113">在筛选器内部执行此操作时，派生的用户数据还将始终匹配类型。</span><span class="sxs-lookup"><span data-stu-id="3525d-113">When this operation is performed inside of a filter, derived user data types are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3525d-114">示例</span><span class="sxs-lookup"><span data-stu-id="3525d-114">Example</span></span>  
 <span data-ttu-id="3525d-115">下面的示例包含的事件筛选器表达式的计算结果将为`true`有关`MyLibrary.MyObject`实例和任何实例派生的类的`MyLibrary.MyObject`。</span><span class="sxs-lookup"><span data-stu-id="3525d-115">The following sample contains an event filter expression that will evaluate to `true` for `MyLibrary.MyObject` instances and for any instances from classes that derive from `MyLibrary.MyObject`.</span></span>  
  
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