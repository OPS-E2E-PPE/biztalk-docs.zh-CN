---
title: 如何删除接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19828b7b456e872af78c2bae3c89ed75828a32ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249725"
---
# <a name="how-to-delete-a-receive-location"></a><span data-ttu-id="4d0cf-102">如何删除接收位置</span><span class="sxs-lookup"><span data-stu-id="4d0cf-102">How to Delete a Receive Location</span></span>
<span data-ttu-id="4d0cf-103">本主题介绍如何使用 BizTalk Server 管理控制台来删除接收位置。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-103">This topic describes how to use the BizTalk Server Administration console to delete a receive location.</span></span> <span data-ttu-id="4d0cf-104">在您删除某一接收位置时，该位置将从 BizTalk 管理数据库中删除，并且不再显示在 BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-104">When you delete a receive location, it is removed from the BizTalk Management database and is no longer displayed in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4d0cf-105">在删除接收位置时，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="4d0cf-105">When deleting a receive location, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="4d0cf-106">在可以删除接收位置之前，它必须先将其禁用中, 所述[如何禁用接收位置](../core/how-to-disable-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-106">Before you can delete a receive location, it must first be disabled, as described in [How to Disable a Receive Location](../core/how-to-disable-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="4d0cf-107">不能删除接收端口的主接收位置。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-107">You cannot delete the primary receive location for a receive port.</span></span> <span data-ttu-id="4d0cf-108">如果尝试这样做，将收到错误信息。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-108">If you attempt this, you will receive an error message.</span></span> <span data-ttu-id="4d0cf-109">若要删除接收位置，可以删除接收端口（这也将删除它所包含的所有接收位置），或将其他接收位置设为主接收位置，然后删除原来的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-109">To delete the receive location, you can either delete the receive port, which also deletes all of the receive locations that it contains, or you can make a different receive location primary and then delete the original receive location.</span></span> <span data-ttu-id="4d0cf-110">有关使主接收位置的接收位置的说明，请参阅[如何编辑接收位置的属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-110">For instructions on making a receive location the primary receive location, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
-   <span data-ttu-id="4d0cf-111">删除某个接收位置之后，请重新启动与所删除的接收位置对应的独立主机工作进程。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-111">After you delete a receive location, restart the Isolated Host Worker Processes corresponding to the deleted receive location.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d0cf-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="4d0cf-112">Prerequisites</span></span>  
 <span data-ttu-id="4d0cf-113">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4d0cf-114">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-location"></a><span data-ttu-id="4d0cf-115">若要删除接收位置</span><span class="sxs-lookup"><span data-stu-id="4d0cf-115">To delete a receive location</span></span>  
  
1.  <span data-ttu-id="4d0cf-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4d0cf-117">在控制台树中，展开要为其删除接收位置的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to delete a receive location.</span></span>  
  
3.  <span data-ttu-id="4d0cf-118">单击**接收位置**，右键单击要删除，然后单击的接收位置**删除**。</span><span class="sxs-lookup"><span data-stu-id="4d0cf-118">Click **Receive Locations**, right-click the receive location to delete, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0cf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d0cf-119">See Also</span></span>  
 [<span data-ttu-id="4d0cf-120">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="4d0cf-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)