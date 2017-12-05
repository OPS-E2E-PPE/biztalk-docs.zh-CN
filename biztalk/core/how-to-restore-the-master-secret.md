---
title: "如何还原主密钥 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9241c8d9c5f6e41f47199211d0215c16526951d6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="3a701-102">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="3a701-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="3a701-103">在数据恢复过程中，可能需要还原主密钥以重新使用现有的数据。</span><span class="sxs-lookup"><span data-stu-id="3a701-103">As part of data recovery procedures, you may need to restore the master secret to re-use existing data.</span></span> <span data-ttu-id="3a701-104">若要执行此任务，必须使用同时作为 Windows 管理员和 SSO 管理员的帐户登录主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="3a701-104">In order to perform this task, you must log on to the master secret server with an account that is both a Windows administrator and an SSO administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="3a701-105">使用 MMC 管理单元还原主密钥</span><span class="sxs-lookup"><span data-stu-id="3a701-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="3a701-106">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="3a701-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="3a701-107">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="3a701-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="3a701-108">右键单击**系统**，然后单击**还原机密**。</span><span class="sxs-lookup"><span data-stu-id="3a701-108">Right-click **System**, and then click **Restore Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="3a701-109">使用命令行还原主密钥</span><span class="sxs-lookup"><span data-stu-id="3a701-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="3a701-110">上**启动**菜单上，单击**所有程序**，然后单击**附件**。</span><span class="sxs-lookup"><span data-stu-id="3a701-110">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="3a701-111">右键单击**命令提示符**，然后单击**运行方式...**.</span><span class="sxs-lookup"><span data-stu-id="3a701-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="3a701-112">选择相应的管理员，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a701-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3a701-113">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="3a701-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3a701-114">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="3a701-114">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="3a701-115">类型**ssoconfig-restoreSecret\<还原文件\>**，其中**\<还原文件\>**是路径和主密钥的文件的名称存储中。</span><span class="sxs-lookup"><span data-stu-id="3a701-115">Type **ssoconfig –restoreSecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a701-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3a701-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a701-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a701-117">See Also</span></span>  
 <span data-ttu-id="3a701-118">[如何生成主密钥](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="3a701-118">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="3a701-119">[如何备份主密钥](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="3a701-119">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="3a701-120">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a701-120">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="3a701-121">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="3a701-121">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)