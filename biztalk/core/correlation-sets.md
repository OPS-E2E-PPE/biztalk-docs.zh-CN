---
title: "关联集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bad0bf41f5b509f9a64e9484cac84f66a84e4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="correlation-sets"></a><span data-ttu-id="8cc94-102">关联集</span><span class="sxs-lookup"><span data-stu-id="8cc94-102">Correlation Sets</span></span>
<span data-ttu-id="8cc94-103">您可以通过定义相关集，实现消息与业务流程实例的此类相关。</span><span class="sxs-lookup"><span data-stu-id="8cc94-103">You can achieve this sort of correlation of messages with orchestration instances by defining correlation sets.</span></span> <span data-ttu-id="8cc94-104">相关集是一组属性*具有特定值*。</span><span class="sxs-lookup"><span data-stu-id="8cc94-104">A correlation set is a set of properties *with specific values*.</span></span> <span data-ttu-id="8cc94-105">相关集不同于相关类型，后者只是属性的列表。</span><span class="sxs-lookup"><span data-stu-id="8cc94-105">This is different from a correlation type, which is simply a list of properties.</span></span> <span data-ttu-id="8cc94-106">如果某一传入消息不具有所有这些属性（每个属性都有匹配的值），则相关将失败，并且业务流程实例将不会收到该消息。</span><span class="sxs-lookup"><span data-stu-id="8cc94-106">If an incoming message does not have all of these properties, with matching values for each, correlation will fail and the message will not be received by the orchestration instance.</span></span>  
  
 <span data-ttu-id="8cc94-107">相关类型定义将关联消息的一组属性。</span><span class="sxs-lookup"><span data-stu-id="8cc94-107">Correlation types define a set of properties on which you will be correlating messages.</span></span> <span data-ttu-id="8cc94-108">这些属性可以是以前在属性架构中定义并与某个 BizTalk 项目一起部署的任何属性，包括与作为基础 BizTalk 安装的一部分安装的 GlobalPropertySchemas 一起部署的“system”属性。</span><span class="sxs-lookup"><span data-stu-id="8cc94-108">These can be any properties which were previously defined in a property schema and deployed with some BizTalk Project including "system" properties deployed with the GlobalPropertySchemas which is installed as part of the base BizTalk install.</span></span> <span data-ttu-id="8cc94-109">相关集对消息必须包含的属性定义一组属性和相应的值，以便特定业务流程对该消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="8cc94-109">A correlation set defines a set of properties and values for these properties that a message must contain to be processed by a particular orchestration.</span></span>  
  
 <span data-ttu-id="8cc94-110">例如，某一相关类型可由以下属性构成：</span><span class="sxs-lookup"><span data-stu-id="8cc94-110">For example, a correlation type could consist of the following properties:</span></span>  
  
|<span data-ttu-id="8cc94-111">相关类型属性</span><span class="sxs-lookup"><span data-stu-id="8cc94-111">Correlation Type Property</span></span>|<span data-ttu-id="8cc94-112">可能的 XML 表示形式</span><span class="sxs-lookup"><span data-stu-id="8cc94-112">Possible XML Representation</span></span>|  
|-------------------------------|---------------------------------|  
|<span data-ttu-id="8cc94-113">社会保障号</span><span class="sxs-lookup"><span data-stu-id="8cc94-113">Social Security number</span></span>|<span data-ttu-id="8cc94-114">\<SSN\>\</SSN\></span><span class="sxs-lookup"><span data-stu-id="8cc94-114">\<SSN\>\</SSN\></span></span>|  
|<span data-ttu-id="8cc94-115">出生日期</span><span class="sxs-lookup"><span data-stu-id="8cc94-115">Date of Birth</span></span>|<span data-ttu-id="8cc94-116">\<DOB\>\</DOB\></span><span class="sxs-lookup"><span data-stu-id="8cc94-116">\<DOB\>\</DOB\></span></span>|  
|<span data-ttu-id="8cc94-117">性别</span><span class="sxs-lookup"><span data-stu-id="8cc94-117">Gender</span></span>|<span data-ttu-id="8cc94-118">\<性别\> \< /性别\></span><span class="sxs-lookup"><span data-stu-id="8cc94-118">\<Gender\>\</Gender\></span></span>|  
  
 <span data-ttu-id="8cc94-119">在从该相关类型派生的相关集可由以下属性和值构成时：</span><span class="sxs-lookup"><span data-stu-id="8cc94-119">While a correlation set derived from this correlation type could consist of the following properties and values:</span></span>  
  
