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
ms.openlocfilehash: 2bb7ff544b1c6d5ae5559dd4b64348a92cacb56b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337895"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="abf7b-102">如何登记发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="abf7b-102">How to Enlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="abf7b-103">本主题介绍如何使用 BizTalk Server 管理控制台来登记发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="abf7b-103">This topic describes how to use the BizTalk Server Administration console to enlist a send port or send port group.</span></span> <span data-ttu-id="abf7b-104">登记发送端口或发送端口组的 BizTalk 主机相关联的发送端口或发送端口组，并创建发送端口或发送端口组的订阅。</span><span class="sxs-lookup"><span data-stu-id="abf7b-104">Enlisting a send port or send port group associates the send port or send port group with a BizTalk host and creates the subscriptions for the send port or send port group.</span></span> <span data-ttu-id="abf7b-105">如果发送端口组不包含发送端口，登记发送端口组不会创建任何订阅。</span><span class="sxs-lookup"><span data-stu-id="abf7b-105">If a send port group does not contain a send port, enlisting the send port group does not create any subscriptions.</span></span> <span data-ttu-id="abf7b-106">此外，登记发送端口组不会更改它所包含的任何发送端口的状态。</span><span class="sxs-lookup"><span data-stu-id="abf7b-106">In addition, enlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf7b-107">启动发送端口或发送端口组也会自动登记。</span><span class="sxs-lookup"><span data-stu-id="abf7b-107">Starting a send port or send port group also automatically enlists it.</span></span> <span data-ttu-id="abf7b-108">此外，默认情况下启动应用程序登记并启动所有项目。</span><span class="sxs-lookup"><span data-stu-id="abf7b-108">In addition, by default starting an application enlists and starts all of its artifacts.</span></span> <span data-ttu-id="abf7b-109">有关详细信息，请参阅[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="abf7b-109">For more information, see [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span> <span data-ttu-id="abf7b-110">另请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="abf7b-110">Also see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="abf7b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="abf7b-111">Prerequisites</span></span>  
 <span data-ttu-id="abf7b-112">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="abf7b-112">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="abf7b-113">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="abf7b-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="abf7b-114">若要登记的发送端口或发送端口组</span><span class="sxs-lookup"><span data-stu-id="abf7b-114">To enlist a send port or send port group</span></span>  
  
1. <span data-ttu-id="abf7b-115">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="abf7b-115">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="abf7b-116">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序登记。</span><span class="sxs-lookup"><span data-stu-id="abf7b-116">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to enlist.</span></span>  
  
3. <span data-ttu-id="abf7b-117">单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="abf7b-117">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Enlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf7b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="abf7b-118">See Also</span></span>  
 [<span data-ttu-id="abf7b-119">管理发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="abf7b-119">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)