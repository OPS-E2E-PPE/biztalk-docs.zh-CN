---
title: 如何配置出站映射接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee2d18a2a1d0e8d39001a232d909a805a27f4707
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341280"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="5a584-102">如何配置出站映射接收端口</span><span class="sxs-lookup"><span data-stu-id="5a584-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="5a584-103">本主题介绍如何使用 BizTalk Server 管理控制台配置接收端口的出站映射。</span><span class="sxs-lookup"><span data-stu-id="5a584-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="5a584-104">可以使用出站映射与请求-响应接收端口转换到另一个; 的出站消息从一个架构若要将您的公司使用的消息转换为合作伙伴使用的架构的示例。</span><span class="sxs-lookup"><span data-stu-id="5a584-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="5a584-105">使用映射来应用 XSL 转换，而无需通过业务流程处理该消息的接收端口发送的响应消息。</span><span class="sxs-lookup"><span data-stu-id="5a584-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="5a584-106">可以添加出站映射、 删除映射，或更改现有映射到另一个。</span><span class="sxs-lookup"><span data-stu-id="5a584-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="5a584-107">可以将多个映射添加到接收端口，但每个映射必须具有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="5a584-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="5a584-108">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="5a584-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a584-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="5a584-109">Prerequisites</span></span>  
 <span data-ttu-id="5a584-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5a584-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5a584-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5a584-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="5a584-112">若要配置接收端口的出站映射</span><span class="sxs-lookup"><span data-stu-id="5a584-112">To configure outbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="5a584-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5a584-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="5a584-114">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要配置接收端口的出站映射。</span><span class="sxs-lookup"><span data-stu-id="5a584-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="5a584-115">展开**接收端口**，右键单击该接收端口，单击**属性**，然后单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="5a584-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="5a584-116">下表中所述配置出站映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5a584-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="5a584-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5a584-117">Use this</span></span>|<span data-ttu-id="5a584-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5a584-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="5a584-119">**删除**</span><span class="sxs-lookup"><span data-stu-id="5a584-119">**Remove**</span></span>|<span data-ttu-id="5a584-120">单击此项可删除所选的映射。</span><span class="sxs-lookup"><span data-stu-id="5a584-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="5a584-121">**源文档**</span><span class="sxs-lookup"><span data-stu-id="5a584-121">**Source Document**</span></span>|<span data-ttu-id="5a584-122">从下拉列表中，选择要使用与此端口的源架构。</span><span class="sxs-lookup"><span data-stu-id="5a584-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="5a584-123">**地图**</span><span class="sxs-lookup"><span data-stu-id="5a584-123">**Map**</span></span>|<span data-ttu-id="5a584-124">从下拉列表中，选择你想要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="5a584-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="5a584-125">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="5a584-125">**Target Document**</span></span>|<span data-ttu-id="5a584-126">从下拉列表中，选择要使用与此端口的目标架构。</span><span class="sxs-lookup"><span data-stu-id="5a584-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a584-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a584-127">See Also</span></span>  
 <span data-ttu-id="5a584-128">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="5a584-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="5a584-129">管理映射</span><span class="sxs-lookup"><span data-stu-id="5a584-129">Managing Maps</span></span>](../core/managing-maps.md)