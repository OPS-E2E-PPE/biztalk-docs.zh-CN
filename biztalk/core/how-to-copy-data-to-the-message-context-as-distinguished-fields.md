---
title: "如何将数据复制到与消息的上下文可分辨字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a><span data-ttu-id="065da-102">如何将数据复制到可分辨的字段的消息上下文</span><span class="sxs-lookup"><span data-stu-id="065da-102">How to Copy Data to the Message Context as Distinguished Fields</span></span>
<span data-ttu-id="065da-103">本主题提供有关将提升为属性的分步说明**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="065da-103">This topic provides step-by-step instructions for promoting a property as a **Distinguished Field**.</span></span>  
  
 <span data-ttu-id="065da-104">你可以选择**可分辨字段**通过升级**属性字段**出于以下原因升级：</span><span class="sxs-lookup"><span data-stu-id="065da-104">You might choose **Distinguished Field** promotion over **Property Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="065da-105">**属性字段**值限于 255 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="065da-105">**Property Field** values are limited to 255 characters in length.</span></span>  
  
-   <span data-ttu-id="065da-106">**属性字段**值存储在数据库中，并因此具有多个开销低于**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="065da-106">**Property Field** values are stored in a database, and therefore have more overhead than **Distinguished Fields**.</span></span> <span data-ttu-id="065da-107">**可分辨字段**不需要任何其他存储; 它们是实质上是别名**XPath**，从而允许业务流程更轻松地访问直接从消息的相关值。</span><span class="sxs-lookup"><span data-stu-id="065da-107">**Distinguished Fields** do not require any additional storage; they are essentially an alias for an **XPath**, thereby allowing orchestrations to more easily access the relevant values directly from the message.</span></span>  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a><span data-ttu-id="065da-108">将属性升级为可分辨字段</span><span class="sxs-lookup"><span data-stu-id="065da-108">To promote a property as a Distinguished Field</span></span>  
  
1.  <span data-ttu-id="065da-109">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="065da-109">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Distinguished Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="065da-110">记录节点永远不会被提升为**可分辨字段**，不管它们包含的内容类型。</span><span class="sxs-lookup"><span data-stu-id="065da-110">Record nodes can never be promoted as **Distinguished Fields**, regardless of the type of content they contain.</span></span>  
  
2.  <span data-ttu-id="065da-111">右键单击所选的节点，单击**Promote**，然后单击**显示提升**。</span><span class="sxs-lookup"><span data-stu-id="065da-111">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="065da-112">**升级属性**对话框随即打开与所选的节点显示的所选对话框左侧的架构树中。</span><span class="sxs-lookup"><span data-stu-id="065da-112">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
3.  <span data-ttu-id="065da-113">在**升级属性**对话框中，选择**可分辨字段**选项卡。</span><span class="sxs-lookup"><span data-stu-id="065da-113">In the **Promote Properties** dialog box, select the **Distinguished Fields** tab.</span></span>  
  
4.  <span data-ttu-id="065da-114">与节点可升级的左侧的架构树中仍选定**升级属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="065da-114">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="065da-115">如果允许，所选的节点添加到列表上**可分辨字段**选项卡。如果不允许，消息框将提供说明。</span><span class="sxs-lookup"><span data-stu-id="065da-115">If allowed, the selected node is added to the list on the **Distinguished Fields** tab. If not allowed, a message box provides an explanation.</span></span>  
  
5.  <span data-ttu-id="065da-116">你可以在对话框中，单击左侧架构树中选择更多节点升级**添加**后每个所选内容。</span><span class="sxs-lookup"><span data-stu-id="065da-116">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** after each selection.</span></span>  
  
6.  <span data-ttu-id="065da-117">完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="065da-117">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="065da-118">选择进行升级的节点现**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="065da-118">The nodes that you selected to promote are now **Distinguished Fields**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065da-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="065da-119">See Also</span></span>  
 <span data-ttu-id="065da-120">[提升属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="065da-120">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="065da-121">[如何创建属性架构](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="065da-121">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="065da-122">使用与控件消息处理的消息内容的方法</span><span class="sxs-lookup"><span data-stu-id="065da-122">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)