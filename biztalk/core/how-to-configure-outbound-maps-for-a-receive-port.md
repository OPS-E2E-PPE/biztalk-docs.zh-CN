---
title: 如何配置出站映射接收端口 |Microsoft 文档
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
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248509"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="ee8d0-102">如何为接收端口配置出站映射</span><span class="sxs-lookup"><span data-stu-id="ee8d0-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="ee8d0-103">本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置出站映射。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="ee8d0-104">可以将出站映射与请求-响应接收端口一起使用，以将出站消息从一个架构转换到另一个架构；例如，将公司使用的消息转换到合作伙伴使用的架构中。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="ee8d0-105">可以使用映射对该接收端口发送的响应消息应用 XSL 转换，而无需通过业务流程来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="ee8d0-106">您可以添加出站映射、删除映射或更改现有映射。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="ee8d0-107">可以为接收端口添加多个映射，但每个映射必须仅仅有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="ee8d0-108">有关地图背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ee8d0-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="ee8d0-109">Prerequisites</span></span>  
 <span data-ttu-id="ee8d0-110">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ee8d0-111">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="ee8d0-112">为接收端口配置出站映射</span><span class="sxs-lookup"><span data-stu-id="ee8d0-112">To configure outbound maps for a receive port</span></span>  
  
1.  <span data-ttu-id="ee8d0-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ee8d0-114">在控制台树中，展开要为其配置出站映射的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3.  <span data-ttu-id="ee8d0-115">展开**接收端口**，右键单击接收端口，请单击**属性**，然后单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4.  <span data-ttu-id="ee8d0-116">下表中所述配置出站映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="ee8d0-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ee8d0-117">Use this</span></span>|<span data-ttu-id="ee8d0-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ee8d0-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ee8d0-119">**删除**</span><span class="sxs-lookup"><span data-stu-id="ee8d0-119">**Remove**</span></span>|<span data-ttu-id="ee8d0-120">单击此项可删除所选映射。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-120">Click to remove the selected map.</span></span>|  
    |<span data-ttu-id="ee8d0-121">**源文档**</span><span class="sxs-lookup"><span data-stu-id="ee8d0-121">**Source Document**</span></span>|<span data-ttu-id="ee8d0-122">从下拉列表中，选择要与此端口一起使用的源架构。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="ee8d0-123">**地图**</span><span class="sxs-lookup"><span data-stu-id="ee8d0-123">**Map**</span></span>|<span data-ttu-id="ee8d0-124">从下拉列表中，选择要与此端口关联的映射。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="ee8d0-125">**目标文档**</span><span class="sxs-lookup"><span data-stu-id="ee8d0-125">**Target Document**</span></span>|<span data-ttu-id="ee8d0-126">从下拉列表中，选择要与此端口一起使用的目标架构。</span><span class="sxs-lookup"><span data-stu-id="ee8d0-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee8d0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee8d0-127">See Also</span></span>  
 <span data-ttu-id="ee8d0-128">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ee8d0-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="ee8d0-129">管理映射</span><span class="sxs-lookup"><span data-stu-id="ee8d0-129">Managing Maps</span></span>](../core/managing-maps.md)