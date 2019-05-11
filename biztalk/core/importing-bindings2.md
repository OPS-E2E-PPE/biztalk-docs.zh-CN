---
title: 导入 Bindings2 |Microsoft Docs
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
ms.openlocfilehash: fab3b7677336a2d10daf365d7bf58d3c90aa9f35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382531"
---
# <a name="importing-bindings"></a><span data-ttu-id="ce89e-102">导入绑定</span><span class="sxs-lookup"><span data-stu-id="ce89e-102">Importing Bindings</span></span>
<span data-ttu-id="ce89e-103">在本部分中的主题介绍如何绑定导入到 BizTalk 组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce89e-103">The topics in this section describe how to import bindings into a BizTalk group or application.</span></span>  

 <span data-ttu-id="ce89e-104">在导入绑定，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="ce89e-104">When importing bindings, bear in mind the following important points:</span></span>  

- <span data-ttu-id="ce89e-105">**将覆盖现有绑定。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-105">**Existing bindings will be overwritten.**</span></span> <span data-ttu-id="ce89e-106">如果您导入的绑定具有与现有绑定相同的名称，现有绑定将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="ce89e-106">If the bindings that you import have the same name as existing bindings, the existing bindings are overwritten.</span></span> <span data-ttu-id="ce89e-107">此外，如果绑定文件包含参与方和别名，参与方和应用程序中已存在具有相同名称的别名的任何绑定将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="ce89e-107">In addition, if the binding file contains parties and aliases, any bindings for parties and aliases of the same name that already exist in the application are overwritten.</span></span>  

- <span data-ttu-id="ce89e-108">**在组中的所有绑定必须都是唯一的。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-108">**All bindings in a group must be unique.**</span></span> <span data-ttu-id="ce89e-109">如果绑定具有相同的名称，一个要导入已存在的组中，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-109">If a binding having the same name as one you are importing already exists in the group, the import operation will fail.</span></span>  

- <span data-ttu-id="ce89e-110">**必须重新配置密码。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-110">**You must reconfigure passwords.**</span></span> <span data-ttu-id="ce89e-111">出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。</span><span class="sxs-lookup"><span data-stu-id="ce89e-111">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="ce89e-112">导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。</span><span class="sxs-lookup"><span data-stu-id="ce89e-112">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="ce89e-113">发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。</span><span class="sxs-lookup"><span data-stu-id="ce89e-113">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="ce89e-114">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="ce89e-114">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="ce89e-115">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ce89e-115">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

- <span data-ttu-id="ce89e-116">**主机组中必须存在。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-116">**The host must exist in the group.**</span></span> <span data-ttu-id="ce89e-117">在其中绑定将导入和主机的信任级别必须匹配在 BizTalk 组中必须存在对应的绑定中指定的主机的主机。</span><span class="sxs-lookup"><span data-stu-id="ce89e-117">A host corresponding to the host specified in the bindings must already exist in the BizTalk group into which the bindings are imported and the host trust level must match.</span></span> <span data-ttu-id="ce89e-118">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-118">Otherwise, the import operation will fail.</span></span>  

