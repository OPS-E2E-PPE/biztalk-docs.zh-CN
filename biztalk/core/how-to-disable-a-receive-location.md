---
title: 如何禁用接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], disabling
- receive locations, disabling
- disabling, receive locations
ms.assetid: 079a5c2c-3aec-49b3-afac-f3202404bca1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67356b22c0cc4aeae6001a15a83245104a0048f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385205"
---
# <a name="how-to-disable-a-receive-location"></a><span data-ttu-id="abd19-102">如何禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="abd19-102">How to Disable a Receive Location</span></span>
<span data-ttu-id="abd19-103">本主题介绍如何使用 BizTalk Server 管理控制台禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="abd19-103">This topic describes how to use the BizTalk Server Administration console to disable a receive location.</span></span> <span data-ttu-id="abd19-104">禁用接收位置时，它将停止接收消息。</span><span class="sxs-lookup"><span data-stu-id="abd19-104">When you disable a receive location, it stops receiving messages.</span></span> <span data-ttu-id="abd19-105">如果你想要在禁用接收位置之后, 您可以它再次启用，以便它将再次接收消息。</span><span class="sxs-lookup"><span data-stu-id="abd19-105">If you want, after disabling a receive location, you can enable it again, so that it will again receive messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="abd19-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="abd19-106">Prerequisites</span></span>  
 <span data-ttu-id="abd19-107">若要执行本主题中的过程，必须是 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="abd19-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="abd19-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="abd19-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-disable-a-receive-location"></a><span data-ttu-id="abd19-109">若要禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="abd19-109">To disable a receive location</span></span>  
  
1. <span data-ttu-id="abd19-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="abd19-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="abd19-111">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="abd19-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to disable a receive location.</span></span>  
  
3. <span data-ttu-id="abd19-112">单击**接收位置**，右键单击接收位置，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="abd19-112">Click **Receive Locations**, right-click the receive location, and then click **Disable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd19-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd19-113">See Also</span></span>  
 <span data-ttu-id="abd19-114">[管理接收位置](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="abd19-114">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="abd19-115">如何启用接收位置</span><span class="sxs-lookup"><span data-stu-id="abd19-115">How to Enable a Receive Location</span></span>](../core/how-to-enable-a-receive-location.md)