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
ms.openlocfilehash: 682306dca7a0ae120b4a0ccc84a52733ce23b772
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331932"
---
# <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="9d714-102">安装 Bam-eventing 软件</span><span class="sxs-lookup"><span data-stu-id="9d714-102">Installing the BAM-Eventing Software</span></span>
<span data-ttu-id="9d714-103">若要实现 BAM 解决方案使用 BAM eventing Api 或 Windows Workflow Foundation 或 Windows Communication Foundation 应用程序要用于 Windows Workflow Foundation 的 BAM 侦听器配置，必须安装 Bam-eventing 软件使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="9d714-103">To implement BAM solutions using the BAM eventing APIs or configure your Windows Workflow Foundation or Windows Communication Foundation application to use the BAM interceptor for Windows Workflow Foundation, you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="9d714-104">此软件可以安装的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时或单独选择中的其他软件在 BAM Eventing Support[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d714-104">This software can be installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime or separately by selecting BAM Eventing Support under Additional Software in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup application.</span></span>  
  
### <a name="to-install-the-bam-eventing-software"></a><span data-ttu-id="9d714-105">若要安装 Bam-eventing 软件</span><span class="sxs-lookup"><span data-stu-id="9d714-105">To install the BAM-Eventing software</span></span>  
  
1. <span data-ttu-id="9d714-106">登录到将承载 WF 应用程序使用具有管理员权限的帐户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9d714-106">Log on to the computer that will host the WF application using an account that has Administrator privileges.</span></span>  
  
2. <span data-ttu-id="9d714-107">上运行安装程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装 CD。</span><span class="sxs-lookup"><span data-stu-id="9d714-107">Run the Setup program on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Installation CD.</span></span>  
  
3. <span data-ttu-id="9d714-108">清除所有选择的选项。</span><span class="sxs-lookup"><span data-stu-id="9d714-108">Clear all selected options.</span></span> <span data-ttu-id="9d714-109">如果不执行此步骤中，你可能安装不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="9d714-109">If you do not perform this step, you may install software you do not need.</span></span>  
  
4. <span data-ttu-id="9d714-110">展开**其他软件**，然后选择**Bam-eventing**复选框。</span><span class="sxs-lookup"><span data-stu-id="9d714-110">Expand **Additional Software**, and then select the **BAM-Eventing** check box.</span></span>  
  
5. <span data-ttu-id="9d714-111">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="9d714-111">Click **Next**.</span></span>  
  
6. <span data-ttu-id="9d714-112">单击 **“安装”**。</span><span class="sxs-lookup"><span data-stu-id="9d714-112">Click **Install**.</span></span>  
  
7. <span data-ttu-id="9d714-113">安装过程完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d714-113">When the installation procedure is complete, click **OK**.</span></span>  
  
    <span data-ttu-id="9d714-114">现在安装 Bam-eventing 软件。</span><span class="sxs-lookup"><span data-stu-id="9d714-114">The BAM-Eventing software is now installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d714-115">安装使用此方法的 BAM 侦听器库不需要购买其他许可证。</span><span class="sxs-lookup"><span data-stu-id="9d714-115">Installing the BAM interceptor library using this method does not require the purchase of additional licenses.</span></span>  
  
 <span data-ttu-id="9d714-116">如果您有兴趣监视 BAM 侦听器性能计数器数据，您首先必须通过使用 InstallUtil.exe 注册它们。</span><span class="sxs-lookup"><span data-stu-id="9d714-116">If you are interested in monitoring performance counter data for the BAM interceptors, you must first register them by using InstallUtil.exe.</span></span>  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a><span data-ttu-id="9d714-117">若要使用 InstallUtil.exe 注册 BAM 侦听器性能计数器</span><span class="sxs-lookup"><span data-stu-id="9d714-117">To register BAM interceptor performance counters by using InstallUtil.exe</span></span>  
  
1. <span data-ttu-id="9d714-118">启动**[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="9d714-118">Start **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt** as an administrator.</span></span>  
  
2. <span data-ttu-id="9d714-119">在命令提示符处，输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9d714-119">At the command prompt, enter the following command:</span></span>  
  
    <span data-ttu-id="9d714-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span><span class="sxs-lookup"><span data-stu-id="9d714-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span></span>  
  
3. <span data-ttu-id="9d714-121">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9d714-121">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
    <span data-ttu-id="9d714-122">现在提供了 BAM 侦听器性能计数器。</span><span class="sxs-lookup"><span data-stu-id="9d714-122">The BAM interceptor performance counters are now available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d714-123">默认情况下，只有管理员和系统帐户有权记录性能数据。</span><span class="sxs-lookup"><span data-stu-id="9d714-123">By default, only Administrators and some system accounts have permission to log performance data.</span></span> <span data-ttu-id="9d714-124">若要启用访问权限在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，添加用于运行工作流应用程序到 Performance Log Users 组的帐户。</span><span class="sxs-lookup"><span data-stu-id="9d714-124">To enable access on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], add the account used for running workflow applications to the Performance Log Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d714-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d714-125">See Also</span></span>  
 <span data-ttu-id="9d714-126">[实现 BAM 解决方案](../core/implementing-bam-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9d714-126">[Implementing BAM Solutions](../core/implementing-bam-solutions.md) </span></span>  
 [<span data-ttu-id="9d714-127">BizTalk Server 2013 和 2013 R2 安装概述</span><span class="sxs-lookup"><span data-stu-id="9d714-127">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)