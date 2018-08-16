---
title: 安装 Bam-eventing 软件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5d13e058799113d7847fe6377ce82c7e0a7ea5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000286"
---
# <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="abd53-102">安装 Bam-eventing 软件</span><span class="sxs-lookup"><span data-stu-id="abd53-102">Installing the BAM-Eventing Software</span></span>
<span data-ttu-id="abd53-103">若要实现 BAM 解决方案使用 BAM eventing Api 或 Windows Workflow Foundation 或 Windows Communication Foundation 应用程序要用于 Windows Workflow Foundation 的 BAM 侦听器配置，必须安装 Bam-eventing 软件使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="abd53-103">To implement BAM solutions using the BAM eventing APIs or configure your Windows Workflow Foundation or Windows Communication Foundation application to use the BAM interceptor for Windows Workflow Foundation, you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="abd53-104">此软件可以作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时的一部分安装，也可以通过在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装应用程序中的“其他软件”下选择揃“BAM Eventing Support”来单独安装。</span><span class="sxs-lookup"><span data-stu-id="abd53-104">This software can be installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime or separately by selecting BAM Eventing Support under Additional Software in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup application.</span></span>  
  
### <a name="to-install-the-bam-eventing-software"></a><span data-ttu-id="abd53-105">安装 BAM-Eventing 软件</span><span class="sxs-lookup"><span data-stu-id="abd53-105">To install the BAM-Eventing software</span></span>  
  
1. <span data-ttu-id="abd53-106">使用具有管理员权限的帐户登录到将承载 WF 应用程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="abd53-106">Log on to the computer that will host the WF application using an account that has Administrator privileges.</span></span>  
  
2. <span data-ttu-id="abd53-107">上运行安装程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装 CD。</span><span class="sxs-lookup"><span data-stu-id="abd53-107">Run the Setup program on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Installation CD.</span></span>  
  
3. <span data-ttu-id="abd53-108">清除所有选定的选项。</span><span class="sxs-lookup"><span data-stu-id="abd53-108">Clear all selected options.</span></span> <span data-ttu-id="abd53-109">如果不执行此步骤，可能会安装不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="abd53-109">If you do not perform this step, you may install software you do not need.</span></span>  
  
4. <span data-ttu-id="abd53-110">展开**其他软件**，然后选择**Bam-eventing**复选框。</span><span class="sxs-lookup"><span data-stu-id="abd53-110">Expand **Additional Software**, and then select the **BAM-Eventing** check box.</span></span>  
  
5. <span data-ttu-id="abd53-111">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="abd53-111">Click **Next**.</span></span>  
  
6. <span data-ttu-id="abd53-112">单击 **“安装”**。</span><span class="sxs-lookup"><span data-stu-id="abd53-112">Click **Install**.</span></span>  
  
7. <span data-ttu-id="abd53-113">安装过程完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="abd53-113">When the installation procedure is complete, click **OK**.</span></span>  
  
    <span data-ttu-id="abd53-114">BAM-Eventing 软件现在已安装完毕。</span><span class="sxs-lookup"><span data-stu-id="abd53-114">The BAM-Eventing software is now installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abd53-115">使用此方法安装 BAM 侦听器库不需要购买其他许可证。</span><span class="sxs-lookup"><span data-stu-id="abd53-115">Installing the BAM interceptor library using this method does not require the purchase of additional licenses.</span></span>  
  
 <span data-ttu-id="abd53-116">如果你希望监视 BAM 侦听器的性能计数器数据，必须先使用 InstallUtil.exe 注册它们。</span><span class="sxs-lookup"><span data-stu-id="abd53-116">If you are interested in monitoring performance counter data for the BAM interceptors, you must first register them by using InstallUtil.exe.</span></span>  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a><span data-ttu-id="abd53-117">使用 InstallUtil.exe 注册 BAM 侦听器性能计数器</span><span class="sxs-lookup"><span data-stu-id="abd53-117">To register BAM interceptor performance counters by using InstallUtil.exe</span></span>  
  
1. <span data-ttu-id="abd53-118">启动**[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="abd53-118">Start **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt** as an administrator.</span></span>  
  
2. <span data-ttu-id="abd53-119">在命令提示符下输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="abd53-119">At the command prompt, enter the following command:</span></span>  
  
    <span data-ttu-id="abd53-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span><span class="sxs-lookup"><span data-stu-id="abd53-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span></span>  
  
3. <span data-ttu-id="abd53-121">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="abd53-121">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
    <span data-ttu-id="abd53-122">BAM 侦听器性能计数器现在处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="abd53-122">The BAM interceptor performance counters are now available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abd53-123">默认情况下，只有管理员帐户和系统帐户具有在日志中记录性能数据的权限。</span><span class="sxs-lookup"><span data-stu-id="abd53-123">By default, only Administrators and some system accounts have permission to log performance data.</span></span> <span data-ttu-id="abd53-124">若要启用访问权限在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，添加用于运行工作流应用程序到 Performance Log Users 组的帐户。</span><span class="sxs-lookup"><span data-stu-id="abd53-124">To enable access on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], add the account used for running workflow applications to the Performance Log Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd53-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd53-125">See Also</span></span>  
 <span data-ttu-id="abd53-126">[实现 BAM 解决方案](../core/implementing-bam-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="abd53-126">[Implementing BAM Solutions](../core/implementing-bam-solutions.md) </span></span>  
 [<span data-ttu-id="abd53-127">BizTalk Server 2013 和 2013 R2 安装概述</span><span class="sxs-lookup"><span data-stu-id="abd53-127">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)