---
title: 如何配置入站的映射接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b840f4c418c835765345adc01da5c9c18812d3ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985598"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="5b168-102">如何为接收端口配置入站映射</span><span class="sxs-lookup"><span data-stu-id="5b168-102">How to Configure Inbound Maps for a Receive Port</span></span>
<span data-ttu-id="5b168-103">本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置入站映射。</span><span class="sxs-lookup"><span data-stu-id="5b168-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a receive port.</span></span> <span data-ttu-id="5b168-104">使用入站映射可以将入站消息从一种架构转换为另一种架构，例如，将从合作伙伴接收到的入站消息转换为您公司所使用的架构。</span><span class="sxs-lookup"><span data-stu-id="5b168-104">You use inbound maps to transform inbound messages from one schema to another; for example to transform messages received from a partner into a schema that your company uses.</span></span>  
  
 <span data-ttu-id="5b168-105">可以使用映射对该接收端口发送的消息应用 XSL 转换，而无需通过业务流程来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="5b168-105">You use a map to apply an XSL transformation to a message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="5b168-106">您可以添加入站映射、删除映射或更改现有映射。</span><span class="sxs-lookup"><span data-stu-id="5b168-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="5b168-107">可以为接收端口添加多个映射，但每个映射必须仅仅有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="5b168-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="5b168-108">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="5b168-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b168-109">应用程序开发人员可以通过在开发过程中使用本主题中的过程来为接收端口配置映射。</span><span class="sxs-lookup"><span data-stu-id="5b168-109">The application developer can configure maps for a receive port during the development process by using the procedure in this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b168-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="5b168-110">Prerequisites</span></span>  
 <span data-ttu-id="5b168-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5b168-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5b168-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5b168-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="5b168-113">为接收端口配置入站映射</span><span class="sxs-lookup"><span data-stu-id="5b168-113">To configure inbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="5b168-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5b168-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="5b168-115">在控制台树中，展开要为其配置入站映射的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b168-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="5b168-116">单击**接收端口**，右键单击该接收端口，单击**属性**，然后单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="5b168-116">Click **Receive Ports**, right-click the receive port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="5b168-117">下表中所述配置入站的映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5b168-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="5b168-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5b168-118">Use this</span></span>|<span data-ttu-id="5b168-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5b168-119">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="5b168-120">**删除**</span><span class="sxs-lookup"><span data-stu-id="5b168-120">**Remove**</span></span>|<span data-ttu-id="5b168-121">单击此项可删除所选映射。</span><span class="sxs-lookup"><span data-stu-id="5b168-121">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="5b168-122">**源文档**</span><span class="sxs-lookup"><span data-stu-id="5b168-122">**Source Document**</span></span>|<span data-ttu-id="5b168-123">从下拉列表中，选择要与此端口一起使用的源架构。</span><span class="sxs-lookup"><span data-stu-id="5b168-123">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="5b168-124">**地图**</span><span class="sxs-lookup"><span data-stu-id="5b168-124">**Map**</span></span>|<span data-ttu-id="5b168-125">从下拉列表中，选择要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="5b168-125">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="5b168-126">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="5b168-126">**Target Document**</span></span>|<span data-ttu-id="5b168-127">从下拉列表中，选择要与此端口一起使用的目标架构。</span><span class="sxs-lookup"><span data-stu-id="5b168-127">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b168-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b168-128">See Also</span></span>  
 <span data-ttu-id="5b168-129">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="5b168-129">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="5b168-130">管理映射</span><span class="sxs-lookup"><span data-stu-id="5b168-130">Managing Maps</span></span>](../core/managing-maps.md)