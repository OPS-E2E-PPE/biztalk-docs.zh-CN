---
title: "将权限分配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, assigning permissions
- security, user accounts
- document library, new messages
- document library, unparsed
- messages, document library
- privileges
- permissions
- unparsed document library
- security, permissions
ms.assetid: cee44240-aa00-4080-9e7f-728b2421102b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a980fde1a4aea5d2e741fa576e55e659c0835f9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assigning-rights"></a><span data-ttu-id="6621a-102">分配权限</span><span class="sxs-lookup"><span data-stu-id="6621a-102">Assigning Rights</span></span>
<span data-ttu-id="6621a-103">应在文档库，用于在前面的主题中创建每个站点组上授予以下权限：</span><span class="sxs-lookup"><span data-stu-id="6621a-103">The following permissions should be granted on the Document libraries for each site group created in the preceding topic:</span></span>  
  
|<span data-ttu-id="6621a-104">文档库</span><span class="sxs-lookup"><span data-stu-id="6621a-104">Document library</span></span>|<span data-ttu-id="6621a-105">站点组</span><span class="sxs-lookup"><span data-stu-id="6621a-105">Site groups</span></span>|<span data-ttu-id="6621a-106">要应用的自定义文档库的权限</span><span class="sxs-lookup"><span data-stu-id="6621a-106">Custom document library permissions to apply</span></span>|  
|----------------------|-----------------|--------------------------------------------------|  
|<span data-ttu-id="6621a-107">模板文档库</span><span class="sxs-lookup"><span data-stu-id="6621a-107">Templates document library</span></span>|<span data-ttu-id="6621a-108">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="6621a-108">Payments_Creators</span></span><br /><br /> <span data-ttu-id="6621a-109">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="6621a-109">Payments_Repairers</span></span><br /><br /> <span data-ttu-id="6621a-110">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="6621a-110">Payments_Approvers</span></span>|<span data-ttu-id="6621a-111">查看项</span><span class="sxs-lookup"><span data-stu-id="6621a-111">View items</span></span>|  
|<span data-ttu-id="6621a-112">未分析 （下面的详细信息）</span><span class="sxs-lookup"><span data-stu-id="6621a-112">Unparsed (details below)</span></span>|<span data-ttu-id="6621a-113">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="6621a-113">Payments_Repairers</span></span>|<span data-ttu-id="6621a-114">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-114">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="6621a-115">新 SWIFT MT 消息 （下面详细信息）</span><span class="sxs-lookup"><span data-stu-id="6621a-115">New SWIFT MT Messages (details below)</span></span>|<span data-ttu-id="6621a-116">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="6621a-116">Payments_Creators</span></span>|<span data-ttu-id="6621a-117">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-117">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="6621a-118">新 SWIFT MX 消息 （下面详细信息）</span><span class="sxs-lookup"><span data-stu-id="6621a-118">New SWIFT MX Messages (details below)</span></span>|<span data-ttu-id="6621a-119">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="6621a-119">Payments_Creators</span></span>|<span data-ttu-id="6621a-120">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-120">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="6621a-121">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="6621a-121">Payments_Repairers</span></span>|<span data-ttu-id="6621a-122">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="6621a-122">Payments_Repairers</span></span>|<span data-ttu-id="6621a-123">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-123">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="6621a-124">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="6621a-124">Payments_Approvers</span></span>|<span data-ttu-id="6621a-125">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="6621a-125">Payments_Approvers</span></span>|<span data-ttu-id="6621a-126">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-126">View, insert, edit, delete items</span></span>|  
|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="6621a-127">_Outbox</span><span class="sxs-lookup"><span data-stu-id="6621a-127">_Outbox</span></span>|<span data-ttu-id="6621a-128">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="6621a-128">Payments_Creators</span></span><br /><br /> <span data-ttu-id="6621a-129">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="6621a-129">Payments_Repairers</span></span><br /><br /> <span data-ttu-id="6621a-130">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="6621a-130">Payments_Approvers</span></span>|<span data-ttu-id="6621a-131">查看、 插入、 编辑、 删除项</span><span class="sxs-lookup"><span data-stu-id="6621a-131">View, insert, edit, delete items</span></span>|  
  
