---
title: 导入 Bindings2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, requirements
- importing, bindings
- bindings, importing
ms.assetid: 9e10bc04-aba8-430a-b8fd-de9399d54f88
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f2c92d5469f88494c77ad062d97c53768572a5b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006126"
---
# <a name="importing-bindings"></a><span data-ttu-id="1ab34-102">导入绑定</span><span class="sxs-lookup"><span data-stu-id="1ab34-102">Importing Bindings</span></span>
<span data-ttu-id="1ab34-103">本部分中的主题介绍如何将绑定导入到 BizTalk 组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ab34-103">The topics in this section describe how to import bindings into a BizTalk group or application.</span></span>  
  
 <span data-ttu-id="1ab34-104">在导入的绑定，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="1ab34-104">When importing bindings, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="1ab34-105">**将覆盖现有绑定。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-105">**Existing bindings will be overwritten.**</span></span> <span data-ttu-id="1ab34-106">如果导入的绑定与现有的绑定同名，则现有的绑定将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="1ab34-106">If the bindings that you import have the same name as existing bindings, the existing bindings are overwritten.</span></span> <span data-ttu-id="1ab34-107">此外，如果绑定文件包含参与方和别名，则应用程序中已存在的同名的参与方和别名的任何绑定将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="1ab34-107">In addition, if the binding file contains parties and aliases, any bindings for parties and aliases of the same name that already exist in the application are overwritten.</span></span>  
  
-   <span data-ttu-id="1ab34-108">**在组中的所有绑定都必须都是唯一的。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-108">**All bindings in a group must be unique.**</span></span> <span data-ttu-id="1ab34-109">如果与您正在导入的绑定同名的绑定在组中已存在，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-109">If a binding having the same name as one you are importing already exists in the group, the import operation will fail.</span></span>  
  
-   <span data-ttu-id="1ab34-110">**你必须重新配置密码。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-110">**You must reconfigure passwords.**</span></span> <span data-ttu-id="1ab34-111">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab34-111">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="1ab34-112">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="1ab34-112">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="1ab34-113">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="1ab34-113">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="1ab34-114">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab34-114">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="1ab34-115">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab34-115">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="1ab34-116">**主机组中必须存在。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-116">**The host must exist in the group.**</span></span> <span data-ttu-id="1ab34-117">要将绑定导入其中的 BizTalk 组中必须存在与绑定文件中指定的主机相对应的主机，并且，主机的信任级别必须匹配。</span><span class="sxs-lookup"><span data-stu-id="1ab34-117">A host corresponding to the host specified in the bindings must already exist in the BizTalk group into which the bindings are imported and the host trust level must match.</span></span> <span data-ttu-id="1ab34-118">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-118">Otherwise, the import operation will fail.</span></span>  
  
