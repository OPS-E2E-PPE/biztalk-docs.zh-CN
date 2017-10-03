---
title: "步骤 5： 升级架构属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9000b0466c8c0fc8d466f8174bc0e900a93bf392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-promote-schema-properties"></a><span data-ttu-id="dce8b-102">步骤 5： 升级架构中的属性</span><span class="sxs-lookup"><span data-stu-id="dce8b-102">Step 5: Promote Schema Properties</span></span>
<span data-ttu-id="dce8b-103">在此步骤中，升级架构中的属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务流程可以引用在后续步骤中创建这些属性值。</span><span class="sxs-lookup"><span data-stu-id="dce8b-103">In this step, you promote schema properties so that a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration can reference those property values that you create in later steps.</span></span> <span data-ttu-id="dce8b-104">升级是一种机制，用于引用消息实例内的某个特定值，并使其能够[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组件，例如业务流程或基于内容的路由目的。</span><span class="sxs-lookup"><span data-stu-id="dce8b-104">Promotion is a mechanism that you use to reference a specific value within a message instance and make it accessible to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] components such as orchestration or for content-based routing purposes.</span></span> <span data-ttu-id="dce8b-105">此外，已提升的属性是可见的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]IntelliSense 中的表达式编辑器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dce8b-105">Additionally, a promoted property is visible by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] IntelliSense in the Expression Editor of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="dce8b-106">审核和日志记录功能，使用 BizTalk 运行状况和活动跟踪 (HAT) 工具可以跟踪仅提升的架构属性。</span><span class="sxs-lookup"><span data-stu-id="dce8b-106"> auditing and logging functionality with the BizTalk Health and Activity Tracking (HAT) tool can track only promoted schema properties.</span></span>  
  
### <a name="to-promote-schema-properties"></a><span data-ttu-id="dce8b-107">若要升级架构中的属性</span><span class="sxs-lookup"><span data-stu-id="dce8b-107">To promote schema properties</span></span>  
  
1.  <span data-ttu-id="dce8b-108">在解决方案资源管理器下**BTAHL7 项目**，双击**DoorBell.xsd**节点以打开该架构。</span><span class="sxs-lookup"><span data-stu-id="dce8b-108">In Solution Explorer, under **BTAHL7 Project**, double-click the **DoorBell.xsd** node to open the schema.</span></span>  
  
2.  <span data-ttu-id="dce8b-109">右键单击**FirstName**字段元素中，依次指向**Promote**，然后单击**快速升级**。</span><span class="sxs-lookup"><span data-stu-id="dce8b-109">Right-click the **FirstName** field element, point to **Promote**, and then click **Quick Promotion**.</span></span>  
  
3.  <span data-ttu-id="dce8b-110">单击**确定**属性架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="dce8b-110">Click **OK** to add the property schema to the project.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="dce8b-111">添加的图标橙色圆圈**FirstName**元素，，该值指示元素已被提升。</span><span class="sxs-lookup"><span data-stu-id="dce8b-111"> adds an orange circle to the icon for the **FirstName** element, indicating that the element has been promoted.</span></span>  
  
4.  <span data-ttu-id="dce8b-112">重复上述步骤以提升的以下字段元素：</span><span class="sxs-lookup"><span data-stu-id="dce8b-112">Repeat these steps to promote the following field elements:</span></span>  
  
    -   <span data-ttu-id="dce8b-113">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="dce8b-113">**MiddleName**</span></span>  
  
    -   <span data-ttu-id="dce8b-114">**LastName**</span><span class="sxs-lookup"><span data-stu-id="dce8b-114">**LastName**</span></span>  
  
    -   <span data-ttu-id="dce8b-115">**SSN**</span><span class="sxs-lookup"><span data-stu-id="dce8b-115">**SSN**</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="dce8b-116">务必要注意如社会保障号 (SSN) 会导致该升级一个患者 ID (PID)[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]来跟踪该属性用于通过系统每个入站消息。</span><span class="sxs-lookup"><span data-stu-id="dce8b-116">It is important to note that promoting a patient ID (PID) such as a social security number (SSN) causes [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to track that property for every inbound message through the system.</span></span> <span data-ttu-id="dce8b-117">这种情况下的副作用是消息跟踪数据库将患者 Ssn 的副本。</span><span class="sxs-lookup"><span data-stu-id="dce8b-117">The side effect of this situation is that the message-tracking database keeps a copy of patient SSNs.</span></span> <span data-ttu-id="dce8b-118">这可能会造成重大的安全问题。</span><span class="sxs-lookup"><span data-stu-id="dce8b-118">This can create a significant security issue.</span></span> <span data-ttu-id="dce8b-119">你必须保护小心地使用此数据存储，或者可以完全避免 PID 数据在升级。</span><span class="sxs-lookup"><span data-stu-id="dce8b-119">You must either protect this data store with extreme care or avoid the promotion of PID data completely.</span></span>  
  
     <span data-ttu-id="dce8b-120">有关跟踪升级的架构元素所基于的文档的详细信息，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助有关运行状况和活动跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="dce8b-120">For more information about tracking documents based on the schema elements that you promoted, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help for information on Health and Activity Tracking.</span></span>  
  
 <span data-ttu-id="dce8b-121">继续执行[步骤 6： 验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="dce8b-121">Proceed to [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce8b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dce8b-122">See Also</span></span>  
 [<span data-ttu-id="dce8b-123">消息扩充教程</span><span class="sxs-lookup"><span data-stu-id="dce8b-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)