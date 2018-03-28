---
title: 如何备份主密钥 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="1de08-102">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="1de08-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="1de08-103">您可以将主密钥服务器中的主密钥备份到 NTFS 文件系统或可移动媒体（如软盘）上。</span><span class="sxs-lookup"><span data-stu-id="1de08-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="1de08-104">你必须是单一登录管理员和 Windows 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="1de08-104">You must be a Single Sign-On administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="1de08-105">单一登录 (SSO) 系统将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="1de08-105">The Single Sign-On (SSO) system will prompt you for a password.</span></span> <span data-ttu-id="1de08-106">以后若要还原该密钥，则必须提供同一密码。</span><span class="sxs-lookup"><span data-stu-id="1de08-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1de08-107">如果主密钥服务器崩溃和您丢失了密钥，或如果密钥已损坏，你将不能检索凭据数据库中存储数据。</span><span class="sxs-lookup"><span data-stu-id="1de08-107">If the master secret server crashes and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the Credential database.</span></span> <span data-ttu-id="1de08-108">你必须备份的主密钥或风险从凭据数据库丢失数据。</span><span class="sxs-lookup"><span data-stu-id="1de08-108">You must back up the master secret, or you risk losing data from the Credential database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="1de08-109">使用 MMC 管理单元备份主密钥</span><span class="sxs-lookup"><span data-stu-id="1de08-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="1de08-110">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="1de08-110">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="1de08-111">在 ENTSSO Microsoft 管理控制台 (MMC) 管理单元的作用域窗格中，展开**企业单一登录**节点。</span><span class="sxs-lookup"><span data-stu-id="1de08-111">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="1de08-112">右键单击**系统**，然后单击**备份主密钥**。</span><span class="sxs-lookup"><span data-stu-id="1de08-112">Right-click **System**, and then click **Back up Master Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="1de08-113">使用命令行备份主密钥</span><span class="sxs-lookup"><span data-stu-id="1de08-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="1de08-114">上**启动**菜单上，单击**程序**，然后单击**附件**。</span><span class="sxs-lookup"><span data-stu-id="1de08-114">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="1de08-115">右键单击 **命令提示符**, ，然后单击 **运行另存为...**。</span><span class="sxs-lookup"><span data-stu-id="1de08-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="1de08-116">选择相应的管理员，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="1de08-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1de08-117">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1de08-117">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1de08-118">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1de08-118">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1de08-119">类型`ssoconfig –backupsecret <backup file>`，其中*\<备份文件 >*是路径和其中主密钥将备份，例如，文件的名称`A:\ssobackup.bak`。</span><span class="sxs-lookup"><span data-stu-id="1de08-119">Type `ssoconfig –backupsecret <backup file>`, where *\<backup file>* is the path and name of the file where the master secret will be backed up, for example, `A:\ssobackup.bak`.</span></span>  
  
5.  <span data-ttu-id="1de08-120">提供一个密码来帮助保护此文件。</span><span class="sxs-lookup"><span data-stu-id="1de08-120">Provide a password to help protect this file.</span></span>  
  
     <span data-ttu-id="1de08-121">然后，将提示您确认该密码并提供密码提示以帮助您记起此密码。</span><span class="sxs-lookup"><span data-stu-id="1de08-121">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1de08-122">您必须将该备份文件保存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="1de08-122">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de08-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1de08-123">See Also</span></span>  
 <span data-ttu-id="1de08-124">[如何生成主密钥](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="1de08-124">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="1de08-125">[如何还原主密钥](../esso/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="1de08-125">[How to Restore the Master Secret](../esso/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="1de08-126">[主密钥服务器](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="1de08-126">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="1de08-127">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="1de08-127">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)