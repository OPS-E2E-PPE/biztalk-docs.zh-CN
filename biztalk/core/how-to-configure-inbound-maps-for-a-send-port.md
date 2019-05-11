---
title: 如何配置发送端口的入站的映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], inbound maps
- configuring, send ports
- send ports, inbound maps
- configuring, inbound maps
- managing [send ports], configuring
- send ports, configuring
ms.assetid: 213c66ba-928f-4c00-9a87-f45eaa9f7dca
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65b08e147e95f2fdb899784c373a3dc69013c8b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386239"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="be423-102">如何配置发送端口的入站的映射</span><span class="sxs-lookup"><span data-stu-id="be423-102">How to Configure Inbound Maps for a Send Port</span></span>
<span data-ttu-id="be423-103">本主题介绍如何使用 BizTalk Server 管理控制台配置发送端口的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="be423-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a send port.</span></span> <span data-ttu-id="be423-104">入站的映射仅用于动态或静态要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="be423-104">Inbound maps are used only with dynamic or static solicit-response send ports.</span></span> <span data-ttu-id="be423-105">使用映射到接收端口，而无需通过业务流程处理该消息的响应消息应用 XSL 转换。</span><span class="sxs-lookup"><span data-stu-id="be423-105">You use a map to apply an XSL transformation to a response message received by the port without processing the message through an orchestration.</span></span> <span data-ttu-id="be423-106">可以添加入站的映射、 删除映射，或更改现有映射到另一个。</span><span class="sxs-lookup"><span data-stu-id="be423-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="be423-107">可以将多个映射添加到发送端口，但每个映射必须具有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="be423-107">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="be423-108">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="be423-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be423-109">应用程序开发人员可以通过使用本主题中的过程在开发过程中配置映射。</span><span class="sxs-lookup"><span data-stu-id="be423-109">The application developer can configure maps during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be423-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="be423-110">Prerequisites</span></span>  
 <span data-ttu-id="be423-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="be423-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="be423-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="be423-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="be423-113">若要配置为发送端口的入站的映射</span><span class="sxs-lookup"><span data-stu-id="be423-113">To configure inbound maps for a send port</span></span>  
  
1. <span data-ttu-id="be423-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="be423-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="be423-115">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置为发送端口的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="be423-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound map for a send port.</span></span>  
  
3. <span data-ttu-id="be423-116">展开**发送端口**，右键单击发送端口，单击**属性**，然后单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="be423-116">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="be423-117">下表中所述配置入站的映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="be423-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="be423-118">根据需要添加或删除多个映射重复。</span><span class="sxs-lookup"><span data-stu-id="be423-118">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="be423-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be423-119">Use this</span></span>|<span data-ttu-id="be423-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be423-120">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="be423-121">**删除**</span><span class="sxs-lookup"><span data-stu-id="be423-121">**Remove**</span></span>|<span data-ttu-id="be423-122">单击此项可删除所选的映射。</span><span class="sxs-lookup"><span data-stu-id="be423-122">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="be423-123">**源文档**</span><span class="sxs-lookup"><span data-stu-id="be423-123">**Source Document**</span></span>|<span data-ttu-id="be423-124">从下拉列表中，选择入站映射的源文档。</span><span class="sxs-lookup"><span data-stu-id="be423-124">From the drop-down list, select the source document for the inbound map.</span></span>|  
   |<span data-ttu-id="be423-125">**地图**</span><span class="sxs-lookup"><span data-stu-id="be423-125">**Map**</span></span>|<span data-ttu-id="be423-126">从下拉列表中，选择要将与源和目标文档关联的映射。</span><span class="sxs-lookup"><span data-stu-id="be423-126">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="be423-127">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="be423-127">**Target Document**</span></span>|<span data-ttu-id="be423-128">从下拉列表中，选择入站映射的目标文档。</span><span class="sxs-lookup"><span data-stu-id="be423-128">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be423-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="be423-129">See Also</span></span>  
 <span data-ttu-id="be423-130">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="be423-130">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="be423-131">管理映射</span><span class="sxs-lookup"><span data-stu-id="be423-131">Managing Maps</span></span>](../core/managing-maps.md)