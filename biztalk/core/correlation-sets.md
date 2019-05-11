---
title: 相关集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1767755e240171431b01d5997691b800fdbdaa3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354389"
---
# <a name="correlation-sets"></a><span data-ttu-id="9c373-102">相关集</span><span class="sxs-lookup"><span data-stu-id="9c373-102">Correlation Sets</span></span>
<span data-ttu-id="9c373-103">可以通过定义相关集来实现此的类消息与业务流程实例相关。</span><span class="sxs-lookup"><span data-stu-id="9c373-103">You can achieve this sort of correlation of messages with orchestration instances by defining correlation sets.</span></span> <span data-ttu-id="9c373-104">相关集是一组属性*具有特定值*。</span><span class="sxs-lookup"><span data-stu-id="9c373-104">A correlation set is a set of properties *with specific values*.</span></span> <span data-ttu-id="9c373-105">这是不同于相关类型，即只需的属性列表。</span><span class="sxs-lookup"><span data-stu-id="9c373-105">This is different from a correlation type, which is simply a list of properties.</span></span> <span data-ttu-id="9c373-106">如果传入消息不具有所有这些属性，具有匹配的每个值，则相关将失败并且业务流程实例将不接收此消息。</span><span class="sxs-lookup"><span data-stu-id="9c373-106">If an incoming message does not have all of these properties, with matching values for each, correlation will fail and the message will not be received by the orchestration instance.</span></span>  
  
 <span data-ttu-id="9c373-107">相关类型定义一组属性的关联消息。</span><span class="sxs-lookup"><span data-stu-id="9c373-107">Correlation types define a set of properties on which you will be correlating messages.</span></span> <span data-ttu-id="9c373-108">这些可以是任何属性，之前的属性架构中定义并部署与某个 BizTalk 项目，包括与作为基础 BizTalk 安装的一部分安装的 GlobalPropertySchemas 一起部署的"系统"属性。</span><span class="sxs-lookup"><span data-stu-id="9c373-108">These can be any properties which were previously defined in a property schema and deployed with some BizTalk Project including "system" properties deployed with the GlobalPropertySchemas which is installed as part of the base BizTalk install.</span></span> <span data-ttu-id="9c373-109">相关集定义一组属性和消息必须包含由特定业务流程处理这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="9c373-109">A correlation set defines a set of properties and values for these properties that a message must contain to be processed by a particular orchestration.</span></span>  
  
 <span data-ttu-id="9c373-110">例如，相关类型可能包含以下属性：</span><span class="sxs-lookup"><span data-stu-id="9c373-110">For example, a correlation type could consist of the following properties:</span></span>  
  
|<span data-ttu-id="9c373-111">相关类型属性</span><span class="sxs-lookup"><span data-stu-id="9c373-111">Correlation Type Property</span></span>|<span data-ttu-id="9c373-112">可能的 XML 表示形式</span><span class="sxs-lookup"><span data-stu-id="9c373-112">Possible XML Representation</span></span>|  
|-------------------------------|---------------------------------|  
|<span data-ttu-id="9c373-113">社会保障号</span><span class="sxs-lookup"><span data-stu-id="9c373-113">Social Security number</span></span>|<span data-ttu-id="9c373-114">\<SSN\>\</SSN\></span><span class="sxs-lookup"><span data-stu-id="9c373-114">\<SSN\>\</SSN\></span></span>|  
|<span data-ttu-id="9c373-115">出生日期</span><span class="sxs-lookup"><span data-stu-id="9c373-115">Date of Birth</span></span>|<span data-ttu-id="9c373-116">\<DOB\>\</DOB\></span><span class="sxs-lookup"><span data-stu-id="9c373-116">\<DOB\>\</DOB\></span></span>|  
|<span data-ttu-id="9c373-117">性别</span><span class="sxs-lookup"><span data-stu-id="9c373-117">Gender</span></span>|<span data-ttu-id="9c373-118">\<性别\> \< /性别\></span><span class="sxs-lookup"><span data-stu-id="9c373-118">\<Gender\>\</Gender\></span></span>|  
  
 <span data-ttu-id="9c373-119">而从该相关类型派生的相关集可由以下属性和值构成：</span><span class="sxs-lookup"><span data-stu-id="9c373-119">While a correlation set derived from this correlation type could consist of the following properties and values:</span></span>  
  
