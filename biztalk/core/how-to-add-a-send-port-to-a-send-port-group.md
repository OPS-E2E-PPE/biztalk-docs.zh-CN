---
title: 如何将发送端口添加到发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c2b616952aa4f24e40ddd56e035a6de4a77c58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007174"
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="a3d8f-102">如何向发送端口组添加发送端口</span><span class="sxs-lookup"><span data-stu-id="a3d8f-102">How to Add a Send Port to a Send Port Group</span></span>
<span data-ttu-id="a3d8f-103">本主题将介绍如何使用 BizTalk Server 管理控制台将一个或多个发送端口添加到发送端口组。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-103">This topic describes how to use the BizTalk Server Administration console to add one or more send ports to a send port group.</span></span> <span data-ttu-id="a3d8f-104">只能向发送端口组添加单向静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-104">You can only add one-way static send ports to a send port group.</span></span>  
  
 <span data-ttu-id="a3d8f-105">可以添加其他应用程序中存在的发送端口。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-105">You can add a send port that exists in a different application.</span></span> <span data-ttu-id="a3d8f-106">如果进行这种添加，必须将包含发送端口组的应用程序的引用添加到包含此发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-106">If you do this, you must add a reference from the application containing the send port group to the application containing the send port.</span></span> <span data-ttu-id="a3d8f-107">有关说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-107">For instructions, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3d8f-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="a3d8f-108">Prerequisites</span></span>  
 <span data-ttu-id="a3d8f-109">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a3d8f-110">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a><span data-ttu-id="a3d8f-111">向发送端口组添加发送端口</span><span class="sxs-lookup"><span data-stu-id="a3d8f-111">To add a send port to a send port group</span></span>  
  
1. <span data-ttu-id="a3d8f-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a3d8f-113">在控制台树中，展开要在其中将发送端口添加到发送端口组的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-113">In the console tree, expand the BizTalk group and the BizTalk application in which you want to add a send port to a send port group.</span></span>  
  
3. <span data-ttu-id="a3d8f-114">单击**发送端口组**，右键单击发送端口组，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-114">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="a3d8f-115">在**发送端口**，单击下拉列表下的**名称**，然后单击要添加到发送端口组的发送端口。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-115">In **Send ports**, click the drop-down list under **Name**, and click the send port to add to the send port group.</span></span> <span data-ttu-id="a3d8f-116">对每个要添加到该组的发送端口重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-116">Repeat for each send port you want to add to the group.</span></span> <span data-ttu-id="a3d8f-117">若要创建新的发送端口并将其添加，请单击**\<新发送端口...\>**  ，然后按照中的说明[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-117">To create a new send port and add it, click **\<New send port…\>** and then follow the instructions in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
5. <span data-ttu-id="a3d8f-118">完成向发送端口组添加发送端口，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a3d8f-118">When finished adding send ports to the send port group, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d8f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3d8f-119">See Also</span></span>  
 <span data-ttu-id="a3d8f-120">[创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="a3d8f-120">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="a3d8f-121">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="a3d8f-121">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)