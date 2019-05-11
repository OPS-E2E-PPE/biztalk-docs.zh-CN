---
title: 使用 BizTalk Server 项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0ad9b2659ce20876807d894f99751eeb265e92e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363829"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a><span data-ttu-id="4c634-102">使用 BizTalk Server 项目中的 WCF LOB 适配器 SDK 适配器</span><span class="sxs-lookup"><span data-stu-id="4c634-102">Consume a WCF LOB Adapter SDK adapter in a BizTalk Server project</span></span>
<span data-ttu-id="4c634-103">本主题介绍如何使用使用构建适配器[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c634-103">This topic describes how to consume an adapter built using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  

> [!NOTE]
>  <span data-ttu-id="4c634-104">若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则必须安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]工具在同一计算机承载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c634-104">In order to use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you must install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tools on the same computer hosting [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  


## <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="4c634-105">使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="4c634-105">Use the Consume Adapter Service Add-in</span></span>  


1. <span data-ttu-id="4c634-106">打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c634-106">Open your .NET application in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="4c634-107">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，请在**项目**窗格中，右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目，，然后选择**添加**&#124;**添加生成的项** &#124; **使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="4c634-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in the **Project** pane, right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project, and then choose **Add**&#124;**Add Generated Items** &#124; **Consume Adapter Service**.</span></span>  

3. <span data-ttu-id="4c634-108">在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]屏幕上，选择一个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="4c634-108">In the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] screen, select an adapter binding.</span></span>  

4. <span data-ttu-id="4c634-109">单击**配置**，配置所选的适配器绑定的连接 URI，它提供任何凭据、 URI 属性和绑定属性。</span><span class="sxs-lookup"><span data-stu-id="4c634-109">Click **Configure** to configure the connection URI for the selected adapter binding and to provide any credentials, URI properties, and binding properties.</span></span> <span data-ttu-id="4c634-110">实际要求将因所选的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="4c634-110">Actual requirements will vary based on the selected adapter binding.</span></span>  

5. <span data-ttu-id="4c634-111">单击**确定**配置 URI 时。</span><span class="sxs-lookup"><span data-stu-id="4c634-111">Click **OK** when you have configured the URI.</span></span>  

6. <span data-ttu-id="4c634-112">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="4c634-112">Click **Connect**.</span></span> <span data-ttu-id="4c634-113">如果连接 URI 有效并且接受客户端凭据 （如果有），**类别**窗格应填充的类别和适配器提供的操作。</span><span class="sxs-lookup"><span data-stu-id="4c634-113">If the connection URI is valid and client credentials (if any) are accepted, the **Category** pane should be populated with the categories and operations provided by the adapter.</span></span>  

7. <span data-ttu-id="4c634-114">如果适配器支持搜索，搜索字段将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4c634-114">If the adapter support search, the search field will be active.</span></span> <span data-ttu-id="4c634-115">否则为可以按协定类型进行筛选，并通过单击中的节点浏览类型和操作**类别**窗格。</span><span class="sxs-lookup"><span data-stu-id="4c634-115">Otherwise, you can filter by contract type and explore types and operations by clicking nodes in the **Category** pane.</span></span>  

