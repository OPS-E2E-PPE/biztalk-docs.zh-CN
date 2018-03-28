---
title: 如何还原主密钥 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="49143-102">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="49143-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="49143-103">作为数据恢复过程的一部分，你可能需要还原主密钥可以重复使用现有数据。</span><span class="sxs-lookup"><span data-stu-id="49143-103">As part of data recovery procedures, you might have to restore the master secret to reuse existing data.</span></span> <span data-ttu-id="49143-104">若要执行此任务，你必须使用的是 Windows 管理员和单一登录 (SSO) 管理员的帐户登录到的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="49143-104">To perform this task, you must log on to the master secret server by using an account that is both a Windows administrator and a Single Sign-On (SSO) administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="49143-105">使用 MMC 管理单元还原主密钥</span><span class="sxs-lookup"><span data-stu-id="49143-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="49143-106">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="49143-106">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="49143-107">在 ENTSSO Microsoft 管理控制台 (MMC) 管理单元的作用域窗格中，展开**企业单一登录**节点。</span><span class="sxs-lookup"><span data-stu-id="49143-107">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="49143-108">右键单击**系统**，然后单击**还原主密钥**。</span><span class="sxs-lookup"><span data-stu-id="49143-108">Right-click **System**, and then click **Restore Master Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="49143-109">使用命令行还原主密钥</span><span class="sxs-lookup"><span data-stu-id="49143-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="49143-110">上**启动**菜单上，单击**程序**，然后单击**附件**。</span><span class="sxs-lookup"><span data-stu-id="49143-110">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="49143-111">右键单击 **命令提示符**, ，然后单击 **运行另存为...**。</span><span class="sxs-lookup"><span data-stu-id="49143-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="49143-112">选择相应的管理员，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="49143-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="49143-113">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="49143-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="49143-114">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="49143-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="49143-115">类型`ssoconfig –restoresecret <restore file>`，其中*\<还原文件 >*是路径和主密钥的存储位置的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="49143-115">Type `ssoconfig –restoresecret <restore file>`, where *\<restore file>* is the path and name of the file where the master secret is stored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49143-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49143-116">See Also</span></span>  
 <span data-ttu-id="49143-117">[如何生成主密钥](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="49143-117">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="49143-118">[如何备份主密钥](../esso/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="49143-118">[How to Back Up the Master Secret](../esso/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="49143-119">[主密钥服务器](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="49143-119">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="49143-120">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="49143-120">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)