-   <span data-ttu-id="1ab34-119">**绑定导入行为取决于绑定的源。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-119">**Binding import behavior depends on the source of the bindings.**</span></span> <span data-ttu-id="1ab34-120">绑定可能已从程序集、应用程序或组中导出。</span><span class="sxs-lookup"><span data-stu-id="1ab34-120">The bindings may have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="1ab34-121">根据绑定的导出位置，导入操作可能具有不同的作用，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="1ab34-121">Depending on from where the bindings were exported, the import operation may have different effects, as shown in the following table.</span></span>  
  
    |<span data-ttu-id="1ab34-122">绑定源</span><span class="sxs-lookup"><span data-stu-id="1ab34-122">Origin of the bindings</span></span>|<span data-ttu-id="1ab34-123">导入到应用程序</span><span class="sxs-lookup"><span data-stu-id="1ab34-123">Importing into an application</span></span>|<span data-ttu-id="1ab34-124">导入到组</span><span class="sxs-lookup"><span data-stu-id="1ab34-124">Importing into a group</span></span>|  
    |----------------------------|-----------------------------------|----------------------------|  
    |<span data-ttu-id="1ab34-125">从程序集导出的绑定</span><span class="sxs-lookup"><span data-stu-id="1ab34-125">Bindings exported from an assembly</span></span>|<span data-ttu-id="1ab34-126">指定的应用程序必须包含与从中导出绑定文件的程序集同名的程序集。</span><span class="sxs-lookup"><span data-stu-id="1ab34-126">The specified application in must contain an assembly having the same name as the assembly from which the binding file was exported.</span></span> <span data-ttu-id="1ab34-127">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-127">Otherwise, the import operation fails.</span></span>|<span data-ttu-id="1ab34-128">组必须包含与从中导出绑定文件的程序集和应用程序同名的程序集和应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ab34-128">The group must contain an assembly and an application having the same name as the assembly and application from which the binding file was exported.</span></span> <span data-ttu-id="1ab34-129">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-129">Otherwise, the import fails.</span></span>|  
    |<span data-ttu-id="1ab34-130">从应用程序导出的绑定</span><span class="sxs-lookup"><span data-stu-id="1ab34-130">Bindings exported from an application</span></span>|<span data-ttu-id="1ab34-131">从中导出绑定文件的应用程序必须与指定的应用程序同名。</span><span class="sxs-lookup"><span data-stu-id="1ab34-131">The application from which the binding file was exported must have the same name as the specified application.</span></span> <span data-ttu-id="1ab34-132">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-132">Otherwise, the import operation fails.</span></span>|<span data-ttu-id="1ab34-133">从中导出绑定文件的应用程序必须与要将绑定导入的组中的应用程序同名。</span><span class="sxs-lookup"><span data-stu-id="1ab34-133">The application from which the binding file was exported must have the same name as an application in the group into which you are importing the bindings.</span></span> <span data-ttu-id="1ab34-134">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-134">Otherwise, the import operation fails.</span></span>|  
    |<span data-ttu-id="1ab34-135">从组导出的绑定</span><span class="sxs-lookup"><span data-stu-id="1ab34-135">Bindings exported from a group</span></span>|<span data-ttu-id="1ab34-136">从中导出绑定文件的组必须包含与指定的应用程序同名的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ab34-136">The group from which the binding file was exported must include an application that has the same name as the specified application.</span></span> <span data-ttu-id="1ab34-137">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="1ab34-137">Otherwise, the import operation fails.</span></span>|<span data-ttu-id="1ab34-138">绑定将导入对应的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1ab34-138">Bindings are imported for corresponding applications.</span></span> <span data-ttu-id="1ab34-139">换言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中同名的应用程序内。</span><span class="sxs-lookup"><span data-stu-id="1ab34-139">In other words, the bindings of an application in the group from which bindings were exported are imported into an application having the same name in the current group.</span></span>|  
  
-   <span data-ttu-id="1ab34-140">**适配器的名称属性可能不正确。**</span><span class="sxs-lookup"><span data-stu-id="1ab34-140">**The Name attribute for an adapter may be incorrect.**</span></span> <span data-ttu-id="1ab34-141">如果绑定文件包括适配器的设置，请验证绑定文件中 TransportType 元素的 Name 属性与在 BizTalk Server 管理控制台中（在“平台设置”>“适配器”下）为该适配器配置的属性相同。</span><span class="sxs-lookup"><span data-stu-id="1ab34-141">If the binding file includes settings for an adapter, verify that the Name attribute of the TransportType element in the binding file is the same as that configured for the adapter in the BizTalk Server Administration console (under Platform Settings > Adapters).</span></span>  
  
     <span data-ttu-id="1ab34-142">具体而言，你应验证这种情况，在导入来自绑定[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1ab34-142">In particular, you should verify that this is the case when importing bindings from [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="1ab34-143">对于以下传输，这可能会是一个问题：</span><span class="sxs-lookup"><span data-stu-id="1ab34-143">Some transports for which this may be an issue are as follows:</span></span>  
  
    -   <span data-ttu-id="1ab34-144">MQS</span><span class="sxs-lookup"><span data-stu-id="1ab34-144">MQS</span></span>  
  
    -   <span data-ttu-id="1ab34-145">MSMQ</span><span class="sxs-lookup"><span data-stu-id="1ab34-145">MSMQ</span></span>  
  
    -   <span data-ttu-id="1ab34-146">POP3</span><span class="sxs-lookup"><span data-stu-id="1ab34-146">POP3</span></span>  
  
    -   <span data-ttu-id="1ab34-147">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="1ab34-147">Windows SharePoint Services</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ab34-148">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ab34-148">In This Section</span></span>  
  
-   [<span data-ttu-id="1ab34-149">如何将绑定导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="1ab34-149">How to Import Bindings into a BizTalk Group</span></span>](../core/how-to-import-bindings-into-a-biztalk-group.md)  
  
-   [<span data-ttu-id="1ab34-150">如何将绑定导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1ab34-150">How to Import Bindings into a BizTalk Application</span></span>](../core/how-to-import-bindings-into-a-biztalk-application.md)  
  
-   [<span data-ttu-id="1ab34-151">如何导入绑定 EDI AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="1ab34-151">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)