|<span data-ttu-id="8cc94-120">相关集属性/值</span><span class="sxs-lookup"><span data-stu-id="8cc94-120">Correlation Set Property/Value</span></span>|<span data-ttu-id="8cc94-121">可能的 XML 表示形式</span><span class="sxs-lookup"><span data-stu-id="8cc94-121">Possible XML representation</span></span>|  
|-------------------------------------|---------------------------------|  
|<span data-ttu-id="8cc94-122">社会保障号 = 222112222</span><span class="sxs-lookup"><span data-stu-id="8cc94-122">Social Security number = 222112222</span></span>|<span data-ttu-id="8cc94-123">\<SSN\>222112222\</SSN\></span><span class="sxs-lookup"><span data-stu-id="8cc94-123">\<SSN\>222112222\</SSN\></span></span>|  
|<span data-ttu-id="8cc94-124">出生日期 = “1/1/1995”</span><span class="sxs-lookup"><span data-stu-id="8cc94-124">Date of Birth = “1/1/1995”</span></span>|<span data-ttu-id="8cc94-125">\<DOB\>"1/1/1995"\</DOB\></span><span class="sxs-lookup"><span data-stu-id="8cc94-125">\<DOB\>”1/1/1995”\</DOB\></span></span>|  
|<span data-ttu-id="8cc94-126">性别 = Male</span><span class="sxs-lookup"><span data-stu-id="8cc94-126">Gender = Male</span></span>|<span data-ttu-id="8cc94-127">\<性别\>M \< /性别\></span><span class="sxs-lookup"><span data-stu-id="8cc94-127">\<Gender\>M\</Gender\></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8cc94-128">每个相关集都支持最多三个字符。</span><span class="sxs-lookup"><span data-stu-id="8cc94-128">Each correlation set supports a maximum of three parameters.</span></span>  
  
## <a name="initializing-correlation-sets"></a><span data-ttu-id="8cc94-129">初始化相关集</span><span class="sxs-lookup"><span data-stu-id="8cc94-129">Initializing Correlation Sets</span></span>  
  
-   <span data-ttu-id="8cc94-130">**关联集上的接收操作的初始化**</span><span class="sxs-lookup"><span data-stu-id="8cc94-130">**Correlation Sets initialized on a Receive action**</span></span>  
  
     <span data-ttu-id="8cc94-131">在接收操作上初始化的相关集定义必须在发布的消息中存在的完全匹配的一组属性，以便发布的消息可由业务流程中的相应接收操作进行处理。</span><span class="sxs-lookup"><span data-stu-id="8cc94-131">Correlation sets initialized on a Receive action define the exact set of properties that must exist in a published message in order for it to be processed by the corresponding receive action(s) in an orchestration.</span></span> <span data-ttu-id="8cc94-132">初始化相关集将基于某一文档中的相应值，从相关类型创建一个相关集。</span><span class="sxs-lookup"><span data-stu-id="8cc94-132">An initializing correlation set will create a correlation set from a correlation type based on the corresponding values in a document.</span></span>  
  
-   <span data-ttu-id="8cc94-133">**关联集初始化发送操作**</span><span class="sxs-lookup"><span data-stu-id="8cc94-133">**Correlation Sets initialized on a Send action**</span></span>  
  
     <span data-ttu-id="8cc94-134">在发送操作上初始化的相关集基于文档中的相应值从某一相关类型创建，并且升级出站文档中的相关属性。</span><span class="sxs-lookup"><span data-stu-id="8cc94-134">Correlation sets initialized on a Send action are created from a correlation type based upon the corresponding values in a document and promote the correlation properties in the outbound document.</span></span>  
  