8. <span data-ttu-id="4c634-116">单击**确定**生成代理项目。</span><span class="sxs-lookup"><span data-stu-id="4c634-116">Click **OK** to generate the proxy artifacts.</span></span> <span data-ttu-id="4c634-117">根据协定类型的项目数而有所不同：</span><span class="sxs-lookup"><span data-stu-id="4c634-117">The number of artifacts varies based on the contract type:</span></span>  


   | <span data-ttu-id="4c634-118">协定类型</span><span class="sxs-lookup"><span data-stu-id="4c634-118">Contract Type</span></span> |  <span data-ttu-id="4c634-119">项目</span><span class="sxs-lookup"><span data-stu-id="4c634-119">Artifact</span></span>   |                         <span data-ttu-id="4c634-120">Description</span><span class="sxs-lookup"><span data-stu-id="4c634-120">Description</span></span>                         |                                                             |
   |---------------|-------------|-------------------------------------------------------------|-------------------------------------------------------------|
   |   <span data-ttu-id="4c634-121">出站</span><span class="sxs-lookup"><span data-stu-id="4c634-121">Outbound</span></span>    | <span data-ttu-id="4c634-122">XML 架构</span><span class="sxs-lookup"><span data-stu-id="4c634-122">XML Schemas</span></span> | <span data-ttu-id="4c634-123">包含所选的类型和操作的架构。</span><span class="sxs-lookup"><span data-stu-id="4c634-123">Contains the schemas for the selected types and operations.</span></span> |                                                             |
   |   <span data-ttu-id="4c634-124">出站</span><span class="sxs-lookup"><span data-stu-id="4c634-124">Outbound</span></span>    |             |        <span data-ttu-id="4c634-125">WCF 自定义发送端口的绑定信息 XML</span><span class="sxs-lookup"><span data-stu-id="4c634-125">WCF-Custom send port binding information XML</span></span>         |  <span data-ttu-id="4c634-126">包含 XML 配置 Wcf-custom 发送端口。</span><span class="sxs-lookup"><span data-stu-id="4c634-126">Contains configuration XML for the WCF-Custom send port.</span></span>   |
   |    <span data-ttu-id="4c634-127">入站</span><span class="sxs-lookup"><span data-stu-id="4c634-127">Inbound</span></span>    | <span data-ttu-id="4c634-128">XML 架构</span><span class="sxs-lookup"><span data-stu-id="4c634-128">XML Schemas</span></span> | <span data-ttu-id="4c634-129">包含所选的类型和操作的架构。</span><span class="sxs-lookup"><span data-stu-id="4c634-129">Contains the schemas for the selected types and operations.</span></span> |                                                             |
   |    <span data-ttu-id="4c634-130">入站</span><span class="sxs-lookup"><span data-stu-id="4c634-130">Inbound</span></span>    |             |       <span data-ttu-id="4c634-131">WCF 自定义接收端口的绑定信息 XML</span><span class="sxs-lookup"><span data-stu-id="4c634-131">WCF-Custom receive port binding information XML</span></span>       | <span data-ttu-id="4c634-132">包含配置 XML 为 WCF 自定义接收端口。</span><span class="sxs-lookup"><span data-stu-id="4c634-132">Contains configuration XML for the WCF-Custom receive port.</span></span> |


9. <span data-ttu-id="4c634-133">现在可以使用中的 XML 架构文件在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c634-133">You can now use the XML Schema files in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  

## <a name="deploy-the-biztalk-server-project"></a><span data-ttu-id="4c634-134">部署 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="4c634-134">Deploy the BizTalk Server project</span></span>  

1. <span data-ttu-id="4c634-135">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="4c634-135">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="4c634-136">导入要创建物理端口的端口绑定 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4c634-136">Import the port binding XML file(s) to create the physical ports.</span></span> <span data-ttu-id="4c634-137">右键单击受测应用程序**应用程序**组中，选择**导入绑定**，然后导航到并选择适当的端口绑定信息 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4c634-137">Right-click your application under the **Applications** group, select **Import Bindings**, and then navigate to and select the appropriate port binding information XML file(s).</span></span>  

3. <span data-ttu-id="4c634-138">映射中定义的逻辑端口在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]与新创建的物理端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="4c634-138">Map the logical ports defined in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestrations to the newly created physical ports.</span></span>  

4. <span data-ttu-id="4c634-139">单击**业务流程**在应用程序中，右键单击业务流程以登记，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="4c634-139">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  

5. <span data-ttu-id="4c634-140">单击**业务流程**在应用程序中，右键单击业务流程以登记，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="4c634-140">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Start**.</span></span>  

6. <span data-ttu-id="4c634-141">右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="4c634-141">Right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, and then click **Start**.</span></span>  

## <a name="generate-multiple-schemas"></a><span data-ttu-id="4c634-142">生成多个架构</span><span class="sxs-lookup"><span data-stu-id="4c634-142">Generate Multiple Schemas</span></span>  
 <span data-ttu-id="4c634-143">如果使用使用适配器服务向导来生成多个架构，一个或多个元素可能会导致编译失败有关的架构中重复[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="4c634-143">If you use the Consume Adapter Service Wizard to generate multiple schemas, one or more elements may be duplicated in the schemas resulting in compilation failure for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="4c634-144">您可以避免此问题选择**生成唯一的架构类型**复选框以确保架构类型生成包含唯一命名空间。</span><span class="sxs-lookup"><span data-stu-id="4c634-144">You can avoid this by selecting the **Generate Unique Schema Type** check box to ensure that schema types are generated with unique namespaces.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4c634-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c634-145">See Also</span></span>  
 [<span data-ttu-id="4c634-146">使用创建使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="4c634-146">Consume an adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)