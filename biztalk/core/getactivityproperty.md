---
title: GetActivityProperty |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55f0d24da85088fb8f13693c8c71d32bee1bef7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246581"
---
# <a name="getactivityproperty"></a><span data-ttu-id="23179-102">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="23179-102">GetActivityProperty</span></span>
<span data-ttu-id="23179-103">将提取的属性从与跟踪事件相关的活动推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="23179-103">Pushes the extracted property from the activity related to the tracking event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23179-104">语法</span><span class="sxs-lookup"><span data-stu-id="23179-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23179-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="23179-105">Parameters</span></span>  
 <span data-ttu-id="23179-106">属性名称。</span><span class="sxs-lookup"><span data-stu-id="23179-106">Name of the property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23179-107">返回值</span><span class="sxs-lookup"><span data-stu-id="23179-107">Return Value</span></span>  
 <span data-ttu-id="23179-108">包含属性值的字符串。</span><span class="sxs-lookup"><span data-stu-id="23179-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23179-109">注释</span><span class="sxs-lookup"><span data-stu-id="23179-109">Remarks</span></span>  
 <span data-ttu-id="23179-110">您可以使用以点分隔的表达式来限定希望检索的属性名称。</span><span class="sxs-lookup"><span data-stu-id="23179-110">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="23179-111">这会为您提供对通过属性公开的其他对象的内部对象的访问。</span><span class="sxs-lookup"><span data-stu-id="23179-111">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="23179-112">例如，要访问采购订单的 Address 实例的 City 属性，请使用“purchaseOrder.Address.City”。</span><span class="sxs-lookup"><span data-stu-id="23179-112">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="23179-113">属性名称的第一次匹配区分大小写，其余匹配不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="23179-113">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="23179-114">在 WF 应用程序中，当两个或多个活动属性仅大小写不同时，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="23179-114">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="23179-115">例如，如果工作流应用程序定义了“myWorkflow”和“MyWorkflow”属性，而您正在查找“MyWorkflow”，则会通过区分大小写匹配与第二个属性进行匹配。</span><span class="sxs-lookup"><span data-stu-id="23179-115">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="23179-116">如果您指定了“MYWORKFLOW”，则在区分大小写的匹配尝试失败后，会通过不区分大小写匹配与“myWorkflow”进行匹配。</span><span class="sxs-lookup"><span data-stu-id="23179-116">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-insensitive match after a case-sensitive match attempt fails.</span></span>  
  
 <span data-ttu-id="23179-117">例如，如果你有两个活动属性仅可由不同用例:"myProperty"和"MyProperty"。</span><span class="sxs-lookup"><span data-stu-id="23179-117">For example, if you have two activity properties that vary only by case: "myProperty" and "MyProperty".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23179-118">Null 属性值将导致 NullReferenceException 引发回工作流实例。</span><span class="sxs-lookup"><span data-stu-id="23179-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23179-119">示例</span><span class="sxs-lookup"><span data-stu-id="23179-119">Example</span></span>  
 <span data-ttu-id="23179-120">在下面的示例中，更新表达式会用于通过使用 `GetActivityProperty` 持久化活动属性“MyProperty”。</span><span class="sxs-lookup"><span data-stu-id="23179-120">In the following sample, an update expression is used to persist the activity property "MyProperty" by using `GetActivityProperty`.</span></span>  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```