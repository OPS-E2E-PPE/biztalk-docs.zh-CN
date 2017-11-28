---
title: "如何备份 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-bam-portal"></a><span data-ttu-id="5fdfc-102">如何备份 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="5fdfc-102">How to Back Up the BAM Portal</span></span>
<span data-ttu-id="5fdfc-103">如果您使用业务活动监视 (BAM)，则作为备份 BizTalk Server 工作的一部分，必须备份 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-103">If you are using Business Activity Monitoring (BAM), you must back up the BAM portal as part of backing up your BizTalk server.</span></span> <span data-ttu-id="5fdfc-104">如果没有使用 BAM，则此过程为可选。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="5fdfc-105">备份过程的某些部分会因您所备份的 Internet 信息服务 (IIS) 版本的不同而有显著的不同。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-105">Certain portions of the backup process differ markedly depending on which version of Internet Information Services (IIS) you are backing up.</span></span> <span data-ttu-id="5fdfc-106">IIS 6.0 允许您分别备份应用程序池配置和网站配置，您可以使用密码对配置备份文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-106">IIS 6.0 permits you to back up the application pool configuration and web site configuration separately, and you can encrypt the configuration backup files using a password.</span></span>  
  
 <span data-ttu-id="5fdfc-107">IIS 7.0 将应用程序池和网站的配置设置保存到单个文件，applicationHost.config。未加密的 applicationHost.config 文件，但帐户密码，如果有的话，进行加密的文件中。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-107">IIS 7.0 saves configuration settings for both the application pool and web site to a single file, applicationHost.config. The applicationHost.config file is not encrypted, but account passwords, if any, are encrypted in the file.</span></span> <span data-ttu-id="5fdfc-108">使用你要备份的计算机中的证书执行加密。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-108">Encryption is performed using the certificate from the computer you are backing up.</span></span> <span data-ttu-id="5fdfc-109">此配置不能还原到它源自以外的计算机。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-109">This configuration cannot be restored to a computer other than the one from which it originated.</span></span>  
  
 <span data-ttu-id="5fdfc-110">不能备份 BAM 门户配置过程，使用 IIS 7.0 管理器;必须使用**Appcmd.exe**命令行工具。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-110">You cannot back up the BAM portal configuration using the IIS 7.0 Manager; you must use the **Appcmd.exe** command-line tool.</span></span> <span data-ttu-id="5fdfc-111">有关 Appcmd 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-111">For more information about Appcmd, see [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5fdfc-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="5fdfc-112">Prerequisites</span></span>  
 <span data-ttu-id="5fdfc-113">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-113">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a><span data-ttu-id="5fdfc-114">若要备份 BAM 门户 (IIS 7.0)</span><span class="sxs-lookup"><span data-stu-id="5fdfc-114">To back up the BAM portal (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="5fdfc-115">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-115">Click **Start**, and then click **Run**.</span></span>  
  
2.  <span data-ttu-id="5fdfc-116">在运行对话框中，在打开的框中，键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-116">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="5fdfc-117">*Accountname*必须是本地计算机上 administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-117">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
3.  <span data-ttu-id="5fdfc-118">出现提示时，键入的密码*accountname*，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-118">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="5fdfc-119">类型`cd %windir%\system32\inetsrv`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-119">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="5fdfc-120">类型`appcmd add backup “` *backupname*`”`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-120">Type `appcmd add backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="5fdfc-121">无需输入备份名称。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-121">You do not have to enter a backup name.</span></span> <span data-ttu-id="5fdfc-122">如果未设置，它将自动生成。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-122">If not set, it will be autogenerated.</span></span> <span data-ttu-id="5fdfc-123">自动生成的备份名称的一个示例是“20090224T123302”。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-123">An example of an autogenerated backup name is “20090224T123302.”</span></span>  
  
     <span data-ttu-id="5fdfc-124">若要查看现有配置备份的列表，请键入`appcmd list backup`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-124">To see a list of existing configuration backups, type `appcmd list backup`, and then press **Enter**.</span></span> <span data-ttu-id="5fdfc-125">由用户创建的备份保存在**%windir%\system32\inetsrv\backup**目录。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-125">Backups created by the user are saved in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="5fdfc-126">若要查看提供的备份选项的列表**appcmd.exe**，类型`appcmd backup /?`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5fdfc-126">To see a list of the backup options provided by **appcmd.exe**, type `appcmd backup /?`, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fdfc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fdfc-127">See Also</span></span>  
 <span data-ttu-id="5fdfc-128">[备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="5fdfc-128">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 <span data-ttu-id="5fdfc-129">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="5fdfc-129">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="5fdfc-130">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="5fdfc-130">BAM Portal</span></span>](../core/bam-portal.md)