## <a name="unparsed-document-library"></a><span data-ttu-id="6621a-132">未分析的文档库</span><span class="sxs-lookup"><span data-stu-id="6621a-132">Unparsed Document Library</span></span>  
 <span data-ttu-id="6621a-133">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]失败以特殊方式分析的消息，处理消息修复过程。</span><span class="sxs-lookup"><span data-stu-id="6621a-133">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair process deals with messages that fail parsing in a special manner.</span></span> <span data-ttu-id="6621a-134">未分析的消息 （不能转换为 XML 的消息） 都路由到单一未分析的消息文档库中。</span><span class="sxs-lookup"><span data-stu-id="6621a-134">Unparsed messages (messages that cannot be translated into XML) are routed to a single unparsed message document library.</span></span> <span data-ttu-id="6621a-135">未分析的文档库应被限制以允许仅特定用户，而不是整个组，无法访问该文件夹。</span><span class="sxs-lookup"><span data-stu-id="6621a-135">The unparsed document library should be restricted to allow only specific people, rather than entire groups, to access the folder.</span></span> <span data-ttu-id="6621a-136">这将确保未分析的文件夹是尽可能安全。</span><span class="sxs-lookup"><span data-stu-id="6621a-136">This will ensure that the unparsed folder is as secure as possible.</span></span>  
  
 <span data-ttu-id="6621a-137">用户有权修复未分析的消息在 MMC 配置控制台中，定义的至少一个部门需要修复角色的权限，还需要在 NT 组中注册[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。</span><span class="sxs-lookup"><span data-stu-id="6621a-137">Users who have permissions to repair unparsed messages need permissions in the repair role for at least one department defined in the MMC configuration console, and also need to be enrolled in the NT Group [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Users Group.</span></span>  
  
## <a name="new-swift-mt-mx-messages-document-library"></a><span data-ttu-id="6621a-138">新 SWIFT MT / MX 消息文档库</span><span class="sxs-lookup"><span data-stu-id="6621a-138">New SWIFT MT/ MX Messages Document Library</span></span>  
 <span data-ttu-id="6621a-139">在部署 MRSR 网站时创建新 SWIFT MT 消息和新 SWIFT MX 消息文档库。</span><span class="sxs-lookup"><span data-stu-id="6621a-139">The New SWIFT MT Messages and New SWIFT MX Messages document libraries are created at the time of deploying the MRSR site.</span></span> <span data-ttu-id="6621a-140">新 SWIFT MT 消息和新 SWIFT MX 消息文档库中存储新 SWIFT XML 模板或"样本"消息。</span><span class="sxs-lookup"><span data-stu-id="6621a-140">The New SWIFT MT Messages and New SWIFT MX Messages document libraries store new SWIFT XML templates or "boilerplate" messages.</span></span> <span data-ttu-id="6621a-141">这些消息可用于创建新 SWIFT InfoPath XML 格式表示的消息。</span><span class="sxs-lookup"><span data-stu-id="6621a-141">You can use these messages to create new SWIFT messages represented in InfoPath XML format.</span></span> <span data-ttu-id="6621a-142">这些消息都上载到新 SWIFT MT 消息和新 SWIFT MX 消息文档库由用户通过单击文档库中的上载按钮。</span><span class="sxs-lookup"><span data-stu-id="6621a-142">These messages are uploaded into the New SWIFT MT Messages and New SWIFT MX Messages document libraries by the user by clicking on the Upload button in the document library.</span></span> <span data-ttu-id="6621a-143">你可以进一步分发新 SWIFT 消息模板以限制对指定的用户访问。</span><span class="sxs-lookup"><span data-stu-id="6621a-143">You can further distribute the New SWIFT Message templates to restrict access to specified users.</span></span> <span data-ttu-id="6621a-144">为此，首先要创建新的文档库中，，然后将复制所需的文档库的 XML 模板。</span><span class="sxs-lookup"><span data-stu-id="6621a-144">To do so you first create a new document library, and then copy the XML templates required for the document library.</span></span>  
  
 <span data-ttu-id="6621a-145">有关 FormPublish 工具的详细信息，请参阅[FormPublish 工具](http://msdn.microsoft.com/en-us/09a6ed31-5917-4776-9a5e-955af440cdac)工具部分中。</span><span class="sxs-lookup"><span data-stu-id="6621a-145">For more information about the FormPublish tool, see [FormPublish Tool](http://msdn.microsoft.com/en-us/09a6ed31-5917-4776-9a5e-955af440cdac) in the Tools section.</span></span>