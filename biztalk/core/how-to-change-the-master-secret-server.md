---
title: "如何更改主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4676db07025b4395d58df7c24252769ba65ecfb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-master-secret-server"></a><span data-ttu-id="b6d03-102">如何更改主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="b6d03-102">How to Change the Master Secret Server</span></span>
<span data-ttu-id="b6d03-103">在设置主密钥服务器并配置 SSO 数据库后，如果原始的主密钥服务器发生故障并且无法恢复，则可以更改主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-103">After you set up the master secret server and configure the SSO database, you can change the master secret server if the original master secret server fails and cannot be recovered.</span></span> <span data-ttu-id="b6d03-104">若要更改主密钥服务器，则需要将 SSO 服务器升级为主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-104">To change the master secret server, you need to promote an SSO server to become the master secret server.</span></span>  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a><span data-ttu-id="b6d03-105">使用 MMC 管理单元更改主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="b6d03-105">To change the Master Secret Server using the MMC Snap-in</span></span>  
  
1.  <span data-ttu-id="b6d03-106">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="b6d03-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="b6d03-107">在作用域窗格中，右键单击**系统**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b6d03-107">In the scope pane, right click **System**, and then click **Properties**.</span></span> <span data-ttu-id="b6d03-108">主服务器显示在**常规**选项卡**系统属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="b6d03-108">The Master secret server is displayed on the **General** tab of the **System Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="b6d03-109">单击**更改**以选择新的主服务器密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-109">Click **Change** to select a new Master secret server.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b6d03-110">使用 MMC 管理单元更改主密钥服务器时，必须在主密钥服务器上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b6d03-110">When using the MMC Snap-in to change the Master Secret Server, the operation must be performed on the Master Secret Server.</span></span> <span data-ttu-id="b6d03-111">无法通过不是主密钥服务器的计算机使用 MMC 管理单元更改主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-111">It is not possible to change the Master Secret Server using the MMC Snap-in from a computer that is not the Master Secret Server.</span></span>  
  
4.  <span data-ttu-id="b6d03-112">登录到新的主密钥服务器，将主密钥还原到新的主密钥服务器的注册表中。</span><span class="sxs-lookup"><span data-stu-id="b6d03-112">Logon to the new Master secret server to restore the Master secret to the registry of the new Master secret server.</span></span>  
  
5.  <span data-ttu-id="b6d03-113">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="b6d03-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
6.  <span data-ttu-id="b6d03-114">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b6d03-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b6d03-115">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="b6d03-115">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
7.  <span data-ttu-id="b6d03-116">重新启动新的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-116">Restart the new Master Secret Server.</span></span>  
  
8.  <span data-ttu-id="b6d03-117">类型**ssoconfig-restoreSecret\<还原文件 >**，其中**\<还原文件 >**是路径和主密钥的存储位置的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b6d03-117">Type **ssoconfig –restoreSecret \<restore file>**, where **\<restore file>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="b6d03-118">主密钥存储在注册表中，位置为：</span><span class="sxs-lookup"><span data-stu-id="b6d03-118">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="b6d03-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="b6d03-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6d03-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="b6d03-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a><span data-ttu-id="b6d03-121">使用命令行将单一登录服务器升级为主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="b6d03-121">To promote a Single Sign-On Server to master secret server using the command line</span></span>  
  
1.  <span data-ttu-id="b6d03-122">创建一个包含要升级为主密钥服务器的 SSO 服务器名称的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6d03-122">Create an XML file that includes the name of the SSO server you want to promote to master secret server.</span></span> <span data-ttu-id="b6d03-123">例如：</span><span class="sxs-lookup"><span data-stu-id="b6d03-123">For example,</span></span>  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b6d03-124">若要从不是主密钥服务器的计算机更改主密钥服务器，请确保指定的 XML 文件仅包含主密钥服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b6d03-124">To change the Master Secret Server from a computer that is not the Master Secret Server make sure that the specified XML file contains only the Master Secret Server name.</span></span> <span data-ttu-id="b6d03-125">具体而言，它不应包含的 SSO 管理员 XML 标记或**ssomanage updatedb**操作将失败。</span><span class="sxs-lookup"><span data-stu-id="b6d03-125">Specifically, it should not contain the SSO Administrators XML tag or the **ssomanage -updatedb** operation will fail.</span></span>  
  
2.  <span data-ttu-id="b6d03-126">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="b6d03-126">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3.  <span data-ttu-id="b6d03-127">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b6d03-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b6d03-128">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="b6d03-128">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="b6d03-129">类型**ssomanage-updatedb** \<**更新文件**>，其中\<**更新文件**> 是你在步骤 1 中创建的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b6d03-129">Type **ssomanage –updatedb** \<**update file**>, where \<**update file**> is the name of the XML file you create in step 1.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6d03-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="b6d03-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="b6d03-131">重新启动主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d03-131">Restart the Master Secret Server.</span></span>  
  
6.  <span data-ttu-id="b6d03-132">类型**ssoconfig-restoresecret\<还原文件 >**，其中**\<还原文件 >**是路径和主密钥的存储位置的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b6d03-132">Type **ssoconfig –restoresecret \<restore file>**, where **\<restore file>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="b6d03-133">主密钥存储在注册表中，位置为：</span><span class="sxs-lookup"><span data-stu-id="b6d03-133">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="b6d03-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span><span class="sxs-lookup"><span data-stu-id="b6d03-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6d03-135">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="b6d03-135">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d03-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d03-136">See Also</span></span>  
 <span data-ttu-id="b6d03-137">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="b6d03-137">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 <span data-ttu-id="b6d03-138">[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="b6d03-138">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 <span data-ttu-id="b6d03-139">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6d03-139">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="b6d03-140">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="b6d03-140">Using SSO</span></span>](../core/using-sso.md)