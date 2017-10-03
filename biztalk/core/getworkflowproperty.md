---
title: "GetWorkflowProperty |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505fc41ce544cdf16e3826116514ba1991ba012e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowproperty"></a><span data-ttu-id="5bb39-102">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="5bb39-102">GetWorkflowProperty</span></span>
<span data-ttu-id="5bb39-103">将提取的属性从工作流的根活动推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="5bb39-103">Pushes the extracted property from the root activity of the workflow onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb39-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bb39-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bb39-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5bb39-105">Parameters</span></span>  
 <span data-ttu-id="5bb39-106">属性名称。</span><span class="sxs-lookup"><span data-stu-id="5bb39-106">Name of the property.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="5bb39-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="5bb39-107">Pushed Value</span></span>  
 <span data-ttu-id="5bb39-108">包含属性值的字符串。</span><span class="sxs-lookup"><span data-stu-id="5bb39-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bb39-109">注释</span><span class="sxs-lookup"><span data-stu-id="5bb39-109">Remarks</span></span>  
 <span data-ttu-id="5bb39-110">该操作仅在更新中有效。</span><span class="sxs-lookup"><span data-stu-id="5bb39-110">This operation is only valid in Updates.</span></span>  
  
 <span data-ttu-id="5bb39-111">您可以使用以点分隔的表达式来限定希望检索的属性名称。</span><span class="sxs-lookup"><span data-stu-id="5bb39-111">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="5bb39-112">这会为您提供对通过属性公开的其他对象的内部对象的访问。</span><span class="sxs-lookup"><span data-stu-id="5bb39-112">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="5bb39-113">例如，要访问采购订单的 Address 实例的 City 属性，请使用“purchaseOrder.Address.City”。</span><span class="sxs-lookup"><span data-stu-id="5bb39-113">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="5bb39-114">属性名称的第一次匹配区分大小写，其余匹配不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5bb39-114">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="5bb39-115">在 WF 应用程序中，当两个或多个活动属性仅大小写不同时，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="5bb39-115">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="5bb39-116">例如，如果工作流应用程序定义了“myWorkflow”和“MyWorkflow”属性，而您正在查找“MyWorkflow”，则会通过区分大小写匹配与第二个属性进行匹配。</span><span class="sxs-lookup"><span data-stu-id="5bb39-116">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="5bb39-117">如果您指定了“MYWORKFLOW”，则在不区分大小写的匹配尝试失败后，会通过区分大小写匹配与“myWorkflow”进行匹配。</span><span class="sxs-lookup"><span data-stu-id="5bb39-117">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-sensitive match after a case-insensitive match attempt fails.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bb39-118">Null 属性值将导致 NullReferenceException 引发回工作流实例。</span><span class="sxs-lookup"><span data-stu-id="5bb39-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bb39-119">示例</span><span class="sxs-lookup"><span data-stu-id="5bb39-119">Example</span></span>  
 <span data-ttu-id="5bb39-120">在下面的示例中，更新表达式用于通过使用 `GetWorkflowProperty` 持久化采购订单的工作流属性“City”。</span><span class="sxs-lookup"><span data-stu-id="5bb39-120">In the following sample, an update expression is used to persist the workflow property "City" from a purchase order by using `GetWorkflowProperty`.</span></span>  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```