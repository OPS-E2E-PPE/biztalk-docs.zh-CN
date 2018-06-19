---
title: 如何删除接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5ad0b1d69747f3a890fbc20c63b8aa76c30639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249069"
---
# <a name="how-to-delete-a-receive-port"></a><span data-ttu-id="216b7-102">如何删除接收端口</span><span class="sxs-lookup"><span data-stu-id="216b7-102">How to Delete a Receive Port</span></span>
<span data-ttu-id="216b7-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="216b7-103">This topic describes how to use the BizTalk Server Administration console to delete a receive port from a BizTalk application.</span></span> <span data-ttu-id="216b7-104">进行此操作时，还将删除该组的 BizTalk 管理数据库中的接收端口，与此同时此接收端口的所有接收位置也被删除。</span><span class="sxs-lookup"><span data-stu-id="216b7-104">When you do this, the receive port is also deleted from the BizTalk Management database for the group, as are all receive locations in this receive port.</span></span>  
  
 <span data-ttu-id="216b7-105">为了使此操作成功，不能将接收端口绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="216b7-105">For this operation to succeed, the receive port cannot be bound to an orchestration.</span></span> <span data-ttu-id="216b7-106">有关删除接收端口的绑定的说明，请参阅[如何取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="216b7-106">For instructions on removing the bindings for a receive port, see [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="216b7-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="216b7-107">Prerequisites</span></span>  
 <span data-ttu-id="216b7-108">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="216b7-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="216b7-109">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="216b7-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-port"></a><span data-ttu-id="216b7-110">删除接收端口</span><span class="sxs-lookup"><span data-stu-id="216b7-110">To delete a receive port</span></span>  
  
1.  <span data-ttu-id="216b7-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="216b7-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="216b7-112">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的接收端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="216b7-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the receive port that you want to delete.</span></span>  
  
3.  <span data-ttu-id="216b7-113">单击**接收端口**，右键单击接收端口，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="216b7-113">Click **Receive Ports**, right-click the receive port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216b7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="216b7-114">See Also</span></span>  
 [<span data-ttu-id="216b7-115">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="216b7-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)