---
title: "如何恢复 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 781191047e0ee99b0000c7b773d46aa035a7e1d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-bam-portal"></a><span data-ttu-id="15188-102">如何恢复 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="15188-102">How to Recover the BAM Portal</span></span>
<span data-ttu-id="15188-103">如果在使用业务活动监视 (BAM)，则必须在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时恢复 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="15188-103">If you are using Business Activity Monitoring (BAM), you must recover the BAM portal as a part of recovering your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="15188-104">如果没有使用 BAM，则此过程为可选。</span><span class="sxs-lookup"><span data-stu-id="15188-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="15188-105">根据 IIS 的版本使用以便恢复 BAM 门户配置过程有很大不同。</span><span class="sxs-lookup"><span data-stu-id="15188-105">The procedure for recovering the BAM portal configuration differs considerably depending on which version of IIS you are using.</span></span> <span data-ttu-id="15188-106">在还原 IIS 7 的配置时，你使用**Appcmd.exe**，和还原整个默认网站，而不仅仅是 BAM 门户的配置。</span><span class="sxs-lookup"><span data-stu-id="15188-106">When you restore the configuration for IIS 7, you use **Appcmd.exe**, and you restore the configuration for the entire default Web site, not just the BAM portal.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15188-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="15188-107">Prerequisites</span></span>  
 <span data-ttu-id="15188-108">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="15188-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a><span data-ttu-id="15188-109">若要恢复的 BAM 门户配置 (IIS 7.0)</span><span class="sxs-lookup"><span data-stu-id="15188-109">To recover the BAM portal configuration (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="15188-110">在运行对话框中，在打开的框中，键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="15188-110">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="15188-111">*Accountname*必须是本地计算机上 administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="15188-111">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
2.  <span data-ttu-id="15188-112">出现提示时，键入的密码*accountname*，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="15188-112">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="15188-113">类型`cd %windir%\system32\inetsrv`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="15188-113">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="15188-114">类型`appcmd restore backup “` *backupname*`”`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="15188-114">Type `appcmd restore backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="15188-115">*Backupname*是先前使用创建的备份名称**Appcmd.exe**。</span><span class="sxs-lookup"><span data-stu-id="15188-115">*Backupname* is the name of a backup you previously created using **Appcmd.exe**.</span></span> <span data-ttu-id="15188-116">此备份必须存在于**%windir%\system32\inetsrv\backup**目录。</span><span class="sxs-lookup"><span data-stu-id="15188-116">This backup must exist in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="15188-117">备份不能用于还原的其他计算机上创建的密码。</span><span class="sxs-lookup"><span data-stu-id="15188-117">The backup cannot be used to restore passwords created on a different computer.</span></span> <span data-ttu-id="15188-118">如果 BAMAppPool 配置为在不同于默认标识下运行**NetworkService**帐户，您必须单独下, 一步中所述配置的帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="15188-118">If the BAMAppPool is configured to run under an identity other than the default **NetworkService** account, you must configure the account and password separately, as described in the next step.</span></span>  
  
5.  <span data-ttu-id="15188-119">使用**Internet Information Services (IIS) Manager**，选择**应用程序池**中**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="15188-119">Using the **Internet Information Services (IIS) Manager**, select **Application Pools** in the **Connections** pane.</span></span>  
  
6.  <span data-ttu-id="15188-120">在**应用程序池**窗格中，右键单击**BAMAppPool**，然后单击**高级设置**</span><span class="sxs-lookup"><span data-stu-id="15188-120">In the **Application Pools** pane, right-click the **BAMAppPool**, then click **Advanced Settings**</span></span>  
  
7.  <span data-ttu-id="15188-121">在**高级设置**s 对话框中，向下滚动到**进程模型**部分。</span><span class="sxs-lookup"><span data-stu-id="15188-121">In the **Advanced Setting**s dialog, scroll down to the **Process Model** section.</span></span> <span data-ttu-id="15188-122">单击**标识**框。</span><span class="sxs-lookup"><span data-stu-id="15188-122">Click the **Identity** box.</span></span> <span data-ttu-id="15188-123">这将导致一个用于出现在框的右侧的省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="15188-123">This will cause an ellipses button to appear on the right side of the box.</span></span> <span data-ttu-id="15188-124">单击**省略号**按钮。</span><span class="sxs-lookup"><span data-stu-id="15188-124">Click the **ellipses** button.</span></span>  
  
8.  <span data-ttu-id="15188-125">在**应用程序池标识**对话框中，单击**自定义帐户**按钮，然后单击**设置**按钮。</span><span class="sxs-lookup"><span data-stu-id="15188-125">In the **Application Pool Identity** dialog, click the **Custom account** button, then click the **Set** button.</span></span>  
  
9. <span data-ttu-id="15188-126">在**设置凭据**对话框框中，输入帐户名和你想要用于 BAMAppPool 的密码。</span><span class="sxs-lookup"><span data-stu-id="15188-126">In the **Set Credentials** dialog box, enter the account name and password you want to use for the BAMAppPool.</span></span> <span data-ttu-id="15188-127">应输入的帐户名称作为*计算机名称*`\`*accountname*，或*域*`\`*accountname*.</span><span class="sxs-lookup"><span data-stu-id="15188-127">The account name should be entered as *computer name*`\`*accountname*, or *domain*`\`*accountname*.</span></span> <span data-ttu-id="15188-128">单击**确定**关闭**设置凭据**对话框。</span><span class="sxs-lookup"><span data-stu-id="15188-128">Click **OK** to close the **Set Credentials** dialog.</span></span>  
  
10. <span data-ttu-id="15188-129">单击**确定**关闭**应用程序池标识**对话框。</span><span class="sxs-lookup"><span data-stu-id="15188-129">Click **OK** to close the **Application Pool Identity** dialog.</span></span>  
  
11. <span data-ttu-id="15188-130">单击**确定**关闭**高级设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="15188-130">Click **OK** to close the **Advanced Settings** dialog.</span></span>  
  
12. <span data-ttu-id="15188-131">验证**BAMAppPool**在应用程序池的列表中选择。</span><span class="sxs-lookup"><span data-stu-id="15188-131">Verify that the **BAMAppPool** is selected in the list of application pools.</span></span> <span data-ttu-id="15188-132">在**操作**的右侧窗格中**Internet Information Services (IIS) Manager**屏幕上，在**应用程序池任务**，单击**启动**.</span><span class="sxs-lookup"><span data-stu-id="15188-132">In the **Actions** pane on the right of the **Internet Information Services (IIS) Manager** screen, under **Application Pool Tasks**, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15188-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15188-133">See Also</span></span>  
 <span data-ttu-id="15188-134">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="15188-134">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="15188-135">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="15188-135">BAM Portal</span></span>](../core/bam-portal.md)