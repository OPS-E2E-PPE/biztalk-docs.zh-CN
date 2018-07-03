---
title: 如何登记发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127673659878738a57045ea1b5bd9f1d1cf16d10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016192"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="cda5a-102">如何登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="cda5a-102">How to Enlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="cda5a-103">本主题将介绍如何使用 BizTalk Server 管理控制台登记发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="cda5a-103">This topic describes how to use the BizTalk Server Administration console to enlist a send port or send port group.</span></span> <span data-ttu-id="cda5a-104">登记发送端口或发送端口组将把发送端口或发送端口组与 BizTalk 主机相关联，并为发送端口或发送端口组创建订阅。</span><span class="sxs-lookup"><span data-stu-id="cda5a-104">Enlisting a send port or send port group associates the send port or send port group with a BizTalk host and creates the subscriptions for the send port or send port group.</span></span> <span data-ttu-id="cda5a-105">如果发送端口组不包含发送端口，登记发送端口组将不会创建任何订阅。</span><span class="sxs-lookup"><span data-stu-id="cda5a-105">If a send port group does not contain a send port, enlisting the send port group does not create any subscriptions.</span></span> <span data-ttu-id="cda5a-106">此外，登记发送端口组不会改变其包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="cda5a-106">In addition, enlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cda5a-107">启动发送端口或发送端口组也会自动登记该发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="cda5a-107">Starting a send port or send port group also automatically enlists it.</span></span> <span data-ttu-id="cda5a-108">此外，默认情况下，启动应用程序会登记并启动它的所有项目。</span><span class="sxs-lookup"><span data-stu-id="cda5a-108">In addition, by default starting an application enlists and starts all of its artifacts.</span></span> <span data-ttu-id="cda5a-109">有关详细信息，请参阅[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="cda5a-109">For more information, see [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span> <span data-ttu-id="cda5a-110">另请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="cda5a-110">Also see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cda5a-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="cda5a-111">Prerequisites</span></span>  
 <span data-ttu-id="cda5a-112">若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cda5a-112">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="cda5a-113">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="cda5a-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="cda5a-114">登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="cda5a-114">To enlist a send port or send port group</span></span>  
  
1. <span data-ttu-id="cda5a-115">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cda5a-115">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cda5a-116">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序登记。</span><span class="sxs-lookup"><span data-stu-id="cda5a-116">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to enlist.</span></span>  
  
3. <span data-ttu-id="cda5a-117">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="cda5a-117">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Enlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda5a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cda5a-118">See Also</span></span>  
 [<span data-ttu-id="cda5a-119">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="cda5a-119">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)