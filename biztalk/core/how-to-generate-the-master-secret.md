---
title: 如何生成主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41e7f000dbb53a054259ba18f5c1d118531c8138
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978334"
---
# <a name="how-to-generate-the-master-secret"></a><span data-ttu-id="4ba4f-102">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="4ba4f-102">How to Generate the Master Secret</span></span>
<span data-ttu-id="4ba4f-103">必须具有对主密钥服务器的管理员权限才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-103">You must have administrator rights on the master secret server in order to perform this task.</span></span> <span data-ttu-id="4ba4f-104">此外，您还必须从主密钥服务器执行此任务。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-104">In addition, you must perform this task from the master secret server.</span></span>  
  
 <span data-ttu-id="4ba4f-105">安装企业单一登录的第一台服务器就是主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-105">The first server where you install Enterprise Single Sign-On becomes the master secret server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ba4f-106">在 SSO 系统中只能有一台主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-106">There can be only one master secret server in your SSO system.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="4ba4f-107">当企业单一登录安装的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装中，主密钥生成配置向导的一部分。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-107">When Enterprise Single Sign-On is installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, the master secret is generated as part of the Configuration Wizard.</span></span> <span data-ttu-id="4ba4f-108">如果希望生成新的主密钥，则只需要执行此任务。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-108">You will only need to perform this task if you want to generate a new master secret.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="4ba4f-109">使用 MMC 管理单元生成主密钥</span><span class="sxs-lookup"><span data-stu-id="4ba4f-109">To generate the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="4ba4f-110">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="4ba4f-111">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="4ba4f-112">右键单击**系统**，然后单击**生成机密**。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-112">Right-click **System**, and then click **Generate Secret**.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a><span data-ttu-id="4ba4f-113">使用命令行生成主密钥</span><span class="sxs-lookup"><span data-stu-id="4ba4f-113">To generate the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="4ba4f-114">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="4ba4f-115">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4ba4f-116">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-116">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="4ba4f-117">类型**ssoconfig-generateSecret \<*备份文件*\>**，其中\<*备份文件*\>的名称使用包含主密钥的文件。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-117">Type **ssoconfig –generateSecret \<*backup file*\>**, where \<*backup file*\> is the name of the file that contains the master secret.</span></span>  
  
     <span data-ttu-id="4ba4f-118">此时，系统将提示您输入密码以保护刚刚创建的文件。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-118">You will be prompted to enter a password to protect the file you just created.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ba4f-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4ba4f-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba4f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba4f-120">See Also</span></span>  
 <span data-ttu-id="4ba4f-121">[如何备份主密钥](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="4ba4f-121">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="4ba4f-122">[主密钥服务器](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ba4f-122">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="4ba4f-123">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="4ba4f-123">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)