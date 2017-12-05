---
title: "如何删除发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], deleting
- send ports, deleting
- deleting, send ports
ms.assetid: aff5980e-57bf-400c-82bd-3d02e143f227
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63355f742f12fbbaf57ccde7a1406dbb694ee073
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-delete-a-send-port"></a><span data-ttu-id="29799-102">如何删除发送端口</span><span class="sxs-lookup"><span data-stu-id="29799-102">How to Delete a Send Port</span></span>
<span data-ttu-id="29799-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="29799-103">This topic describes how to use the BizTalk Server Administration console to delete a send port from a BizTalk application.</span></span> <span data-ttu-id="29799-104">执行此操作时，发送端口也将删除从组 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="29799-104">When you do this, the send port is also deleted from the BizTalk Management database for the group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29799-105">当删除发送端口时，任何正在运行的服务与该端口关联的实例不能再获取有关发送端口，例如其名称的配置信息。</span><span class="sxs-lookup"><span data-stu-id="29799-105">When you delete a send port, any running service instances associated with that port can no longer obtain configuration information about the send port, such as its name.</span></span> <span data-ttu-id="29799-106">尽管此信息缓存的如果服务实例必须重新发送一条消息，它将不能完成，并且将挂起消息。</span><span class="sxs-lookup"><span data-stu-id="29799-106">Although this information is cached, if the service instance must resend a message, it will not be able to complete, and the message will be suspended.</span></span> <span data-ttu-id="29799-107">在删除之前发送端口，你应验证是否有任何运行中所述服务实例，[如何发送端口的视图实例信息](../core/how-to-view-instance-information-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="29799-107">Before deleting a send port, you should verify that there are no running service instances, as described in [How to View Instance Information for a Send Port](../core/how-to-view-instance-information-for-a-send-port.md).</span></span>  
  
 <span data-ttu-id="29799-108">仅当符合下列条件，你可以删除发送端口：</span><span class="sxs-lookup"><span data-stu-id="29799-108">You can delete a send port only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="29799-109">业务流程不绑定到发送端口中。</span><span class="sxs-lookup"><span data-stu-id="29799-109">An orchestration is not bound to the send port.</span></span> <span data-ttu-id="29799-110">如果出现这种情况，您可以通过执行中的说明删除绑定[如何取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="29799-110">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="29799-111">发送端口是同时停止并取消登记。</span><span class="sxs-lookup"><span data-stu-id="29799-111">The send port is both stopped and unenlisted.</span></span> <span data-ttu-id="29799-112">有关停止和取消登记发送端口的说明，请参阅[如何发送端口或发送端口组中取消](../core/how-to-unenlist-a-send-port-or-send-port-group.md)和[如何停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="29799-112">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="29799-113">发送端口未被方引用。</span><span class="sxs-lookup"><span data-stu-id="29799-113">The send port is not referenced by a party.</span></span> <span data-ttu-id="29799-114">有关删除从方对发送端口的引用的说明，请参阅[如何查看或编辑方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)。</span><span class="sxs-lookup"><span data-stu-id="29799-114">For instructions on removing a reference to a send port from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
-   <span data-ttu-id="29799-115">发送端口未包含在发送端口组。</span><span class="sxs-lookup"><span data-stu-id="29799-115">The send port is not included in a send port group.</span></span> <span data-ttu-id="29799-116">有关从发送端口组中删除发送端口的说明，请参阅[如何从发送端口组中删除发送端口](../core/how-to-remove-a-send-port-from-a-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="29799-116">For instructions on removing a send port from a send port group, see [How to Remove a Send Port from a Send Port Group](../core/how-to-remove-a-send-port-from-a-send-port-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29799-117">应用程序开发人员可以通过在开发过程中使用本主题中的过程来删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="29799-117">The application developer can delete a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29799-118">先决条件</span><span class="sxs-lookup"><span data-stu-id="29799-118">Prerequisites</span></span>  
 <span data-ttu-id="29799-119">若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="29799-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="29799-120">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="29799-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port"></a><span data-ttu-id="29799-121">若要删除发送端口</span><span class="sxs-lookup"><span data-stu-id="29799-121">To delete a send port</span></span>  
  
1.  <span data-ttu-id="29799-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="29799-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="29799-123">在控制台树中，展开 BizTalk Server 管理、 展开的 BizTalk 组，展开应用程序，，然后展开包含你想要删除的发送端口的应用程序</span><span class="sxs-lookup"><span data-stu-id="29799-123">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand Applications, and then expand the application containing the send port that you want to delete</span></span>  
  
3.  <span data-ttu-id="29799-124">单击**发送端口**，发送端口中，右键单击，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="29799-124">Click **Send Ports**, right-click the send port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29799-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29799-125">See Also</span></span>  
 [<span data-ttu-id="29799-126">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="29799-126">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)