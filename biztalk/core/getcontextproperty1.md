---
title: GetContextProperty1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e843a8324526e183a577425a015b49c7be3725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345133"
---
# <a name="getcontextproperty"></a><span data-ttu-id="6c28a-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="6c28a-102">GetContextProperty</span></span>
<span data-ttu-id="6c28a-103">将推送到堆栈上的请求的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="6c28a-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c28a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c28a-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c28a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c28a-105">Parameters</span></span>  
 <span data-ttu-id="6c28a-106">以下上下文属性名称之一：</span><span class="sxs-lookup"><span data-stu-id="6c28a-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="6c28a-107">上下文属性名称</span><span class="sxs-lookup"><span data-stu-id="6c28a-107">Context property name</span></span>|<span data-ttu-id="6c28a-108">Description</span><span class="sxs-lookup"><span data-stu-id="6c28a-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="6c28a-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="6c28a-109">EventTime</span></span>|<span data-ttu-id="6c28a-110">当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6c28a-110">Current date and time.</span></span>|  
|<span data-ttu-id="6c28a-111">SessionId</span><span class="sxs-lookup"><span data-stu-id="6c28a-111">SessionId</span></span>|<span data-ttu-id="6c28a-112">工作流会话 id。</span><span class="sxs-lookup"><span data-stu-id="6c28a-112">Workflow session id.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6c28a-113">上下文属性名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6c28a-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="6c28a-114">推送的值</span><span class="sxs-lookup"><span data-stu-id="6c28a-114">Pushed Value</span></span>  
 <span data-ttu-id="6c28a-115">包含请求的上下文属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="6c28a-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c28a-116">备注</span><span class="sxs-lookup"><span data-stu-id="6c28a-116">Remarks</span></span>  
 <span data-ttu-id="6c28a-117">时间是 UTC 格式存储在数据库内。</span><span class="sxs-lookup"><span data-stu-id="6c28a-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c28a-118">示例</span><span class="sxs-lookup"><span data-stu-id="6c28a-118">Example</span></span>  
 <span data-ttu-id="6c28a-119">在以下示例更新表达式中，通过检索当前事件的事件时间检索审核日期。</span><span class="sxs-lookup"><span data-stu-id="6c28a-119">In the following sample update expression, the approval date is retrieved by retrieving the event time of the current event.</span></span>  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="6c28a-120">这是常见用法的`GetContextProperty`。</span><span class="sxs-lookup"><span data-stu-id="6c28a-120">This is a common use of `GetContextProperty`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c28a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c28a-121">See Also</span></span>  
 [<span data-ttu-id="6c28a-122">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="6c28a-122">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)