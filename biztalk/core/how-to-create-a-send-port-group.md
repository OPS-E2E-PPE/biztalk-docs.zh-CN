---
title: 如何创建发送端口组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d27914dd5d7ae59b0823c2e6009ab307c41b9b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970363"
---
# <a name="how-to-create-a-send-port-group"></a><span data-ttu-id="676ea-102">如何创建发送端口组</span><span class="sxs-lookup"><span data-stu-id="676ea-102">How to Create a Send Port Group</span></span>
<span data-ttu-id="676ea-103">本主题介绍如何使用 BizTalk Server 管理控制台在 BizTalk 应用程序中创建发送端口组，然后向其中添加发送端口。</span><span class="sxs-lookup"><span data-stu-id="676ea-103">This topic describes how to use the BizTalk Server Administration console to create a send port group in a BizTalk application and then add send ports to it.</span></span> <span data-ttu-id="676ea-104">仅向发送端口组，可以添加静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="676ea-104">You can add static one-way send ports only to a send port group.</span></span> <span data-ttu-id="676ea-105">若要路由消息，发送端口组必须至少包含一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="676ea-105">A send port group must contain at least one send port to route messages.</span></span>  
  
 <span data-ttu-id="676ea-106">可以添加其他应用程序中存在的发送端口。</span><span class="sxs-lookup"><span data-stu-id="676ea-106">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="676ea-107">如果进行这种添加，必须将包含发送端口组的应用程序的引用添加到包含此发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="676ea-107">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="676ea-108">有关说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="676ea-108">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="676ea-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="676ea-109">Prerequisites</span></span>  
 <span data-ttu-id="676ea-110">若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="676ea-110">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="676ea-111">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="676ea-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-create-a-send-port-group"></a><span data-ttu-id="676ea-112">创建发送端口组</span><span class="sxs-lookup"><span data-stu-id="676ea-112">To create a send port group</span></span>  
  
1.  <span data-ttu-id="676ea-113">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="676ea-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="676ea-114">在控制台树中，展开要在其中创建发送端口组的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="676ea-114">In the console tree, expand the BizTalk group and the BizTalk application in which you want to create a send port group.</span></span>  
  
3.  <span data-ttu-id="676ea-115">右键单击**发送端口组**，指向**新建**，然后单击**发送端口组**。</span><span class="sxs-lookup"><span data-stu-id="676ea-115">Right-click **Send Port Groups**, point to **New**, and then click **Send Port Group**.</span></span>  
  
4.  <span data-ttu-id="676ea-116">在**名称**框中，键入发送端口组的名称。</span><span class="sxs-lookup"><span data-stu-id="676ea-116">In the **Name** box, type a name for the send port group.</span></span>  
  
5.  <span data-ttu-id="676ea-117">在**发送端口**，单击下的下拉列表**名称**，然后单击发送端口将添加到发送端口组。</span><span class="sxs-lookup"><span data-stu-id="676ea-117">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="676ea-118">对每个要添加到该组的发送端口重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="676ea-118">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="676ea-119">若要创建新的发送端口并将其添加，请单击**\<新发送端口...\>**  ，然后按照中的说明[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="676ea-119">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
6.  <span data-ttu-id="676ea-120">完成后将发送端口添加到发送端口组，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="676ea-120">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676ea-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="676ea-121">See Also</span></span>  
 [<span data-ttu-id="676ea-122">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="676ea-122">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)