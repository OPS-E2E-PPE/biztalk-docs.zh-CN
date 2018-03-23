---
title: 使用 BizTalk 服务器项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a><span data-ttu-id="84d4d-102">使用 BizTalk 服务器项目中的 WCF LOB 适配器 SDK 适配器</span><span class="sxs-lookup"><span data-stu-id="84d4d-102">Consume a WCF LOB Adapter SDK adapter in a BizTalk Server project</span></span>
<span data-ttu-id="84d4d-103">本主题介绍如何使用适配器使用生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84d4d-103">This topic describes how to consume an adapter built using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84d4d-104">若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，必须安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]上相同的计算机承载工具[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84d4d-104">In order to use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you must install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tools on the same computer hosting [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="84d4d-105">使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="84d4d-105">Use the Consume Adapter Service Add-in</span></span>  
 
  
1.  <span data-ttu-id="84d4d-106">打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84d4d-106">Open your .NET application in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="84d4d-107">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]中**项目**窗格中，右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目，，然后选择**添加**&#124;**添加生成的项** &#124; **使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in the **Project** pane, right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project, and then choose **Add**&#124;**Add Generated Items** &#124; **Consume Adapter Service**.</span></span>  
  
3.  <span data-ttu-id="84d4d-108">在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]屏幕上，选择适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="84d4d-108">In the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] screen, select an adapter binding.</span></span>  
  
4.  <span data-ttu-id="84d4d-109">单击**配置**以配置所选的适配器绑定的连接 URI 并提供任何凭据、 URI 属性和绑定属性。</span><span class="sxs-lookup"><span data-stu-id="84d4d-109">Click **Configure** to configure the connection URI for the selected adapter binding and to provide any credentials, URI properties, and binding properties.</span></span> <span data-ttu-id="84d4d-110">实际要求将因所选的适配器绑定上。</span><span class="sxs-lookup"><span data-stu-id="84d4d-110">Actual requirements will vary based on the selected adapter binding.</span></span>  
  
5.  <span data-ttu-id="84d4d-111">单击**确定**配置 URI 时。</span><span class="sxs-lookup"><span data-stu-id="84d4d-111">Click **OK** when you have configured the URI.</span></span>  
  
6.  <span data-ttu-id="84d4d-112">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-112">Click **Connect**.</span></span> <span data-ttu-id="84d4d-113">连接 URI 是否有效并且接受客户端凭据 （如果有），**类别**窗格中应使用的类别和操作提供的适配器来填充。</span><span class="sxs-lookup"><span data-stu-id="84d4d-113">If the connection URI is valid and client credentials (if any) are accepted, the **Category** pane should be populated with the categories and operations provided by the adapter.</span></span>  
  
7.  <span data-ttu-id="84d4d-114">如果适配器支持搜索，搜索字段将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="84d4d-114">If the adapter support search, the search field will be active.</span></span> <span data-ttu-id="84d4d-115">否则为你可以按协定类型和筛选浏览通过单击中的节点的类型和操作**类别**窗格。</span><span class="sxs-lookup"><span data-stu-id="84d4d-115">Otherwise, you can filter by contract type and explore types and operations by clicking nodes in the **Category** pane.</span></span>  
  
