---
title: "如何备份主密钥 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 185f3ea674015e02cac2bdaa785c2ee06e67db65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="098ab-102">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="098ab-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="098ab-103">您可以将主密钥服务器中的主密钥备份到 NTFS 文件系统或可移动媒体（如软盘）上。</span><span class="sxs-lookup"><span data-stu-id="098ab-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="098ab-104">只有单一登录管理员和 Windows 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="098ab-104">You must be a Single Sign-On Administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="098ab-105">SSO 系统将提示您输入密码。</span><span class="sxs-lookup"><span data-stu-id="098ab-105">The SSO system will prompt you for a password.</span></span> <span data-ttu-id="098ab-106">以后若要还原该密钥，则必须提供同一密码。</span><span class="sxs-lookup"><span data-stu-id="098ab-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="098ab-107">如果主密钥服务器出现故障而且密钥丢失，或者密钥损坏，则将无法检索存储在 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="098ab-107">If the master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="098ab-108">因此必须备份主密钥，否则将面临丢失 SSO 数据库中数据的风险。</span><span class="sxs-lookup"><span data-stu-id="098ab-108">You must back up the master secret, or you risk losing data from the SSO database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="098ab-109">使用 MMC 管理单元备份主密钥</span><span class="sxs-lookup"><span data-stu-id="098ab-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="098ab-110">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="098ab-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="098ab-111">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="098ab-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="098ab-112">右键单击**系统**，然后单击**备份机密**。</span><span class="sxs-lookup"><span data-stu-id="098ab-112">Right-click **System**, and then click **Backup Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="098ab-113">使用命令行备份主密钥</span><span class="sxs-lookup"><span data-stu-id="098ab-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="098ab-114">上**启动**菜单上，单击**所有程序**，然后单击**附件**。</span><span class="sxs-lookup"><span data-stu-id="098ab-114">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="098ab-115">右键单击**命令提示符**，然后单击**运行方式...**.</span><span class="sxs-lookup"><span data-stu-id="098ab-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="098ab-116">选择相应的管理员，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="098ab-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="098ab-117">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="098ab-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="098ab-118">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="098ab-118">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="098ab-119">类型**ssoconfig-backupSecret *\<备份文件\>***，其中*\<备份文件\>*是路径和名称将备份主密钥的文件。</span><span class="sxs-lookup"><span data-stu-id="098ab-119">Type **ssoconfig –backupSecret *\<backup file\>***, where *\<backup file\>* is the path and name of the file where the master secret will be backed up.</span></span> <span data-ttu-id="098ab-120">例如，A:\ssobackup.bak。</span><span class="sxs-lookup"><span data-stu-id="098ab-120">For example, A:\ssobackup.bak</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="098ab-121">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="098ab-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="098ab-122">提供密码以保护此文件。</span><span class="sxs-lookup"><span data-stu-id="098ab-122">Provide a password to protect this file.</span></span> <span data-ttu-id="098ab-123">然后，将提示您确认该密码并提供密码提示以帮助您记起此密码。</span><span class="sxs-lookup"><span data-stu-id="098ab-123">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="098ab-124">您必须将该备份文件保存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="098ab-124">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098ab-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="098ab-125">See Also</span></span>  
 <span data-ttu-id="098ab-126">[如何生成主密钥](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="098ab-126">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="098ab-127">[如何还原主密钥](../core/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="098ab-127">[How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="098ab-128">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="098ab-128">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="098ab-129">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="098ab-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)