---
title: 如何更改主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e588e4ea7ac91b5f4ff8124b33b3611e91e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387003"
---
# <a name="how-to-change-the-master-secret-server"></a><span data-ttu-id="c3324-102">如何更改主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="c3324-102">How to Change the Master Secret Server</span></span>
<span data-ttu-id="c3324-103">在设置主密钥服务器并配置 SSO 数据库后，可以更改主密钥服务器，如果在原始主服务器失败，并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="c3324-103">After you set up the master secret server and configure the SSO database, you can change the master secret server if the original master secret server fails and cannot be recovered.</span></span> <span data-ttu-id="c3324-104">若要更改主密钥服务器，你需要升级 SSO 服务器成为主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="c3324-104">To change the master secret server, you need to promote an SSO server to become the master secret server.</span></span>  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a><span data-ttu-id="c3324-105">若要更改主密钥服务器使用 mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="c3324-105">To change the Master Secret Server using the MMC Snap-in</span></span>  
  
1.  <span data-ttu-id="c3324-106">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="c3324-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="c3324-107">在作用域窗格中，右键单击**系统**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c3324-107">In the scope pane, right click **System**, and then click **Properties**.</span></span> <span data-ttu-id="c3324-108">主服务器上将显示**常规**选项卡**系统属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="c3324-108">The Master secret server is displayed on the **General** tab of the **System Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="c3324-109">单击**更改**以选择新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="c3324-109">Click **Change** to select a new Master secret server.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c3324-110">当使用 MMC 管理单元更改主密钥服务器，必须在主密钥服务器上执行操作。</span><span class="sxs-lookup"><span data-stu-id="c3324-110">When using the MMC Snap-in to change the Master Secret Server, the operation must be performed on the Master Secret Server.</span></span> <span data-ttu-id="c3324-111">不能更改主密钥服务器不是主密钥服务器的计算机使用 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="c3324-111">It is not possible to change the Master Secret Server using the MMC Snap-in from a computer that is not the Master Secret Server.</span></span>  
  
4.  <span data-ttu-id="c3324-112">登录到新的主服务器，将主密钥还原到新的主注册表机密密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="c3324-112">Logon to the new Master secret server to restore the Master secret to the registry of the new Master secret server.</span></span>  
  
5.  <span data-ttu-id="c3324-113">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="c3324-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
6.  <span data-ttu-id="c3324-114">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="c3324-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="c3324-115">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="c3324-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
7.  <span data-ttu-id="c3324-116">重新启动新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="c3324-116">Restart the new Master Secret Server.</span></span>  
  
8.  <span data-ttu-id="c3324-117">类型**ssoconfig-restoreSecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。</span><span class="sxs-lookup"><span data-stu-id="c3324-117">Type **ssoconfig –restoreSecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="c3324-118">主密钥存储在注册表中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="c3324-118">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="c3324-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="c3324-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3324-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c3324-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a><span data-ttu-id="c3324-121">若要单一登录将服务器提升为使用命令行的主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="c3324-121">To promote a Single Sign-On Server to master secret server using the command line</span></span>  
  
1.  <span data-ttu-id="c3324-122">创建一个包含你想要升级到主密钥服务器的 SSO 服务器的名称的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="c3324-122">Create an XML file that includes the name of the SSO server you want to promote to master secret server.</span></span> <span data-ttu-id="c3324-123">例如，</span><span class="sxs-lookup"><span data-stu-id="c3324-123">For example,</span></span>  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c3324-124">若要更改主密钥服务器不是主密钥服务器的计算机，请确保指定的 XML 文件包含仅的主密钥服务器名称。</span><span class="sxs-lookup"><span data-stu-id="c3324-124">To change the Master Secret Server from a computer that is not the Master Secret Server make sure that the specified XML file contains only the Master Secret Server name.</span></span> <span data-ttu-id="c3324-125">具体而言，它不应包含 SSO 管理员 XML 标记或**ssomanage-updatedb**操作将失败。</span><span class="sxs-lookup"><span data-stu-id="c3324-125">Specifically, it should not contain the SSO Administrators XML tag or the **ssomanage -updatedb** operation will fail.</span></span>  
  
2.  <span data-ttu-id="c3324-126">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="c3324-126">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3.  <span data-ttu-id="c3324-127">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="c3324-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="c3324-128">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="c3324-128">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="c3324-129">类型**ssomanage – updatedb** \<**更新文件**\>，其中\<**更新文件**\>是 XML 文件的名称步骤 1 中创建。</span><span class="sxs-lookup"><span data-stu-id="c3324-129">Type **ssomanage –updatedb** \<**update file**\>, where \<**update file**\> is the name of the XML file you create in step 1.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3324-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c3324-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="c3324-131">重新启动主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="c3324-131">Restart the Master Secret Server.</span></span>  
  
6.  <span data-ttu-id="c3324-132">类型**ssoconfig-restoresecret\<还原文件\>**，其中**\<还原文件\>** 是路径和主密钥的文件的名称存储中。</span><span class="sxs-lookup"><span data-stu-id="c3324-132">Type **ssoconfig –restoresecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="c3324-133">主密钥存储在注册表中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="c3324-133">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="c3324-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span><span class="sxs-lookup"><span data-stu-id="c3324-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3324-135">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c3324-135">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3324-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3324-136">See Also</span></span>  
 <span data-ttu-id="c3324-137">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3324-137">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 <span data-ttu-id="c3324-138">[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="c3324-138">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 <span data-ttu-id="c3324-139">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="c3324-139">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="c3324-140">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="c3324-140">Using SSO</span></span>](../core/using-sso.md)