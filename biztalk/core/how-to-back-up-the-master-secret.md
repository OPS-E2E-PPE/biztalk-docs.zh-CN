---
title: 如何备份主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e38ebeb861d26bfdb31819ea1d94d830bf58fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387095"
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="cc43d-102">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="cc43d-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="cc43d-103">你可以备份中的主密钥对主密钥服务器到 NTFS 文件系统或可移动媒体，如软盘。</span><span class="sxs-lookup"><span data-stu-id="cc43d-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="cc43d-104">您必须是单一登录管理员和 Windows 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="cc43d-104">You must be a Single Sign-On Administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="cc43d-105">SSO 系统将提示您输入密码。</span><span class="sxs-lookup"><span data-stu-id="cc43d-105">The SSO system will prompt you for a password.</span></span> <span data-ttu-id="cc43d-106">若要还原该密钥更高版本，必须指定相同的密码。</span><span class="sxs-lookup"><span data-stu-id="cc43d-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cc43d-107">如果主密钥服务器失败，并且丢失了密钥，或者密钥损坏，您将不能检索存储在 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="cc43d-107">If the master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="cc43d-108">您必须备份主密钥或风险会丢失 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="cc43d-108">You must back up the master secret, or you risk losing data from the SSO database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="cc43d-109">若要备份主密钥使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="cc43d-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="cc43d-110">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="cc43d-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="cc43d-111">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="cc43d-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="cc43d-112">右键单击**系统**，然后单击**备份密钥**。</span><span class="sxs-lookup"><span data-stu-id="cc43d-112">Right-click **System**, and then click **Backup Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="cc43d-113">若要备份主密钥使用命令行</span><span class="sxs-lookup"><span data-stu-id="cc43d-113">To back up the master secret using the command line</span></span>  
  
1. <span data-ttu-id="cc43d-114">上**启动**菜单上，单击**所有程序**，然后单击**附件**。</span><span class="sxs-lookup"><span data-stu-id="cc43d-114">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="cc43d-115">右键单击**命令提示符**，然后单击**运行方式...**.</span><span class="sxs-lookup"><span data-stu-id="cc43d-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2. <span data-ttu-id="cc43d-116">选择合适的管理员，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc43d-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="cc43d-117">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="cc43d-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cc43d-118">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="cc43d-118">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="cc43d-119">类型 \* \* ssoconfig-backupSecret \*\<备份文件\>\*\*<em>，其中 \*\<备份文件\></em>是路径和要备份主密钥的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cc43d-119">Type \*\*ssoconfig –backupSecret \*\<backup file\>\*\*<em>, where \*\<backup file\></em> is the path and name of the file where the master secret will be backed up.</span></span> <span data-ttu-id="cc43d-120">例如，A:\ssobackup.bak</span><span class="sxs-lookup"><span data-stu-id="cc43d-120">For example, A:\ssobackup.bak</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cc43d-121">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="cc43d-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="cc43d-122">提供一个密码来保护此文件。</span><span class="sxs-lookup"><span data-stu-id="cc43d-122">Provide a password to protect this file.</span></span> <span data-ttu-id="cc43d-123">若要确认该密码并提供密码提示，以帮助您记住此密码，系统将提示您。</span><span class="sxs-lookup"><span data-stu-id="cc43d-123">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc43d-124">必须保存并将备份文件存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="cc43d-124">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc43d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc43d-125">See Also</span></span>  
 <span data-ttu-id="cc43d-126">[如何生成主密钥](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="cc43d-126">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="cc43d-127">[如何还原主密钥](../core/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="cc43d-127">[How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="cc43d-128">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc43d-128">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="cc43d-129">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="cc43d-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)