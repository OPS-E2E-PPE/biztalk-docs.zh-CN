---
title: 如何删除发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e28f2cd7cf4b125e9f6dbd1afa7d9a2e57f2c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338634"
---
# <a name="how-to-delete-a-send-port"></a><span data-ttu-id="31e0a-102">如何删除发送端口</span><span class="sxs-lookup"><span data-stu-id="31e0a-102">How to Delete a Send Port</span></span>
<span data-ttu-id="31e0a-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="31e0a-103">This topic describes how to use the BizTalk Server Administration console to delete a send port from a BizTalk application.</span></span> <span data-ttu-id="31e0a-104">执行此操作，发送端口是还从该组的 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="31e0a-104">When you do this, the send port is also deleted from the BizTalk Management database for the group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31e0a-105">删除发送端口时，任何正在运行的服务不再与此端口相关联的实例可以获取有关发送端口，如其名称的配置信息。</span><span class="sxs-lookup"><span data-stu-id="31e0a-105">When you delete a send port, any running service instances associated with that port can no longer obtain configuration information about the send port, such as its name.</span></span> <span data-ttu-id="31e0a-106">尽管此信息被缓存，如果服务实例，必须重新发送一条消息，它将不能完成，并将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="31e0a-106">Although this information is cached, if the service instance must resend a message, it will not be able to complete, and the message will be suspended.</span></span> <span data-ttu-id="31e0a-107">在删除之前的发送端口，您应该验证是否没有正在运行服务实例，如中所述[如何查看发送端口的实例信息](../core/how-to-view-instance-information-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-107">Before deleting a send port, you should verify that there are no running service instances, as described in [How to View Instance Information for a Send Port](../core/how-to-view-instance-information-for-a-send-port.md).</span></span>  
  
 <span data-ttu-id="31e0a-108">仅当满足以下条件，则可以删除发送端口：</span><span class="sxs-lookup"><span data-stu-id="31e0a-108">You can delete a send port only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="31e0a-109">业务流程未绑定到发送端口。</span><span class="sxs-lookup"><span data-stu-id="31e0a-109">An orchestration is not bound to the send port.</span></span> <span data-ttu-id="31e0a-110">如果是这样，您可以通过执行中的说明删除绑定[如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-110">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="31e0a-111">发送端口是同时停止并取消登记。</span><span class="sxs-lookup"><span data-stu-id="31e0a-111">The send port is both stopped and unenlisted.</span></span> <span data-ttu-id="31e0a-112">有关停止和取消登记发送端口的说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)并[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-112">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="31e0a-113">参与方未引用的发送端口。</span><span class="sxs-lookup"><span data-stu-id="31e0a-113">The send port is not referenced by a party.</span></span> <span data-ttu-id="31e0a-114">删除对发送端口从参与方的引用的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-114">For instructions on removing a reference to a send port from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
-   <span data-ttu-id="31e0a-115">中的发送端口组不包括发送端口。</span><span class="sxs-lookup"><span data-stu-id="31e0a-115">The send port is not included in a send port group.</span></span> <span data-ttu-id="31e0a-116">有关从发送端口组中删除发送端口的说明，请参阅[如何从发送端口组中删除发送端口](../core/how-to-remove-a-send-port-from-a-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-116">For instructions on removing a send port from a send port group, see [How to Remove a Send Port from a Send Port Group](../core/how-to-remove-a-send-port-from-a-send-port-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31e0a-117">应用程序开发人员可以通过使用本主题中的过程在开发过程中删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="31e0a-117">The application developer can delete a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31e0a-118">先决条件</span><span class="sxs-lookup"><span data-stu-id="31e0a-118">Prerequisites</span></span>  
 <span data-ttu-id="31e0a-119">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="31e0a-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="31e0a-120">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="31e0a-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port"></a><span data-ttu-id="31e0a-121">若要删除的发送端口</span><span class="sxs-lookup"><span data-stu-id="31e0a-121">To delete a send port</span></span>  
  
1. <span data-ttu-id="31e0a-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="31e0a-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="31e0a-123">在控制台树中，展开 BizTalk Server 管理、 展开 BizTalk 组中，展开应用程序，，然后展开包含你想要删除的发送端口的应用程序</span><span class="sxs-lookup"><span data-stu-id="31e0a-123">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand Applications, and then expand the application containing the send port that you want to delete</span></span>  
  
3. <span data-ttu-id="31e0a-124">单击**发送端口**，右键单击发送端口，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="31e0a-124">Click **Send Ports**, right-click the send port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e0a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="31e0a-125">See Also</span></span>  
 [<span data-ttu-id="31e0a-126">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="31e0a-126">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)