|<span data-ttu-id="9c373-120">相关集属性/值</span><span class="sxs-lookup"><span data-stu-id="9c373-120">Correlation Set Property/Value</span></span>|<span data-ttu-id="9c373-121">可能的 XML 表示形式</span><span class="sxs-lookup"><span data-stu-id="9c373-121">Possible XML representation</span></span>|  
|-------------------------------------|---------------------------------|  
|<span data-ttu-id="9c373-122">社会保障号 = 222112222</span><span class="sxs-lookup"><span data-stu-id="9c373-122">Social Security number = 222112222</span></span>|<span data-ttu-id="9c373-123">\<SSN\>222112222\</SSN\></span><span class="sxs-lookup"><span data-stu-id="9c373-123">\<SSN\>222112222\</SSN\></span></span>|  
|<span data-ttu-id="9c373-124">出生日期 ="1/1/1995"</span><span class="sxs-lookup"><span data-stu-id="9c373-124">Date of Birth = “1/1/1995”</span></span>|<span data-ttu-id="9c373-125">\<DOB\>”1/1/1995”\</DOB\></span><span class="sxs-lookup"><span data-stu-id="9c373-125">\<DOB\>”1/1/1995”\</DOB\></span></span>|  
|<span data-ttu-id="9c373-126">性别 = Male</span><span class="sxs-lookup"><span data-stu-id="9c373-126">Gender = Male</span></span>|<span data-ttu-id="9c373-127">\<性别\>M \< /性别\></span><span class="sxs-lookup"><span data-stu-id="9c373-127">\<Gender\>M\</Gender\></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9c373-128">每个相关集可支持最多三个参数。</span><span class="sxs-lookup"><span data-stu-id="9c373-128">Each correlation set supports a maximum of three parameters.</span></span>  
  
## <a name="initializing-correlation-sets"></a><span data-ttu-id="9c373-129">初始化相关集</span><span class="sxs-lookup"><span data-stu-id="9c373-129">Initializing Correlation Sets</span></span>  
  
-   <span data-ttu-id="9c373-130">**在接收操作上初始化的相关集**</span><span class="sxs-lookup"><span data-stu-id="9c373-130">**Correlation Sets initialized on a Receive action**</span></span>  
  
     <span data-ttu-id="9c373-131">在操作定义必须存在的属性组中发布的消息，以使其处理由相应的接收初始化的相关集接收业务流程中操作。</span><span class="sxs-lookup"><span data-stu-id="9c373-131">Correlation sets initialized on a Receive action define the exact set of properties that must exist in a published message in order for it to be processed by the corresponding receive action(s) in an orchestration.</span></span> <span data-ttu-id="9c373-132">初始化相关集将创建一个相关集，从基于文档中的相应值的相关类型。</span><span class="sxs-lookup"><span data-stu-id="9c373-132">An initializing correlation set will create a correlation set from a correlation type based on the corresponding values in a document.</span></span>  
  
-   <span data-ttu-id="9c373-133">**在发送操作上初始化的相关集**</span><span class="sxs-lookup"><span data-stu-id="9c373-133">**Correlation Sets initialized on a Send action**</span></span>  
  
     <span data-ttu-id="9c373-134">在发送操作上初始化的相关集，从相关类型基于文档中的相应值创建，并且升级出站文档中的相关属性。</span><span class="sxs-lookup"><span data-stu-id="9c373-134">Correlation sets initialized on a Send action are created from a correlation type based upon the corresponding values in a document and promote the correlation properties in the outbound document.</span></span>  
  
