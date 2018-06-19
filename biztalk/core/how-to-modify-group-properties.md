---
title: 如何修改组属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a191011b6824086e26c72ce5e5a182a167ca0e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254861"
---
# <a name="how-to-modify-group-properties"></a><span data-ttu-id="b1ef7-102">如何修改组属性</span><span class="sxs-lookup"><span data-stu-id="b1ef7-102">How to Modify Group Properties</span></span>
<span data-ttu-id="b1ef7-103">此过程可用于为你的 BizTalk 服务器组配置全局属性，以便你可以选择签名证书、 修改缓存刷新间隔，并确定 BizTalk Server 将如何处理大消息。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-103">You can use this procedure to configure global properties for your BizTalk Server group so that you can select a signing certificate, modify the cache refresh interval, and determine how BizTalk Server will handle large messages.</span></span> <span data-ttu-id="b1ef7-104">有关 BizTalk Server 组属性的详细信息，请参阅[BizTalk 组](../core/biztalk-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-104">For more information about BizTalk Server group properties, see [BizTalk Groups](../core/biztalk-groups.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b1ef7-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="b1ef7-105">Prerequisites</span></span>  
 <span data-ttu-id="b1ef7-106">若要执行此过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-106">To perform this procedure, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-group-properties"></a><span data-ttu-id="b1ef7-107">若要配置 BizTalk 组属性</span><span class="sxs-lookup"><span data-stu-id="b1ef7-107">To configure BizTalk group properties</span></span>  
  
1.  <span data-ttu-id="b1ef7-108">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b1ef7-109">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**BizTalk 组**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-109">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b1ef7-110">在**组属性**对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1ef7-110">In the **Group Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b1ef7-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b1ef7-111">Use this</span></span>|<span data-ttu-id="b1ef7-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b1ef7-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b1ef7-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-113">**Name**</span></span>|<span data-ttu-id="b1ef7-114">键入组名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-114">Type the group name.</span></span> <span data-ttu-id="b1ef7-115">组名称不能超过 128 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-115">The group name cannot exceed 128 characters in length.</span></span> <span data-ttu-id="b1ef7-116">此框中的名称旁边将出现**组**节点在控制台树中，以及服务器名称和 BizTalk 管理数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-116">The name in this box appears next to the **Group** node in the console tree, along with the server name and the BizTalk Management database name.</span></span>|  
    |<span data-ttu-id="b1ef7-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-117">**Server**</span></span>|<span data-ttu-id="b1ef7-118">将显示在其中以物理方式存储 BizTalk 管理数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-118">Displays the server on which the BizTalk Management database is physically stored.</span></span>|  
    |<span data-ttu-id="b1ef7-119">**数据库**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-119">**Database**</span></span>|<span data-ttu-id="b1ef7-120">显示 BizTalk 管理数据库的此组设置存储的所有配置。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-120">Displays the BizTalk Management database on which all configuration settings for this group are stored.</span></span>|  
    |<span data-ttu-id="b1ef7-121">**SSO 服务器名称**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-121">**SSO Server name**</span></span>|<span data-ttu-id="b1ef7-122">键入此计算机将使用用于存储和访问特定于适配器的信息的企业单一登录 (SSO) 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-122">Type the name of the Enterprise Single Sign-On (SSO) server that this computer will use to store and access adapter-specific information.</span></span> <span data-ttu-id="b1ef7-123">这是用于连接到 SSO 数据库的 SSO 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-123">This is the name of the SSO server used to connect to the SSO database.</span></span>|  
    |<span data-ttu-id="b1ef7-124">**BizTalk 管理员组**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-124">**BizTalk Administrator Group**</span></span>|<span data-ttu-id="b1ef7-125">显示具有在安装后管理 BizTalk Server 环境权限的 Administrators 组的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-125">Displays the name of the administrators group that has rights to manage the BizTalk Server environment after installation.</span></span>|  
    |<span data-ttu-id="b1ef7-126">**BizTalk Operators 组**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-126">**BizTalk Operators Group**</span></span>|<span data-ttu-id="b1ef7-127">显示有权查看配置、 运行查询，以及执行计算机维护和基本应用程序监视操作员组的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-127">Displays the name of the operators group that has rights to view configuration, run queries, and perform computer maintenance and basic application monitoring.</span></span>|  
    |<span data-ttu-id="b1ef7-128">**BizTalk Server B2B Operators**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-128">**BizTalk Server B2B Operators**</span></span>|<span data-ttu-id="b1ef7-129">显示 B2B operators 组的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-129">Displays the name of the B2B operators group.</span></span>|  
  
4.  <span data-ttu-id="b1ef7-130">上**数据库**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1ef7-130">On the **Databases** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b1ef7-131">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b1ef7-131">Use this</span></span>|<span data-ttu-id="b1ef7-132">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b1ef7-132">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b1ef7-133">**数据库**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-133">**Databases**</span></span>|<span data-ttu-id="b1ef7-134">显示配置过程中指定的应用程序中的所有数据库及其所在服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-134">Displays the names of all databases in the application and the servers on which they reside, as specified during configuration.</span></span>|  
  
5.  <span data-ttu-id="b1ef7-135">上**证书**选项卡上，执行以下操作，，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="b1ef7-135">On the **Certificate** tab, do the following, and then click **OK**:</span></span>  
  
    |<span data-ttu-id="b1ef7-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b1ef7-136">Use this</span></span>|<span data-ttu-id="b1ef7-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b1ef7-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b1ef7-138">**公用名**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-138">**Common Name**</span></span>|<span data-ttu-id="b1ef7-139">显示所选证书的说明。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-139">Displays a description of the selected certificate.</span></span>|  
    |<span data-ttu-id="b1ef7-140">**指纹**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-140">**Thumbprint**</span></span>|<span data-ttu-id="b1ef7-141">显示用于对此组的出站消息进行数字签名的私匙证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-141">Displays the thumbprint of the private key certificate that is used to digitally sign outbound messages from this group.</span></span> <span data-ttu-id="b1ef7-142">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-142">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
    |<span data-ttu-id="b1ef7-143">**删除证书**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-143">**Remove certificate**</span></span>|<span data-ttu-id="b1ef7-144">单击此项可删除所显示证书。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-144">Click to remove the displayed certificate.</span></span>|  
    |<span data-ttu-id="b1ef7-145">**浏览**</span><span class="sxs-lookup"><span data-stu-id="b1ef7-145">**Browse**</span></span>|<span data-ttu-id="b1ef7-146">单击此项可显示**选择证书**对话框中，你在其中选择想要使用与组的当前用户或个人存储区的签名证书。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-146">Click to display the **Select Certificate** dialog box, where you select the signature certificate for the current user or personal store you want to use with the group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1ef7-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1ef7-147">See Also</span></span>  
 <span data-ttu-id="b1ef7-148">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="b1ef7-148">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="b1ef7-149">[BizTalk 组](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="b1ef7-149">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="b1ef7-150">[如何将服务器添加到组](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="b1ef7-150">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="b1ef7-151">[如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="b1ef7-151">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 [<span data-ttu-id="b1ef7-152">如何从组中删除服务器</span><span class="sxs-lookup"><span data-stu-id="b1ef7-152">How to Remove a Server from a Group</span></span>](../core/how-to-remove-a-server-from-a-group.md)