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
ms.openlocfilehash: c5624d81597648b84d576fddc74909aff5b1742a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341453"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="3e99b-102">如何配置入站的映射接收端口</span><span class="sxs-lookup"><span data-stu-id="3e99b-102">How to Configure Inbound Maps for a Receive Port</span></span>
<span data-ttu-id="3e99b-103">本主题介绍如何使用 BizTalk Server 管理控制台配置接收端口的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="3e99b-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a receive port.</span></span> <span data-ttu-id="3e99b-104">使用入站的映射来转换到另一个; 的入站的消息从一个架构例如，将消息从合作伙伴接收到您的公司使用的架构。</span><span class="sxs-lookup"><span data-stu-id="3e99b-104">You use inbound maps to transform inbound messages from one schema to another; for example to transform messages received from a partner into a schema that your company uses.</span></span>  
  
 <span data-ttu-id="3e99b-105">使用映射来应用 XSL 转换，而无需通过业务流程处理该消息的接收端口发送的消息。</span><span class="sxs-lookup"><span data-stu-id="3e99b-105">You use a map to apply an XSL transformation to a message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="3e99b-106">可以添加入站的映射、 删除映射，或更改现有映射到另一个。</span><span class="sxs-lookup"><span data-stu-id="3e99b-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="3e99b-107">可以将多个映射添加到接收端口，但每个映射必须具有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="3e99b-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="3e99b-108">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="3e99b-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e99b-109">应用程序开发人员可以通过使用在此过程在开发过程中配置为接收端口的映射。</span><span class="sxs-lookup"><span data-stu-id="3e99b-109">The application developer can configure maps for a receive port during the development process by using the procedure in this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e99b-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="3e99b-110">Prerequisites</span></span>  
 <span data-ttu-id="3e99b-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3e99b-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3e99b-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3e99b-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="3e99b-113">若要配置接收端口的入站的映射</span><span class="sxs-lookup"><span data-stu-id="3e99b-113">To configure inbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="3e99b-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3e99b-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3e99b-115">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要配置接收端口的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="3e99b-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="3e99b-116">单击**接收端口**，右键单击该接收端口，单击**属性**，然后单击**入站映射**。</span><span class="sxs-lookup"><span data-stu-id="3e99b-116">Click **Receive Ports**, right-click the receive port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="3e99b-117">下表中所述配置入站的映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e99b-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="3e99b-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3e99b-118">Use this</span></span>|<span data-ttu-id="3e99b-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3e99b-119">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="3e99b-120">**删除**</span><span class="sxs-lookup"><span data-stu-id="3e99b-120">**Remove**</span></span>|<span data-ttu-id="3e99b-121">单击此项可删除所选的映射。</span><span class="sxs-lookup"><span data-stu-id="3e99b-121">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="3e99b-122">**源文档**</span><span class="sxs-lookup"><span data-stu-id="3e99b-122">**Source Document**</span></span>|<span data-ttu-id="3e99b-123">从下拉列表中，选择要使用与此端口的源架构。</span><span class="sxs-lookup"><span data-stu-id="3e99b-123">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="3e99b-124">**地图**</span><span class="sxs-lookup"><span data-stu-id="3e99b-124">**Map**</span></span>|<span data-ttu-id="3e99b-125">从下拉列表中，选择你想要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="3e99b-125">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="3e99b-126">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="3e99b-126">**Target Document**</span></span>|<span data-ttu-id="3e99b-127">从下拉列表中，选择要使用与此端口的目标架构。</span><span class="sxs-lookup"><span data-stu-id="3e99b-127">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e99b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e99b-128">See Also</span></span>  
 <span data-ttu-id="3e99b-129">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="3e99b-129">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="3e99b-130">管理映射</span><span class="sxs-lookup"><span data-stu-id="3e99b-130">Managing Maps</span></span>](../core/managing-maps.md)