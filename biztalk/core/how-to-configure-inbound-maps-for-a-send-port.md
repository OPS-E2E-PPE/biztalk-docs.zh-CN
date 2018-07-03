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
ms.openlocfilehash: f5afe1edd63f10f39619948fb69d657bbaf85b81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996102"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="168a2-102">如何为发送端口配置入站映射</span><span class="sxs-lookup"><span data-stu-id="168a2-102">How to Configure Inbound Maps for a Send Port</span></span>
<span data-ttu-id="168a2-103">本主题将介绍如何使用 BizTalk Server 管理控制台为发送端口配置入站映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a send port.</span></span> <span data-ttu-id="168a2-104">入站映射仅和动态或静态要求响应发送端口一起使用。</span><span class="sxs-lookup"><span data-stu-id="168a2-104">Inbound maps are used only with dynamic or static solicit-response send ports.</span></span> <span data-ttu-id="168a2-105">可以使用映射对该端口接收的响应消息应用 XSL 转换，而无需通过业务流程来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="168a2-105">You use a map to apply an XSL transformation to a response message received by the port without processing the message through an orchestration.</span></span> <span data-ttu-id="168a2-106">您可以添加入站映射、删除映射或更改现有映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="168a2-107">还可以向发送端口添加多个映射，但每个映射必须具有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="168a2-107">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="168a2-108">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="168a2-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="168a2-109">应用程序开发人员可以通过在开发过程中使用本主题中的过程来配置映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-109">The application developer can configure maps during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="168a2-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="168a2-110">Prerequisites</span></span>  
 <span data-ttu-id="168a2-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="168a2-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="168a2-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="168a2-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="168a2-113">为发送端口配置入站映射</span><span class="sxs-lookup"><span data-stu-id="168a2-113">To configure inbound maps for a send port</span></span>  
  
1. <span data-ttu-id="168a2-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="168a2-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="168a2-115">在控制台树中，展开要为其配置入站映射的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="168a2-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound map for a send port.</span></span>  
  
3. <span data-ttu-id="168a2-116">展开**发送端口**，右键单击发送端口，单击**属性**，然后单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="168a2-116">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="168a2-117">下表中所述配置入站的映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="168a2-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="168a2-118">可根据需要重复这些步骤来添加或删除多个映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-118">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="168a2-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="168a2-119">Use this</span></span>|<span data-ttu-id="168a2-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="168a2-120">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="168a2-121">**删除**</span><span class="sxs-lookup"><span data-stu-id="168a2-121">**Remove**</span></span>|<span data-ttu-id="168a2-122">单击此项可删除所选映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-122">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="168a2-123">**源文档**</span><span class="sxs-lookup"><span data-stu-id="168a2-123">**Source Document**</span></span>|<span data-ttu-id="168a2-124">从下拉列表中选择入站映射的源文档。</span><span class="sxs-lookup"><span data-stu-id="168a2-124">From the drop-down list, select the source document for the inbound map.</span></span>|  
   |<span data-ttu-id="168a2-125">**地图**</span><span class="sxs-lookup"><span data-stu-id="168a2-125">**Map**</span></span>|<span data-ttu-id="168a2-126">从下拉列表中选择与源文档和目标文档关联的映射。</span><span class="sxs-lookup"><span data-stu-id="168a2-126">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="168a2-127">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="168a2-127">**Target Document**</span></span>|<span data-ttu-id="168a2-128">从下拉列表中选择入站映射的目标文档。</span><span class="sxs-lookup"><span data-stu-id="168a2-128">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="168a2-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="168a2-129">See Also</span></span>  
 <span data-ttu-id="168a2-130">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="168a2-130">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="168a2-131">管理映射</span><span class="sxs-lookup"><span data-stu-id="168a2-131">Managing Maps</span></span>](../core/managing-maps.md)