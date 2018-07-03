---
title: 如何为发送端口配置备份传输选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73074cd4b644a3d57765a389ca4120f5b1d799b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979718"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a><span data-ttu-id="9dd82-102">如何为发送端口配置备份传输选项</span><span class="sxs-lookup"><span data-stu-id="9dd82-102">How to Configure Backup Transport Options for a Send Port</span></span>
<span data-ttu-id="9dd82-103">本主题将介绍如何使用 BizTalk Server 管理控制台为发送端口配置备份传输选项。</span><span class="sxs-lookup"><span data-stu-id="9dd82-103">This topic describes how to use the BizTalk Server Administration console to configure backup transport options for a send port.</span></span> <span data-ttu-id="9dd82-104">如果主传输无法正常工作，则您所指定的备份传输将生效。</span><span class="sxs-lookup"><span data-stu-id="9dd82-104">The backup transport that you specify takes effect in the event the primary transport fails to function.</span></span> <span data-ttu-id="9dd82-105">中所述配置主传输[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="9dd82-105">Configuring the primary transport is described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dd82-106">对于动态端口，没有可进行配置的属性，因为其传输选项在运行时自动确定。</span><span class="sxs-lookup"><span data-stu-id="9dd82-106">For dynamic ports, there are not properties available to configure because transport options are automatically determined at run time.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9dd82-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="9dd82-107">Prerequisites</span></span>  
 <span data-ttu-id="9dd82-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9dd82-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9dd82-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9dd82-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-specify-transport-options-for-a-send-port"></a><span data-ttu-id="9dd82-110">若要指定发送端口的传输选项</span><span class="sxs-lookup"><span data-stu-id="9dd82-110">To specify transport options for a send port</span></span>  
  
1. <span data-ttu-id="9dd82-111">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9dd82-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9dd82-112">在控制台树中，展开要为其配置备份传输选项的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9dd82-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure backup transport options for a send port.</span></span>  
  
3. <span data-ttu-id="9dd82-113">展开**发送端口**，右键单击发送端口配置，请单击**属性**，然后单击**备份传输**。</span><span class="sxs-lookup"><span data-stu-id="9dd82-113">Expand **Send Ports**, right-click the send port to configure, click **Properties**, and then click **Backup Transport**.</span></span>  
  
4. <span data-ttu-id="9dd82-114">下表中所述配置备份传输属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9dd82-114">Configure backup transport properties as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="9dd82-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9dd82-115">Use this</span></span>|<span data-ttu-id="9dd82-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9dd82-116">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="9dd82-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dd82-117">**Type**</span></span>|<span data-ttu-id="9dd82-118">从下拉列表中，选择适当的备份传输类型或传输协议。</span><span class="sxs-lookup"><span data-stu-id="9dd82-118">From the drop-down list, select the appropriate backup transport type, or transport protocol.</span></span> <span data-ttu-id="9dd82-119">如果端口是要求响应端口，则该列表中只显示支持要求响应的传输类型。</span><span class="sxs-lookup"><span data-stu-id="9dd82-119">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span>|  
   |<span data-ttu-id="9dd82-120">**配置**</span><span class="sxs-lookup"><span data-stu-id="9dd82-120">**Configure**</span></span>|<span data-ttu-id="9dd82-121">选择备份传输类型后，单击**配置**，然后配置传输属性。</span><span class="sxs-lookup"><span data-stu-id="9dd82-121">After you select the backup transport type, click **Configure**, and then configure transport properties.</span></span> <span data-ttu-id="9dd82-122">有关配置属性的详细信息，请单击**帮助**。</span><span class="sxs-lookup"><span data-stu-id="9dd82-122">For more information about configuring the properties, click **Help**.</span></span>|  
   |<span data-ttu-id="9dd82-123">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="9dd82-123">**Send handler**</span></span>|<span data-ttu-id="9dd82-124">从下拉列表中选择运行发送适配器的主机实例。</span><span class="sxs-lookup"><span data-stu-id="9dd82-124">From the drop-down list, select the host instance on which the send adapter is running.</span></span>|  
   |<span data-ttu-id="9dd82-125">**重试次数**</span><span class="sxs-lookup"><span data-stu-id="9dd82-125">**Retry count**</span></span>|<span data-ttu-id="9dd82-126">指定在消息失败时发送端口重发消息的次数。</span><span class="sxs-lookup"><span data-stu-id="9dd82-126">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="9dd82-127">默认值为 3；允许的范围为 0 到 1,000。</span><span class="sxs-lookup"><span data-stu-id="9dd82-127">The default is 3; the allowed range is from 0 to 1,000.</span></span>|  
   |<span data-ttu-id="9dd82-128">**重试间隔**</span><span class="sxs-lookup"><span data-stu-id="9dd82-128">**Retry interval**</span></span>|<span data-ttu-id="9dd82-129">指定两次重发消息尝试之间的时间间隔（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="9dd82-129">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="9dd82-130">默认值为 5;允许的范围是从 0 到 525600。</span><span class="sxs-lookup"><span data-stu-id="9dd82-130">The default is 5; the allowed range is from 0 to 525,600.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dd82-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dd82-131">See Also</span></span>  
 [<span data-ttu-id="9dd82-132">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="9dd82-132">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)