## <a name="following-correlation-sets"></a><span data-ttu-id="9c373-135">沿用相关集</span><span class="sxs-lookup"><span data-stu-id="9c373-135">Following Correlation Sets</span></span>  
 <span data-ttu-id="9c373-136">沿用相关集只能绑定到非激活接收操作或发送操作。</span><span class="sxs-lookup"><span data-stu-id="9c373-136">Following correlation sets can only be bound to a non-activating receive action or to a send action.</span></span> <span data-ttu-id="9c373-137">沿用相关集与以前初始化的相关集一前一后指定。</span><span class="sxs-lookup"><span data-stu-id="9c373-137">Following correlation sets are specified in tandem with previously initialized correlation sets.</span></span>  
  
-   <span data-ttu-id="9c373-138">**绑定到接收操作的沿用相关集**</span><span class="sxs-lookup"><span data-stu-id="9c373-138">**Following Correlation Sets bound to a Receive action**</span></span>  
  
     <span data-ttu-id="9c373-139">沿用相关集绑定到接收操作定义属性和文档必须包含要接收的值的集。</span><span class="sxs-lookup"><span data-stu-id="9c373-139">Following correlation sets bound to a receive action define the set of properties and values that the document must contain to be received.</span></span>  <span data-ttu-id="9c373-140">接收操作的沿用相关集接受包含来自以前初始化的相关集属性的文档。</span><span class="sxs-lookup"><span data-stu-id="9c373-140">Receive actions with following correlation sets accept documents that contain properties from a previously initialized correlation set.</span></span>  
  
-   <span data-ttu-id="9c373-141">**绑定到发送操作的沿用相关集**</span><span class="sxs-lookup"><span data-stu-id="9c373-141">**Following Correlation Sets bound to a Send action**</span></span>  
  
     <span data-ttu-id="9c373-142">沿用相关集绑定到发送操作的规定，出站文档中升级中的相关集的属性集。</span><span class="sxs-lookup"><span data-stu-id="9c373-142">Following correlation sets bound to a send action dictate that the set of properties in the correlation set are promoted in the outbound document.</span></span>  
  
## <a name="inspecting-correlation-sets"></a><span data-ttu-id="9c373-143">检查相关集</span><span class="sxs-lookup"><span data-stu-id="9c373-143">Inspecting Correlation Sets</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9c373-144">提供检查相关集的能力。</span><span class="sxs-lookup"><span data-stu-id="9c373-144">provides the ability to inspect correlation sets.</span></span> <span data-ttu-id="9c373-145">可以使用类似于下面的代码表达式形状中的相关集来检查：</span><span class="sxs-lookup"><span data-stu-id="9c373-145">You can inspect a correlation set in an Expression Shape using code similar to the following:</span></span>  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 <span data-ttu-id="9c373-146">上面的示例假定已创建一个名为变量**MsgLen**类型的**System.Int16** ，并且您的业务流程中包含一个相关集**Correlation_1**.</span><span class="sxs-lookup"><span data-stu-id="9c373-146">The example above assumes that you have created a variable named **MsgLen** of type **System.Int16** and that your orchestration contains a correlation set named **Correlation_1**.</span></span> <span data-ttu-id="9c373-147">若要检查相关集的功能可能需要检查已传递到另一个业务流程通过业务流程的相关值的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="9c373-147">The ability to inspect correlation sets may be useful if you need to inspect the value of a correlation that was passed to an orchestration by another orchestration.</span></span>  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a><span data-ttu-id="9c373-148">向业务流程传递相关集作为参数</span><span class="sxs-lookup"><span data-stu-id="9c373-148">Passing Correlation Sets as Parameters to Orchestrations</span></span>  
 <span data-ttu-id="9c373-149">可以将传递为相关性*在*其他业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="9c373-149">You can pass correlations as *in* parameters to other orchestrations.</span></span>