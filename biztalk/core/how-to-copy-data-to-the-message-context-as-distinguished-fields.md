---
title: 如何将数据复制到消息上下文作为可分辨字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd5708fb972c21c84ae70f258c46e2d4cbcced9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340123"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a><span data-ttu-id="633cb-102">如何将数据复制到消息上下文作为可分辨字段</span><span class="sxs-lookup"><span data-stu-id="633cb-102">How to Copy Data to the Message Context as Distinguished Fields</span></span>
<span data-ttu-id="633cb-103">本主题提供有关将属性升级为的分步说明**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="633cb-103">This topic provides step-by-step instructions for promoting a property as a **Distinguished Field**.</span></span>  
  
 <span data-ttu-id="633cb-104">您可以选择**可分辨字段**通过升级**属性字段**出于以下原因升级：</span><span class="sxs-lookup"><span data-stu-id="633cb-104">You might choose **Distinguished Field** promotion over **Property Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="633cb-105">**属性字段**值被限制为 255 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="633cb-105">**Property Field** values are limited to 255 characters in length.</span></span>  
  
-   <span data-ttu-id="633cb-106">**属性字段**值存储在数据库中，并因此具有更多的开销比**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="633cb-106">**Property Field** values are stored in a database, and therefore have more overhead than **Distinguished Fields**.</span></span> <span data-ttu-id="633cb-107">**可分辨字段**不需要任何其他存储时，它们是实质上是别名**XPath**，从而允许业务流程更轻松地访问相关的值直接从消息。</span><span class="sxs-lookup"><span data-stu-id="633cb-107">**Distinguished Fields** do not require any additional storage; they are essentially an alias for an **XPath**, thereby allowing orchestrations to more easily access the relevant values directly from the message.</span></span>  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a><span data-ttu-id="633cb-108">若要将属性升级为可分辨字段</span><span class="sxs-lookup"><span data-stu-id="633cb-108">To promote a property as a Distinguished Field</span></span>  
  
1.  <span data-ttu-id="633cb-109">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="633cb-109">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Distinguished Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="633cb-110">记录节点永远无法升级为**可分辨字段**，无论它们包含的内容类型。</span><span class="sxs-lookup"><span data-stu-id="633cb-110">Record nodes can never be promoted as **Distinguished Fields**, regardless of the type of content they contain.</span></span>  
  
2.  <span data-ttu-id="633cb-111">右键单击所选的节点，单击**Promote**，然后单击**显示升级**。</span><span class="sxs-lookup"><span data-stu-id="633cb-111">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="633cb-112">**升级属性**对话框将打开与所选的节点显示为对话框的左侧的架构树中已选中。</span><span class="sxs-lookup"><span data-stu-id="633cb-112">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
3.  <span data-ttu-id="633cb-113">在中**升级属性**对话框中，选择**可分辨字段**选项卡。</span><span class="sxs-lookup"><span data-stu-id="633cb-113">In the **Promote Properties** dialog box, select the **Distinguished Fields** tab.</span></span>  
  
4.  <span data-ttu-id="633cb-114">与要升级在左侧和右侧的架构树中仍然处于选中状态的节点**升级属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="633cb-114">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="633cb-115">如果允许，选定的节点添加到列表上**可分辨字段**选项卡。如果不允许，消息框提供了说明。</span><span class="sxs-lookup"><span data-stu-id="633cb-115">If allowed, the selected node is added to the list on the **Distinguished Fields** tab. If not allowed, a message box provides an explanation.</span></span>  
  
5.  <span data-ttu-id="633cb-116">您可以选择升级的其他节点在架构树中的对话框中，单击左侧**添加**后每个所选内容。</span><span class="sxs-lookup"><span data-stu-id="633cb-116">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** after each selection.</span></span>  
  
6.  <span data-ttu-id="633cb-117">完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="633cb-117">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="633cb-118">现已选定要升级的节点**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="633cb-118">The nodes that you selected to promote are now **Distinguished Fields**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633cb-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="633cb-119">See Also</span></span>  
 <span data-ttu-id="633cb-120">[升级属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="633cb-120">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="633cb-121">[如何创建属性架构](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="633cb-121">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="633cb-122">使用消息内容控制消息处理的方法</span><span class="sxs-lookup"><span data-stu-id="633cb-122">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)