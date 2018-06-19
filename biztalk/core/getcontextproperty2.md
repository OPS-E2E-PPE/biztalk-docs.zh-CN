---
title: GetContextProperty2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246141"
---
# <a name="getcontextproperty"></a><span data-ttu-id="8326e-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="8326e-102">GetContextProperty</span></span>
<span data-ttu-id="8326e-103">将请求的上下文属性推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="8326e-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8326e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8326e-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8326e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8326e-105">Parameters</span></span>  
 <span data-ttu-id="8326e-106">下面的上下文属性名称之一：</span><span class="sxs-lookup"><span data-stu-id="8326e-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="8326e-107">上下文属性名称</span><span class="sxs-lookup"><span data-stu-id="8326e-107">Context property name</span></span>|<span data-ttu-id="8326e-108">Description</span><span class="sxs-lookup"><span data-stu-id="8326e-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="8326e-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="8326e-109">EventTime</span></span>|<span data-ttu-id="8326e-110">当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8326e-110">Current date and time.</span></span>|  
|<span data-ttu-id="8326e-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8326e-111">InstanceId</span></span>|<span data-ttu-id="8326e-112">工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="8326e-112">Workflow instance ID.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8326e-113">上下文属性名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8326e-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="8326e-114">推送的值</span><span class="sxs-lookup"><span data-stu-id="8326e-114">Pushed Value</span></span>  
 <span data-ttu-id="8326e-115">包含请求的上下文属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="8326e-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8326e-116">注释</span><span class="sxs-lookup"><span data-stu-id="8326e-116">Remarks</span></span>  
 <span data-ttu-id="8326e-117">时间以 UTC 格式存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="8326e-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8326e-118">示例</span><span class="sxs-lookup"><span data-stu-id="8326e-118">Example</span></span>  
 <span data-ttu-id="8326e-119">在下面的示例中，一个表达式，以便拉取**InstanceId** correlationID 块内中用于设置相关 id。</span><span class="sxs-lookup"><span data-stu-id="8326e-119">In the following sample, an expression for pulling the **InstanceId** is used inside of a correlationID block to set the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="8326e-120">这是一种常用的`GetContextProperty`。</span><span class="sxs-lookup"><span data-stu-id="8326e-120">This is a common use of `GetContextProperty`.</span></span>