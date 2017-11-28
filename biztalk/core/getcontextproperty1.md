---
title: "GetContextProperty1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a><span data-ttu-id="0d514-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="0d514-102">GetContextProperty</span></span>
<span data-ttu-id="0d514-103">将请求的上下文属性推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="0d514-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d514-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d514-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d514-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d514-105">Parameters</span></span>  
 <span data-ttu-id="0d514-106">下面的上下文属性名称之一：</span><span class="sxs-lookup"><span data-stu-id="0d514-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="0d514-107">上下文属性名称</span><span class="sxs-lookup"><span data-stu-id="0d514-107">Context property name</span></span>|<span data-ttu-id="0d514-108">Description</span><span class="sxs-lookup"><span data-stu-id="0d514-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="0d514-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="0d514-109">EventTime</span></span>|<span data-ttu-id="0d514-110">当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0d514-110">Current date and time.</span></span>|  
|<span data-ttu-id="0d514-111">SessionId</span><span class="sxs-lookup"><span data-stu-id="0d514-111">SessionId</span></span>|<span data-ttu-id="0d514-112">工作流会话 id。</span><span class="sxs-lookup"><span data-stu-id="0d514-112">Workflow session id.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0d514-113">上下文属性名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0d514-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="0d514-114">推送的值</span><span class="sxs-lookup"><span data-stu-id="0d514-114">Pushed Value</span></span>  
 <span data-ttu-id="0d514-115">包含请求的上下文属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="0d514-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d514-116">注释</span><span class="sxs-lookup"><span data-stu-id="0d514-116">Remarks</span></span>  
 <span data-ttu-id="0d514-117">时间以 UTC 格式存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="0d514-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d514-118">示例</span><span class="sxs-lookup"><span data-stu-id="0d514-118">Example</span></span>  
 <span data-ttu-id="0d514-119">在下面的示例更新表达式，通过检索当前事件的事件时间检索批准日期。</span><span class="sxs-lookup"><span data-stu-id="0d514-119">In the following sample update expression, the approval date is retrieved by retrieving the event time of the current event.</span></span>  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="0d514-120">这是一种常用的`GetContextProperty`。</span><span class="sxs-lookup"><span data-stu-id="0d514-120">This is a common use of `GetContextProperty`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d514-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d514-121">See Also</span></span>  
 [<span data-ttu-id="0d514-122">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="0d514-122">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)