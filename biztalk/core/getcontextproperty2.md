---
title: GetContextProperty2 | Microsoft Docs
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
ms.openlocfilehash: ec2f155b9fdb1cf79419531cc7ec2d3e8b87c791
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387703"
---
# <a name="getcontextproperty"></a><span data-ttu-id="46ce7-102">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="46ce7-102">GetContextProperty</span></span>
<span data-ttu-id="46ce7-103">将推送到堆栈上的请求的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="46ce7-103">Pushes the requested context property onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ce7-104">语法</span><span class="sxs-lookup"><span data-stu-id="46ce7-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46ce7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="46ce7-105">Parameters</span></span>  
 <span data-ttu-id="46ce7-106">以下上下文属性名称之一：</span><span class="sxs-lookup"><span data-stu-id="46ce7-106">One of the following context property names:</span></span>  
  
|<span data-ttu-id="46ce7-107">上下文属性名称</span><span class="sxs-lookup"><span data-stu-id="46ce7-107">Context property name</span></span>|<span data-ttu-id="46ce7-108">Description</span><span class="sxs-lookup"><span data-stu-id="46ce7-108">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="46ce7-109">EventTime</span><span class="sxs-lookup"><span data-stu-id="46ce7-109">EventTime</span></span>|<span data-ttu-id="46ce7-110">当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="46ce7-110">Current date and time.</span></span>|  
|<span data-ttu-id="46ce7-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="46ce7-111">InstanceId</span></span>|<span data-ttu-id="46ce7-112">工作流实例 id。</span><span class="sxs-lookup"><span data-stu-id="46ce7-112">Workflow instance ID.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="46ce7-113">上下文属性名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="46ce7-113">The context property names are case-sensitive.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="46ce7-114">推送的值</span><span class="sxs-lookup"><span data-stu-id="46ce7-114">Pushed Value</span></span>  
 <span data-ttu-id="46ce7-115">包含请求的上下文属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="46ce7-115">String containing the requested context property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ce7-116">备注</span><span class="sxs-lookup"><span data-stu-id="46ce7-116">Remarks</span></span>  
 <span data-ttu-id="46ce7-117">时间是 UTC 格式存储在数据库内。</span><span class="sxs-lookup"><span data-stu-id="46ce7-117">Time is stored in UTC format inside of the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ce7-118">示例</span><span class="sxs-lookup"><span data-stu-id="46ce7-118">Example</span></span>  
 <span data-ttu-id="46ce7-119">在以下示例中，一个表达式，以便拉取**InstanceId**在 correlationID 块内部中用于设置关联 id。</span><span class="sxs-lookup"><span data-stu-id="46ce7-119">In the following sample, an expression for pulling the **InstanceId** is used inside of a correlationID block to set the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="46ce7-120">这是常见用法的`GetContextProperty`。</span><span class="sxs-lookup"><span data-stu-id="46ce7-120">This is a common use of `GetContextProperty`.</span></span>