---
title: 如何添加接收位置接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adding to receive ports
- managing [receive ports], adding receive locations
- receive ports, adding receive locations
- adding, receive locations
ms.assetid: a71d50dc-629e-4b7f-aa59-6d2274d4cac3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c657c96c7714f04d18a2bd8d6d2d7ef90ad9cbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998998"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="9d140-102">如何将接收位置添加到接收端口</span><span class="sxs-lookup"><span data-stu-id="9d140-102">How to Add a Receive Location to a Receive Port</span></span>
<span data-ttu-id="9d140-103">本主题将介绍如何使用 BizTalk Server 管理控制台将新接收位置添加到接收端口。</span><span class="sxs-lookup"><span data-stu-id="9d140-103">This topic describes how to use the BizTalk Server Administration console to add a new receive location to a receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d140-104">您可以将绑定接收端口到业务流程时配置应用程序，如中所述[如何配置应用程序](../core/how-to-configure-an-application.md)或当您将业务流程绑定，如中所述[如何配置绑定业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="9d140-104">You can bind a receive port to an orchestration when you configure an application, as described in [How to Configure an Application](../core/how-to-configure-an-application.md) or when you bind an orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d140-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="9d140-105">Prerequisites</span></span>  
 <span data-ttu-id="9d140-106">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9d140-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9d140-107">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9d140-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="9d140-108">将接收位置添加到接收端口</span><span class="sxs-lookup"><span data-stu-id="9d140-108">To add a receive location to a receive port</span></span>  
  
1. <span data-ttu-id="9d140-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9d140-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9d140-110">在控制台树中，展开要为其将接收位置添加到接收端口的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d140-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to add a receive location to a receive port.</span></span>  
  
3. <span data-ttu-id="9d140-111">单击**接收端口**，右键单击你想要添加接收位置，指向的接收端口**新建**，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="9d140-111">Click **Receive Ports**, right-click the receive port to which you want to add a receive location, point to **New**, and then click **Receive Location**.</span></span>  
  
4. <span data-ttu-id="9d140-112">在中**名称**，键入新的接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="9d140-112">In **Name**, type a name for the new receive location.</span></span>  
  
5. <span data-ttu-id="9d140-113">按照中的说明配置接收位置属性[如何创建接收位置](../core/how-to-create-a-receive-location.md)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d140-113">Configure properties for the receive location by following the instructions in [How to Create a Receive Location](../core/how-to-create-a-receive-location.md), and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d140-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d140-114">See Also</span></span>  
 [<span data-ttu-id="9d140-115">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="9d140-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)