8.  <span data-ttu-id="84d4d-116">单击**确定**生成代理项目。</span><span class="sxs-lookup"><span data-stu-id="84d4d-116">Click **OK** to generate the proxy artifacts.</span></span> <span data-ttu-id="84d4d-117">项目数而异的协定类型：</span><span class="sxs-lookup"><span data-stu-id="84d4d-117">The number of artifacts varies based on the contract type:</span></span>  
  
    |<span data-ttu-id="84d4d-118">协定类型</span><span class="sxs-lookup"><span data-stu-id="84d4d-118">Contract Type</span></span>|<span data-ttu-id="84d4d-119">项目</span><span class="sxs-lookup"><span data-stu-id="84d4d-119">Artifact</span></span>|<span data-ttu-id="84d4d-120">Description</span><span class="sxs-lookup"><span data-stu-id="84d4d-120">Description</span></span>||  
    |-------------------|--------------|-----------------|-|  
    |<span data-ttu-id="84d4d-121">出站</span><span class="sxs-lookup"><span data-stu-id="84d4d-121">Outbound</span></span>|<span data-ttu-id="84d4d-122">XML 架构</span><span class="sxs-lookup"><span data-stu-id="84d4d-122">XML Schemas</span></span>|<span data-ttu-id="84d4d-123">包含所选的类型和操作的架构。</span><span class="sxs-lookup"><span data-stu-id="84d4d-123">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="84d4d-124">出站</span><span class="sxs-lookup"><span data-stu-id="84d4d-124">Outbound</span></span>||<span data-ttu-id="84d4d-125">WCF 自定义发送端口绑定信息 XML</span><span class="sxs-lookup"><span data-stu-id="84d4d-125">WCF-Custom send port binding information XML</span></span>|<span data-ttu-id="84d4d-126">包含 WCF 自定义发送端口的配置 XML。</span><span class="sxs-lookup"><span data-stu-id="84d4d-126">Contains configuration XML for the WCF-Custom send port.</span></span>|  
    |<span data-ttu-id="84d4d-127">入站</span><span class="sxs-lookup"><span data-stu-id="84d4d-127">Inbound</span></span>|<span data-ttu-id="84d4d-128">XML 架构</span><span class="sxs-lookup"><span data-stu-id="84d4d-128">XML Schemas</span></span>|<span data-ttu-id="84d4d-129">包含所选的类型和操作的架构。</span><span class="sxs-lookup"><span data-stu-id="84d4d-129">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="84d4d-130">入站</span><span class="sxs-lookup"><span data-stu-id="84d4d-130">Inbound</span></span>||<span data-ttu-id="84d4d-131">WCF 自定义接收端口绑定信息 XML</span><span class="sxs-lookup"><span data-stu-id="84d4d-131">WCF-Custom receive port binding information XML</span></span>|<span data-ttu-id="84d4d-132">WCF 自定义接收端口，则包含配置 XML。</span><span class="sxs-lookup"><span data-stu-id="84d4d-132">Contains configuration XML for the WCF-Custom receive port.</span></span>|  
  
9. <span data-ttu-id="84d4d-133">你现在可以使用中的 XML 架构文件你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="84d4d-133">You can now use the XML Schema files in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="deploy-the-biztalk-server-project"></a><span data-ttu-id="84d4d-134">部署 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="84d4d-134">Deploy the BizTalk Server project</span></span>  
  
1.  <span data-ttu-id="84d4d-135">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-135">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="84d4d-136">导入要创建的物理端口的端口绑定 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="84d4d-136">Import the port binding XML file(s) to create the physical ports.</span></span> <span data-ttu-id="84d4d-137">右键单击受测应用程序**应用程序**组中，选择**导入绑定**，然后导航到并选择适当的端口绑定信息 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="84d4d-137">Right-click your application under the **Applications** group, select **Import Bindings**, and then navigate to and select the appropriate port binding information XML file(s).</span></span>  
  
3.  <span data-ttu-id="84d4d-138">在中定义的逻辑端口映射你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]到新创建的物理端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="84d4d-138">Map the logical ports defined in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestrations to the newly created physical ports.</span></span>  
  
4.  <span data-ttu-id="84d4d-139">单击**业务流程**下你的应用程序，右键单击业务流程，以登记，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-139">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
5.  <span data-ttu-id="84d4d-140">单击**业务流程**下你的应用程序，右键单击业务流程，以登记，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-140">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Start**.</span></span>  
  
6.  <span data-ttu-id="84d4d-141">右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="84d4d-141">Right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, and then click **Start**.</span></span>  
  
## <a name="generate-multiple-schemas"></a><span data-ttu-id="84d4d-142">生成多个架构</span><span class="sxs-lookup"><span data-stu-id="84d4d-142">Generate Multiple Schemas</span></span>  
 <span data-ttu-id="84d4d-143">如果使用使用适配器服务向导来生成多个架构，可能导致编译失败的架构中与一个或多个元素的重复[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="84d4d-143">If you use the Consume Adapter Service Wizard to generate multiple schemas, one or more elements may be duplicated in the schemas resulting in compilation failure for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="84d4d-144">你可以通过选择来避免这**生成唯一的架构类型**复选框以确保与唯一的命名空间，将生成的架构类型。</span><span class="sxs-lookup"><span data-stu-id="84d4d-144">You can avoid this by selecting the **Generate Unique Schema Type** check box to ensure that schema types are generated with unique namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d4d-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84d4d-145">See Also</span></span>  
 [<span data-ttu-id="84d4d-146">使用使用 WCF LOB 适配器 SDK 创建的适配器</span><span class="sxs-lookup"><span data-stu-id="84d4d-146">Consume an adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)