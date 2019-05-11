---
title: 如何从发送端口组中删除发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9ab95b645d3bcdcef249de9b65fcf3891677d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335053"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="1b6ce-102">如何从发送端口组中删除发送端口</span><span class="sxs-lookup"><span data-stu-id="1b6ce-102">How to Remove a Send Port from a Send Port Group</span></span>
<span data-ttu-id="1b6ce-103">本主题介绍如何使用 BizTalk Server 管理控制台从发送端口组中删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-103">This topic describes how to use the BizTalk Server Administration console to remove a send port from a send port group.</span></span> <span data-ttu-id="1b6ce-104">当执行此操作时，发送端口不会删除从应用程序或 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-104">When you do this, the send port is not deleted from the application or the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="1b6ce-105">删除发送端口之前，则它必须处于已停止或已取消登记状态。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-105">Before you can remove a send port, it must be in a stopped or unenlisted state.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b6ce-106">若要将消息路由，发送端口组必须包含至少一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-106">To route messages, a send port group must contain at least one send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b6ce-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="1b6ce-107">Prerequisites</span></span>  
 <span data-ttu-id="1b6ce-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="1b6ce-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="1b6ce-110">若要从发送端口组中删除发送端口</span><span class="sxs-lookup"><span data-stu-id="1b6ce-110">To remove a send port from a send port group</span></span>  
  
1. <span data-ttu-id="1b6ce-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="1b6ce-112">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要从发送端口组中删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-112">In the console tree, expand the BizTalk group and the BizTalk application in which you want to remove a send port from a send port group.</span></span>  
  
3. <span data-ttu-id="1b6ce-113">单击**发送端口组**，右键单击发送端口组，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-113">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="1b6ce-114">下**名称**，单击发送端口以删除，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="1b6ce-114">Under **Name**, click the send port to remove, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6ce-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b6ce-115">See Also</span></span>  
 <span data-ttu-id="1b6ce-116">[创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="1b6ce-116">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="1b6ce-117">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="1b6ce-117">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)