---
title: 如何添加接收到的位置接收端口 |Microsoft 文档
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
ms.openlocfilehash: 01a2d51103e8554a221d1598558a0180850c4a5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247381"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="0d1f6-102">如何将接收位置添加到接收端口</span><span class="sxs-lookup"><span data-stu-id="0d1f6-102">How to Add a Receive Location to a Receive Port</span></span>
<span data-ttu-id="0d1f6-103">本主题将介绍如何使用 BizTalk Server 管理控制台将新接收位置添加到接收端口。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-103">This topic describes how to use the BizTalk Server Administration console to add a new receive location to a receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d1f6-104">你可以将绑定接收端口到业务流程时配置应用程序，如中所述[如何配置应用程序](../core/how-to-configure-an-application.md)或当你绑定业务流程中所述[如何配置绑定业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-104">You can bind a receive port to an orchestration when you configure an application, as described in [How to Configure an Application](../core/how-to-configure-an-application.md) or when you bind an orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0d1f6-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="0d1f6-105">Prerequisites</span></span>  
 <span data-ttu-id="0d1f6-106">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0d1f6-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="0d1f6-108">将接收位置添加到接收端口</span><span class="sxs-lookup"><span data-stu-id="0d1f6-108">To add a receive location to a receive port</span></span>  
  
1.  <span data-ttu-id="0d1f6-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0d1f6-110">在控制台树中，展开要为其将接收位置添加到接收端口的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to add a receive location to a receive port.</span></span>  
  
3.  <span data-ttu-id="0d1f6-111">单击**接收端口**，右键单击你想要添加接收位置，指向接收端口**新建**，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-111">Click **Receive Ports**, right-click the receive port to which you want to add a receive location, point to **New**, and then click **Receive Location**.</span></span>  
  
4.  <span data-ttu-id="0d1f6-112">在**名称**，键入新接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-112">In **Name**, type a name for the new receive location.</span></span>  
  
5.  <span data-ttu-id="0d1f6-113">通过中的说明配置为接收位置属性[如何创建接收位置](../core/how-to-create-a-receive-location.md)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0d1f6-113">Configure properties for the receive location by following the instructions in [How to Create a Receive Location](../core/how-to-create-a-receive-location.md), and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1f6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d1f6-114">See Also</span></span>  
 [<span data-ttu-id="0d1f6-115">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="0d1f6-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)