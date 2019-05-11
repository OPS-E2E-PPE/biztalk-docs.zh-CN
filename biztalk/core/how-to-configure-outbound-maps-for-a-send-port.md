---
title: 如何配置发送端口的出站映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7140797eba38ee2eebe22ad01d04fdf4acee83ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386231"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="f7efa-102">如何配置发送端口的出站映射</span><span class="sxs-lookup"><span data-stu-id="f7efa-102">How to Configure Outbound Maps for a Send Port</span></span>
<span data-ttu-id="f7efa-103">本主题介绍如何使用 BizTalk Server 管理控制台配置发送端口的出站映射。</span><span class="sxs-lookup"><span data-stu-id="f7efa-103">This topic describes how to configure outbound maps for a send port by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="f7efa-104">使用映射来应用 XSL 转换，而无需通过业务流程处理该消息的发送端口发送的消息。</span><span class="sxs-lookup"><span data-stu-id="f7efa-104">You use a map to apply an XSL transformation to a message sent by the send port without processing the message through an orchestration.</span></span> <span data-ttu-id="f7efa-105">可以添加出站映射、 删除映射，或更改现有映射到另一个。</span><span class="sxs-lookup"><span data-stu-id="f7efa-105">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="f7efa-106">可以将多个映射添加到发送端口，但每个映射必须具有唯一的源架构。</span><span class="sxs-lookup"><span data-stu-id="f7efa-106">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="f7efa-107">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="f7efa-107">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7efa-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="f7efa-108">Prerequisites</span></span>  
 <span data-ttu-id="f7efa-109">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f7efa-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f7efa-110">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f7efa-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="f7efa-111">若要配置为发送端口的出站映射</span><span class="sxs-lookup"><span data-stu-id="f7efa-111">To configure outbound maps for a send port</span></span>  
  
1. <span data-ttu-id="f7efa-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f7efa-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f7efa-113">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序要为其配置为发送端口的出站映射。</span><span class="sxs-lookup"><span data-stu-id="f7efa-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure the outbound maps for a send port.</span></span>  
  
3. <span data-ttu-id="f7efa-114">展开**发送端口**，右键单击发送端口，单击**属性**，然后单击**出站映射**。</span><span class="sxs-lookup"><span data-stu-id="f7efa-114">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="f7efa-115">下表中所述配置出站映射，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f7efa-115">Configure outbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="f7efa-116">根据需要添加或删除多个映射重复。</span><span class="sxs-lookup"><span data-stu-id="f7efa-116">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="f7efa-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f7efa-117">Use this</span></span>|<span data-ttu-id="f7efa-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f7efa-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="f7efa-119">**删除**</span><span class="sxs-lookup"><span data-stu-id="f7efa-119">**Remove**</span></span>|<span data-ttu-id="f7efa-120">单击此项可删除所选的映射。</span><span class="sxs-lookup"><span data-stu-id="f7efa-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="f7efa-121">**出站映射-源文档**</span><span class="sxs-lookup"><span data-stu-id="f7efa-121">**Outbound maps - Source Document**</span></span>|<span data-ttu-id="f7efa-122">从下拉列表中，选择出站映射的源文档。</span><span class="sxs-lookup"><span data-stu-id="f7efa-122">From the drop-down list, select the source document for the outbound map.</span></span>|  
   |<span data-ttu-id="f7efa-123">**出站映射-映射**</span><span class="sxs-lookup"><span data-stu-id="f7efa-123">**Outbound maps - Map**</span></span>|<span data-ttu-id="f7efa-124">从下拉列表中，选择要将与源和目标文档关联的映射。</span><span class="sxs-lookup"><span data-stu-id="f7efa-124">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="f7efa-125">**出站映射-目标文档**</span><span class="sxs-lookup"><span data-stu-id="f7efa-125">**Outbound maps - Target Document**</span></span>|<span data-ttu-id="f7efa-126">从下拉列表中，选择出站映射的目标文档。</span><span class="sxs-lookup"><span data-stu-id="f7efa-126">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7efa-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7efa-127">See Also</span></span>  
 <span data-ttu-id="f7efa-128">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="f7efa-128">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="f7efa-129">管理映射</span><span class="sxs-lookup"><span data-stu-id="f7efa-129">Managing Maps</span></span>](../core/managing-maps.md)