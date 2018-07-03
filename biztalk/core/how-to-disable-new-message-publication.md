---
title: 禁止发布新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2c46be41fa8dda72e849f756a487b89552621b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974134"
---
# <a name="disable-new-message-publication"></a><span data-ttu-id="a18fe-102">禁止发布新消息</span><span class="sxs-lookup"><span data-stu-id="a18fe-102">Disable New Message Publication</span></span>

## <a name="overview"></a><span data-ttu-id="a18fe-103">概述</span><span class="sxs-lookup"><span data-stu-id="a18fe-103">Overview</span></span>
<span data-ttu-id="a18fe-104">可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来禁止发布新消息。</span><span class="sxs-lookup"><span data-stu-id="a18fe-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console or Windows Management Instrumentation (WMI) to disable new message publication.</span></span> <span data-ttu-id="a18fe-105">在 MessageBox 数据库中禁止发布新消息将使 MessageBox 数据库停止接收新消息。</span><span class="sxs-lookup"><span data-stu-id="a18fe-105">You disable new message publication in the MessageBox database to stop the receipt of new messages by the MessageBox database.</span></span> <span data-ttu-id="a18fe-106">在某些 BizTalk Server 环境中，如果禁止主 MessageBox 数据库发布新消息，则可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="a18fe-106">In some BizTalk Server environments, you can improve performance if you disable new message publication for the master MessageBox database.</span></span> <span data-ttu-id="a18fe-107">禁止发布新消息并不会对 MessageBox 数据库中现有的消息或正在进行中的服务实例产生影响。</span><span class="sxs-lookup"><span data-stu-id="a18fe-107">Disabling new message publication does not affect existing messages in the MessageBox database or service instances that are in progress.</span></span>  
  
 <span data-ttu-id="a18fe-108">有关使用 WMI 禁止发布新消息的信息，请参阅**MSBTS_MsgBoxSetting.DisableNewMessagePublication 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a18fe-108">For information about using WMI to disable new message publication, see the **MSBTS_MsgBoxSetting.DisableNewMessagePublication Property (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a18fe-109">在删除 MessageBox 数据库之前，必须禁用新消息发布功能。</span><span class="sxs-lookup"><span data-stu-id="a18fe-109">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="a18fe-110">有关删除 MessageBox 数据库的信息，请参阅[如何删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md)。</span><span class="sxs-lookup"><span data-stu-id="a18fe-110">For information about deleting a MessageBox database, see [How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a18fe-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="a18fe-111">Prerequisites</span></span>  
 <span data-ttu-id="a18fe-112">管理 MessageBox 数据库的管理员必须具有所需的用户权限。</span><span class="sxs-lookup"><span data-stu-id="a18fe-112">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="a18fe-113">必须具有以下用户权限才能管理 MessageBox 数据库并禁用新消息发布：</span><span class="sxs-lookup"><span data-stu-id="a18fe-113">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="a18fe-114">必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a18fe-114">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="a18fe-115">必须是该数据库所在的计算机的 SQL Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="a18fe-115">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
## <a name="disable-steps"></a><span data-ttu-id="a18fe-116">禁用的步骤</span><span class="sxs-lookup"><span data-stu-id="a18fe-116">Disable steps</span></span>
  
1. <span data-ttu-id="a18fe-117">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a18fe-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a18fe-118">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**消息框**。</span><span class="sxs-lookup"><span data-stu-id="a18fe-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="a18fe-119">在详细信息窗格中，右键单击你想要禁用，，然后单击该 MessageBox 数据库**属性**。</span><span class="sxs-lookup"><span data-stu-id="a18fe-119">In the details pane, right-click the MessageBox database you want to disable, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="a18fe-120">在中**消息框属性**对话框中，选择**禁止发布新消息**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="a18fe-120">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18fe-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a18fe-121">See Also</span></span>  
 <span data-ttu-id="a18fe-122">[管理 MessageBox 数据库](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a18fe-122">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="a18fe-123">[添加新的 MessageBox 数据库](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="a18fe-123">[Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="a18fe-124">[删除 MessageBox 数据库](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="a18fe-124">[Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 [<span data-ttu-id="a18fe-125">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="a18fe-125">The MessageBox Database</span></span>](../core/the-messagebox-database.md)