- <span data-ttu-id="ce89e-119">**绑定导入行为取决于绑定的源。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-119">**Binding import behavior depends on the source of the bindings.**</span></span> <span data-ttu-id="ce89e-120">绑定可能已从程序集、 应用程序或组导出。</span><span class="sxs-lookup"><span data-stu-id="ce89e-120">The bindings may have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="ce89e-121">具体取决于从绑定的导出，导入操作可能具有不同的效果下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="ce89e-121">Depending on from where the bindings were exported, the import operation may have different effects, as shown in the following table.</span></span>  


  |        <span data-ttu-id="ce89e-122">绑定源</span><span class="sxs-lookup"><span data-stu-id="ce89e-122">Origin of the bindings</span></span>         |                                                                        <span data-ttu-id="ce89e-123">导入到应用程序</span><span class="sxs-lookup"><span data-stu-id="ce89e-123">Importing into an application</span></span>                                                                        |                                                                                                     <span data-ttu-id="ce89e-124">导入到组</span><span class="sxs-lookup"><span data-stu-id="ce89e-124">Importing into a group</span></span>                                                                                                      |
  |---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  <span data-ttu-id="ce89e-125">从程序集导出的绑定</span><span class="sxs-lookup"><span data-stu-id="ce89e-125">Bindings exported from an assembly</span></span>   | <span data-ttu-id="ce89e-126">指定应用程序中的必须包含与从中导出绑定文件的程序集同名的程序集。</span><span class="sxs-lookup"><span data-stu-id="ce89e-126">The specified application in must contain an assembly having the same name as the assembly from which the binding file was exported.</span></span> <span data-ttu-id="ce89e-127">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-127">Otherwise, the import operation fails.</span></span> |                        <span data-ttu-id="ce89e-128">组必须包含程序集和具有相同名称的程序集和从中导出绑定文件的应用程序作为应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce89e-128">The group must contain an assembly and an application having the same name as the assembly and application from which the binding file was exported.</span></span> <span data-ttu-id="ce89e-129">否则，导入将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-129">Otherwise, the import fails.</span></span>                        |
  | <span data-ttu-id="ce89e-130">从应用程序导出的绑定</span><span class="sxs-lookup"><span data-stu-id="ce89e-130">Bindings exported from an application</span></span> |            <span data-ttu-id="ce89e-131">从中导出绑定文件的应用程序必须具有与指定的应用程序相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ce89e-131">The application from which the binding file was exported must have the same name as the specified application.</span></span> <span data-ttu-id="ce89e-132">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-132">Otherwise, the import operation fails.</span></span>            |                <span data-ttu-id="ce89e-133">从中导出绑定文件的应用程序必须在其中导入绑定在组中具有与应用程序相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ce89e-133">The application from which the binding file was exported must have the same name as an application in the group into which you are importing the bindings.</span></span> <span data-ttu-id="ce89e-134">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-134">Otherwise, the import operation fails.</span></span>                |
  |    <span data-ttu-id="ce89e-135">从组导出的绑定</span><span class="sxs-lookup"><span data-stu-id="ce89e-135">Bindings exported from a group</span></span>     | <span data-ttu-id="ce89e-136">从中导出绑定文件的组必须包含具有指定的应用程序同名的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce89e-136">The group from which the binding file was exported must include an application that has the same name as the specified application.</span></span> <span data-ttu-id="ce89e-137">否则，导入操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ce89e-137">Otherwise, the import operation fails.</span></span>  | <span data-ttu-id="ce89e-138">绑定将导入对应的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce89e-138">Bindings are imported for corresponding applications.</span></span> <span data-ttu-id="ce89e-139">换而言之，从中导出绑定的组中的应用程序的绑定将导入到当前组中具有相同名称的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce89e-139">In other words, the bindings of an application in the group from which bindings were exported are imported into an application having the same name in the current group.</span></span> |


- <span data-ttu-id="ce89e-140">**适配器的 Name 属性可能不正确。**</span><span class="sxs-lookup"><span data-stu-id="ce89e-140">**The Name attribute for an adapter may be incorrect.**</span></span> <span data-ttu-id="ce89e-141">如果绑定文件包括适配器的设置，请验证绑定文件中 TransportType 元素的 Name 属性是否为适配器在 BizTalk Server 管理控制台中配置相同 (在平台设置下 > 适配器)。</span><span class="sxs-lookup"><span data-stu-id="ce89e-141">If the binding file includes settings for an adapter, verify that the Name attribute of the TransportType element in the binding file is the same as that configured for the adapter in the BizTalk Server Administration console (under Platform Settings > Adapters).</span></span>  

   <span data-ttu-id="ce89e-142">具体而言，应验证这种情况，导入中的绑定时[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ce89e-142">In particular, you should verify that this is the case when importing bindings from [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="ce89e-143">某些传输方式，这可能是一个问题是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce89e-143">Some transports for which this may be an issue are as follows:</span></span>  

  -   <span data-ttu-id="ce89e-144">MQS</span><span class="sxs-lookup"><span data-stu-id="ce89e-144">MQS</span></span>  

  -   <span data-ttu-id="ce89e-145">MSMQ</span><span class="sxs-lookup"><span data-stu-id="ce89e-145">MSMQ</span></span>  

  -   <span data-ttu-id="ce89e-146">POP3</span><span class="sxs-lookup"><span data-stu-id="ce89e-146">POP3</span></span>  

  -   <span data-ttu-id="ce89e-147">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="ce89e-147">Windows SharePoint Services</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="ce89e-148">本节内容</span><span class="sxs-lookup"><span data-stu-id="ce89e-148">In This Section</span></span>  

-   [<span data-ttu-id="ce89e-149">如何将绑定导入 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="ce89e-149">How to Import Bindings into a BizTalk Group</span></span>](../core/how-to-import-bindings-into-a-biztalk-group.md)  

-   [<span data-ttu-id="ce89e-150">如何将绑定导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ce89e-150">How to Import Bindings into a BizTalk Application</span></span>](../core/how-to-import-bindings-into-a-biztalk-application.md)  

-   [<span data-ttu-id="ce89e-151">如何导入 EDI-AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="ce89e-151">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)