## <a name="following-correlation-sets"></a><span data-ttu-id="8cc94-135">沿用相关集</span><span class="sxs-lookup"><span data-stu-id="8cc94-135">Following Correlation Sets</span></span>  
 <span data-ttu-id="8cc94-136">沿用相关集只能绑定到非激活接收操作或发送操作。</span><span class="sxs-lookup"><span data-stu-id="8cc94-136">Following correlation sets can only be bound to a non-activating receive action or to a send action.</span></span> <span data-ttu-id="8cc94-137">沿用相关集与以前初始化的相关集一前一后指定。</span><span class="sxs-lookup"><span data-stu-id="8cc94-137">Following correlation sets are specified in tandem with previously initialized correlation sets.</span></span>  
  
-   <span data-ttu-id="8cc94-138">**以下相关集绑定到接收操作**</span><span class="sxs-lookup"><span data-stu-id="8cc94-138">**Following Correlation Sets bound to a Receive action**</span></span>  
  
     <span data-ttu-id="8cc94-139">绑定到接收操作的沿用相关集定义文档必须包含以便接收的一组属性和值。</span><span class="sxs-lookup"><span data-stu-id="8cc94-139">Following correlation sets bound to a receive action define the set of properties and values that the document must contain to be received.</span></span>  <span data-ttu-id="8cc94-140">具有沿用相关集的接收操作接受包含来自以前初始化的相关集的属性的文档。</span><span class="sxs-lookup"><span data-stu-id="8cc94-140">Receive actions with following correlation sets accept documents that contain properties from a previously initialized correlation set.</span></span>  
  
-   <span data-ttu-id="8cc94-141">**以下相关集绑定到的发送操作**</span><span class="sxs-lookup"><span data-stu-id="8cc94-141">**Following Correlation Sets bound to a Send action**</span></span>  
  
     <span data-ttu-id="8cc94-142">绑定到发送操作的沿用相关集规定在出站文档中升级相关集中的属性组。</span><span class="sxs-lookup"><span data-stu-id="8cc94-142">Following correlation sets bound to a send action dictate that the set of properties in the correlation set are promoted in the outbound document.</span></span>  
  
## <a name="inspecting-correlation-sets"></a><span data-ttu-id="8cc94-143">检查相关集</span><span class="sxs-lookup"><span data-stu-id="8cc94-143">Inspecting Correlation Sets</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8cc94-144">提供用于检查关联集。</span><span class="sxs-lookup"><span data-stu-id="8cc94-144"> provides the ability to inspect correlation sets.</span></span> <span data-ttu-id="8cc94-145">您可以使用如下代码检查表达式形状中的相关集：</span><span class="sxs-lookup"><span data-stu-id="8cc94-145">You can inspect a correlation set in an Expression Shape using code similar to the following:</span></span>  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 <span data-ttu-id="8cc94-146">上面的示例假设你已创建一个名为变量**MsgLen**类型的**System.Int16** ，并且您的业务流程中包含相关设置命名**Correlation_1**.</span><span class="sxs-lookup"><span data-stu-id="8cc94-146">The example above assumes that you have created a variable named **MsgLen** of type **System.Int16** and that your orchestration contains a correlation set named **Correlation_1**.</span></span> <span data-ttu-id="8cc94-147">如果您需要检查已由其他业务流程传递到某一业务流程的相关的值，则能够检查相关集可能就会很有用。</span><span class="sxs-lookup"><span data-stu-id="8cc94-147">The ability to inspect correlation sets may be useful if you need to inspect the value of a correlation that was passed to an orchestration by another orchestration.</span></span>  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a><span data-ttu-id="8cc94-148">将相关集作为参数传递到业务流程</span><span class="sxs-lookup"><span data-stu-id="8cc94-148">Passing Correlation Sets as Parameters to Orchestrations</span></span>  
 <span data-ttu-id="8cc94-149">你可以将传递作为相关性*中*向其他业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="8cc94-149">You can pass correlations as *in* parameters to other orchestrations.</span></span>