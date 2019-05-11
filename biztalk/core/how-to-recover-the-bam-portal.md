---
title: 如何恢复 BAM 门户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7f0d9a813b2a8cee115ba782131c2492ea14fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335595"
---
# <a name="how-to-recover-the-bam-portal"></a><span data-ttu-id="763ae-102">如何恢复 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="763ae-102">How to Recover the BAM Portal</span></span>
<span data-ttu-id="763ae-103">如果使用业务活动监视 (BAM)，你必须恢复 BAM 门户作为恢复的一部分在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="763ae-103">If you are using Business Activity Monitoring (BAM), you must recover the BAM portal as a part of recovering your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="763ae-104">如果您没有使用 BAM，则此过程是可选的。</span><span class="sxs-lookup"><span data-stu-id="763ae-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="763ae-105">恢复 BAM 门户配置的过程大不相同的 IIS 版本根据你使用。</span><span class="sxs-lookup"><span data-stu-id="763ae-105">The procedure for recovering the BAM portal configuration differs considerably depending on which version of IIS you are using.</span></span> <span data-ttu-id="763ae-106">在还原适用于 IIS 7 配置时，使用**Appcmd.exe**，你将还原整个默认网站，而不仅仅是 BAM 门户的配置。</span><span class="sxs-lookup"><span data-stu-id="763ae-106">When you restore the configuration for IIS 7, you use **Appcmd.exe**, and you restore the configuration for the entire default Web site, not just the BAM portal.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="763ae-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="763ae-107">Prerequisites</span></span>  
 <span data-ttu-id="763ae-108">您必须为要执行此过程的管理员组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="763ae-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a><span data-ttu-id="763ae-109">若要恢复 BAM 门户配置 (IIS 7.0)</span><span class="sxs-lookup"><span data-stu-id="763ae-109">To recover the BAM portal configuration (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="763ae-110">在运行对话框中，在打开框中键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="763ae-110">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="763ae-111">*Accountname*必须是本地计算机上 administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="763ae-111">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
2.  <span data-ttu-id="763ae-112">出现提示时，键入的密码*accountname*，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="763ae-112">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="763ae-113">类型`cd %windir%\system32\inetsrv`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="763ae-113">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="763ae-114">类型`appcmd restore backup “` *backupname*`”`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="763ae-114">Type `appcmd restore backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="763ae-115">*Backupname*是以前使用创建的备份名称**Appcmd.exe**。</span><span class="sxs-lookup"><span data-stu-id="763ae-115">*Backupname* is the name of a backup you previously created using **Appcmd.exe**.</span></span> <span data-ttu-id="763ae-116">此备份必须存在于 **%windir%\system32\inetsrv\backup**目录。</span><span class="sxs-lookup"><span data-stu-id="763ae-116">This backup must exist in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="763ae-117">备份不能用于还原的不同计算机上创建的密码。</span><span class="sxs-lookup"><span data-stu-id="763ae-117">The backup cannot be used to restore passwords created on a different computer.</span></span> <span data-ttu-id="763ae-118">如果 BAMAppPool 配置为默认值以外的身份下运行**NetworkService**帐户，您必须在下一步中所述单独配置的帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="763ae-118">If the BAMAppPool is configured to run under an identity other than the default **NetworkService** account, you must configure the account and password separately, as described in the next step.</span></span>  
  
5.  <span data-ttu-id="763ae-119">使用**Internet 信息服务 (IIS) 管理器**，选择**应用程序池**中**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="763ae-119">Using the **Internet Information Services (IIS) Manager**, select **Application Pools** in the **Connections** pane.</span></span>  
  
6.  <span data-ttu-id="763ae-120">在中**应用程序池**窗格中，右键单击**BAMAppPool**，然后单击**高级设置**</span><span class="sxs-lookup"><span data-stu-id="763ae-120">In the **Application Pools** pane, right-click the **BAMAppPool**, then click **Advanced Settings**</span></span>  
  
7.  <span data-ttu-id="763ae-121">在中**高级设置**对话框中，向下滚动到**进程模型**部分。</span><span class="sxs-lookup"><span data-stu-id="763ae-121">In the **Advanced Setting**s dialog, scroll down to the **Process Model** section.</span></span> <span data-ttu-id="763ae-122">单击**标识**框。</span><span class="sxs-lookup"><span data-stu-id="763ae-122">Click the **Identity** box.</span></span> <span data-ttu-id="763ae-123">这将导致一个用于显示框的右侧的省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="763ae-123">This will cause an ellipses button to appear on the right side of the box.</span></span> <span data-ttu-id="763ae-124">单击**省略号**按钮。</span><span class="sxs-lookup"><span data-stu-id="763ae-124">Click the **ellipses** button.</span></span>  
  
8.  <span data-ttu-id="763ae-125">在中**应用程序池标识**对话框中，单击**自定义帐户**按钮，然后单击**设置**按钮。</span><span class="sxs-lookup"><span data-stu-id="763ae-125">In the **Application Pool Identity** dialog, click the **Custom account** button, then click the **Set** button.</span></span>  
  
9. <span data-ttu-id="763ae-126">在中**设置凭据**对话框框中，输入帐户名和你想要用于 BAMAppPool 的密码。</span><span class="sxs-lookup"><span data-stu-id="763ae-126">In the **Set Credentials** dialog box, enter the account name and password you want to use for the BAMAppPool.</span></span> <span data-ttu-id="763ae-127">应为输入帐户名称*计算机名*`\`*accountname*，或*域*`\`*accountname*.</span><span class="sxs-lookup"><span data-stu-id="763ae-127">The account name should be entered as *computer name*`\`*accountname*, or *domain*`\`*accountname*.</span></span> <span data-ttu-id="763ae-128">单击**确定**以关闭**设置凭据**对话框。</span><span class="sxs-lookup"><span data-stu-id="763ae-128">Click **OK** to close the **Set Credentials** dialog.</span></span>  
  
10. <span data-ttu-id="763ae-129">单击**确定**以关闭**应用程序池标识**对话框。</span><span class="sxs-lookup"><span data-stu-id="763ae-129">Click **OK** to close the **Application Pool Identity** dialog.</span></span>  
  
11. <span data-ttu-id="763ae-130">单击**确定**以关闭**高级设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="763ae-130">Click **OK** to close the **Advanced Settings** dialog.</span></span>  
  
12. <span data-ttu-id="763ae-131">确认**BAMAppPool**的应用程序池列表中选择。</span><span class="sxs-lookup"><span data-stu-id="763ae-131">Verify that the **BAMAppPool** is selected in the list of application pools.</span></span> <span data-ttu-id="763ae-132">在中**操作**的右侧窗格**Internet 信息服务 (IIS) 管理器**屏幕上，在**应用程序池任务**，单击**启动**.</span><span class="sxs-lookup"><span data-stu-id="763ae-132">In the **Actions** pane on the right of the **Internet Information Services (IIS) Manager** screen, under **Application Pool Tasks**, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763ae-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="763ae-133">See Also</span></span>  
 <span data-ttu-id="763ae-134">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="763ae-134">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="763ae-135">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="763ae-135">BAM Portal</span></span>](../core/bam-portal.md)