---
title: "如何启用接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling, receive locations
- managing [receive locations], enabling
- receive locations, enabling
ms.assetid: ea1647cd-7bcb-4603-a64e-23b3fb0622a5
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c537f7d37f7d8c7d970f057dae88e02003b1cd9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-a-receive-location"></a><span data-ttu-id="d1e61-102">如何启用接收位置</span><span class="sxs-lookup"><span data-stu-id="d1e61-102">How to Enable a Receive Location</span></span>
<span data-ttu-id="d1e61-103">本主题介绍如何使用 BizTalk Server 管理控制台来启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="d1e61-103">This topic describes how to use the BizTalk Server Administration console to enable a receive location.</span></span> <span data-ttu-id="d1e61-104">接收位置必须在启用后才能接收消息。</span><span class="sxs-lookup"><span data-stu-id="d1e61-104">A receive location must be enabled before it can receive messages.</span></span>  
  
 <span data-ttu-id="d1e61-105">有关创建接收位置的说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="d1e61-105">For instructions on creating a receive location, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d1e61-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="d1e61-106">Prerequisites</span></span>  
 <span data-ttu-id="d1e61-107">若要执行本主题中描述的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="d1e61-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d1e61-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d1e61-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enable-a-receive-location"></a><span data-ttu-id="d1e61-109">若要启用接收位置</span><span class="sxs-lookup"><span data-stu-id="d1e61-109">To enable a receive location</span></span>  
  
1.  <span data-ttu-id="d1e61-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d1e61-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d1e61-111">在控制台树中，展开要为其启用接收位置的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1e61-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to enable a receive location.</span></span>  
  
3.  <span data-ttu-id="d1e61-112">单击**接收位置**，右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="d1e61-112">Click **Receive Locations**, right-click the receive location, and then click **Enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e61-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1e61-113">See Also</span></span>  
 [<span data-ttu-id="d1e61-114">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="d1e61-114">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)