---
title: "在创建和使用架构 TIBCO |Microsoft 文档"
description: "使用 BizTalk 编辑器创建架构的 BizTalk Adapter TIBCO 企业消息服务，并为 BizTalk Server 设置在架构中的目标命名空间"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707067ed0c48abb62d567098cd472b59bad302b0
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="create-and-use-tibco-schemas"></a><span data-ttu-id="61985-103">创建和使用 TIBCO 架构</span><span class="sxs-lookup"><span data-stu-id="61985-103">Create and use TIBCO schemas</span></span>

## <a name="overview"></a><span data-ttu-id="61985-104">概述</span><span class="sxs-lookup"><span data-stu-id="61985-104">Overview</span></span>
<span data-ttu-id="61985-105">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器使用通过 Visual Studio 中的 XML 编辑器或 BizTalk Server 编辑器创建的架构（仅当在业务流程中使用适配器时）。</span><span class="sxs-lookup"><span data-stu-id="61985-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="61985-106">此架构描述您期望的信息类型。</span><span class="sxs-lookup"><span data-stu-id="61985-106">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="61985-107">本主题包含有关发送和接收处理程序的信息。</span><span class="sxs-lookup"><span data-stu-id="61985-107">This topic contains information for both a send and a receive handler.</span></span>  
  
<span data-ttu-id="61985-108">为与用于 TIBCO Enterprise Message Service 的 BizTalk 适配器一起使用而创建的架构必须有目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="61985-108">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="61985-109">BizTalk Server 需要此目标命名空间是因为，它是将给定消息实例与给定业务流程相关联的关键。</span><span class="sxs-lookup"><span data-stu-id="61985-109">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="61985-110">换言之，业务流程订阅有特定目标命名空间的任何消息，并且具有该目标命名空间的传入 XML 消息将提供给订阅该消息的每个业务流程。</span><span class="sxs-lookup"><span data-stu-id="61985-110">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="61985-111">如果 XML 文档架构没有目标命名空间，BizTalk Server 将使用根元素的名称作为关键。</span><span class="sxs-lookup"><span data-stu-id="61985-111">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  

<span data-ttu-id="61985-112">以下步骤显示如何生成架构，以及如何设置的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="61985-112">The following steps show how to generate a schema, and how to set the target namespace.</span></span>  
  
## <a name="generate-a-schema"></a><span data-ttu-id="61985-113">生成架构</span><span class="sxs-lookup"><span data-stu-id="61985-113">Generate a Schema</span></span>    
 
1.  <span data-ttu-id="61985-114">在 BizTalk 编辑器中，打开您的项目。</span><span class="sxs-lookup"><span data-stu-id="61985-114">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="61985-115">在解决方案资源管理器右上角中，选择**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="61985-115">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="61985-116">在**模板**窗格中，选择**生成架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="61985-116">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="61985-117">在**生成架构**对话框中，在**文档类型**列表中，选择**格式正确 XML**。</span><span class="sxs-lookup"><span data-stu-id="61985-117">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="61985-118">单击**浏览**以找到你要为其生成架构，并依次输入的文件**确定**。</span><span class="sxs-lookup"><span data-stu-id="61985-118">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
<span data-ttu-id="61985-119">接下来，设置的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="61985-119">Next, set the target namespace.</span></span>  
  
## <a name="set-the-target-namespace"></a><span data-ttu-id="61985-120">设置的目标命名空间</span><span class="sxs-lookup"><span data-stu-id="61985-120">Set the target namespace</span></span>  
  
1.  <span data-ttu-id="61985-121">在 BizTalk 编辑器中，打开架构文件，右键单击**\<架构 >**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="61985-121">In BizTalk Editor, open your schema file, right-click **\<schema>**, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="61985-122">在**属性**窗格中，找到**Namespace**字段并键入一个名称，例如， `testNameSpace`。</span><span class="sxs-lookup"><span data-stu-id="61985-122">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
 <span data-ttu-id="61985-123">然后，可以使用消息继续您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="61985-123">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="61985-124">选择消息时，BizTalk Server 会查找使用相应架构（具有设置的目标命名空间）的业务流程，然后开始业务流程进程。</span><span class="sxs-lookup"><span data-stu-id="61985-124">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61985-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61985-125">See Also</span></span>  
 [<span data-ttu-id="61985-126">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="61985-126">Developing Applications</span></span>](../core/developing-applications5.md)