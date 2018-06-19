---
title: 安装 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e9d4dfe5818e28e1ccd73b077c19c9d45ecb8cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966507"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="7b8e1-102">安装 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="7b8e1-102">Install the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="7b8e1-103">安装和配置[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-103">Install and configure the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="7b8e1-104">要求</span><span class="sxs-lookup"><span data-stu-id="7b8e1-104">Requirements</span></span> 
<span data-ttu-id="7b8e1-105">以下你在其中安装在系统上的组件安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-105">Install following components on the system where you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> 

> [!NOTE]
> <span data-ttu-id="7b8e1-106">**有关受支持版本的列表**，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-106">**For a list of the supported versions**, see:</span></span> 
> 
> [<span data-ttu-id="7b8e1-107">BizTalk Server 2016 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="7b8e1-107">Hardware and Software Requirements for BizTalk Server 2016</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [<span data-ttu-id="7b8e1-108">BizTalk Server 2013 和 2013 R2 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="7b8e1-108">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)
 
 | | | 
 | --- | --- |
 | <span data-ttu-id="7b8e1-109">Windows</span><span class="sxs-lookup"><span data-stu-id="7b8e1-109">Windows</span></span> | <span data-ttu-id="7b8e1-110">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="7b8e1-110">x86 or x64</span></span> <br/><br/><span data-ttu-id="7b8e1-111">所需的操作系统资源包括：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-111">Required OS resources include:</span></span><br/> <ul><li><span data-ttu-id="7b8e1-112">支持 OleTx 事务所所需的 Microsoft 分布式事务处理协调器 (MSDTC):</span><span class="sxs-lookup"><span data-stu-id="7b8e1-112">Microsoft Distributed Transaction Coordinator (MSDTC) : Required to support OleTx transactions</span></span></li><li><span data-ttu-id="7b8e1-113">支持可靠消息传递所需的消息队列 (MSMQ):</span><span class="sxs-lookup"><span data-stu-id="7b8e1-113">Message Queuing (MSMQ) : Required to support reliable messaging</span></span></li><li><span data-ttu-id="7b8e1-114">Internet Information Services (IIS): 所需如果你想要承载在 IIS 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="7b8e1-114">Internet Information Services (IIS) : Required if you want to host your application in IIS</span></span></li><li><span data-ttu-id="7b8e1-115">Windows Process Activation Service (WAS): 所需如果你想要承载在 WAS 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="7b8e1-115">Windows Process Activation Service (WAS) : Required if you want to host your application in WAS</span></span></li></ul> |
 |<span data-ttu-id="7b8e1-116">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7b8e1-116">Windows Communication Foundation</span></span>| | 
 | [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] | | 
 | [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="7b8e1-117">如果要生成自定义适配器，或使用开发使用适配器的解决方案生成所需[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-117">Required if you are building custom adapters, or developing solutions that use the adapters built with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] | <span data-ttu-id="7b8e1-118">如果你使用具有适配器是必需的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-118">Required if you use the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  |


  
## <a name="install"></a><span data-ttu-id="7b8e1-119">Install</span><span class="sxs-lookup"><span data-stu-id="7b8e1-119">Install</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="7b8e1-120">关闭 Visual Studio 的所有实例</span><span class="sxs-lookup"><span data-stu-id="7b8e1-120">Close all instances of Visual Studio</span></span>
> * <span data-ttu-id="7b8e1-121">若要执行**完成**安装程序，请确保在计算机上是否安装了 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-121">To do a **Complete** setup, confirm that BizTalk Server is installed on the computer.</span></span>  
  
1.  <span data-ttu-id="7b8e1-122">运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-122">Run the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** as Administrator.</span></span>
  
2.  <span data-ttu-id="7b8e1-123">选择**安装 Microsoft BizTalk 适配器**，然后选择**安装 Microsoft WCF LOB 适配器 SDK**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-123">Select **Install Microsoft BizTalk Adapters**, and then select **Install Microsoft WCF LOB Adapter SDK**.</span></span>  
  
3.  <span data-ttu-id="7b8e1-124">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-124">On the **Welcome** screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="7b8e1-125">接受许可协议，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-125">Accept the license agreement, and select **Next**.</span></span>  
  
5.  <span data-ttu-id="7b8e1-126">在**选择安装类型**，选择安装类型：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-126">In **Choose Setup Type**, select the type of installation:</span></span>  
  
    -   <span data-ttu-id="7b8e1-127">若要安装的公共运行的时和工具，选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-127">To install the common run time and tools, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="7b8e1-128">若要选择的功能，你想安装并安装位置，选择**自定义**，然后选择你想要安装的功能。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-128">To select the features that you want to install and the installation location, select **Custom**, and then select the features you want to install.</span></span>  
  
    -   <span data-ttu-id="7b8e1-129">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-129">To install all the features, select **Complete**.</span></span>  
  
6.  <span data-ttu-id="7b8e1-130">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-130">Select **Install**.</span></span>  
  
## <a name="update-or-remove"></a><span data-ttu-id="7b8e1-131">更新或删除</span><span class="sxs-lookup"><span data-stu-id="7b8e1-131">Update or remove</span></span>
  
1.  <span data-ttu-id="7b8e1-132">打开**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-132">Open **Programs and Feature**.</span></span> 
  
2.  <span data-ttu-id="7b8e1-133">在列表中，选择**Windows Communication Foundation LOB 适配器 SDK**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-133">In the list, select **Windows Communication Foundation LOB Adapter SDK**, and then select **Change**.</span></span>  
  
3.  <span data-ttu-id="7b8e1-134">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-134">On the **Welcome** screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="7b8e1-135">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-135">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="7b8e1-136">若要选择你想要安装的组件，选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-136">To select the components that you want to install, select **Change**.</span></span>  
  
    -   <span data-ttu-id="7b8e1-137">若要修复最新安装中的错误，选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-137">To repair errors in the most recent installation, select **Repair**.</span></span>  
  
    -   <span data-ttu-id="7b8e1-138">若要删除[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从计算机上，选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-138">To remove the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] from the computer, select **Remove**.</span></span>  
  
5.  <span data-ttu-id="7b8e1-139">如果您选择要修改安装：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-139">If you choose to modify the installation:</span></span>  
  
    1.  <span data-ttu-id="7b8e1-140">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-140">Select **Next**.</span></span>  
  
    2.  <span data-ttu-id="7b8e1-141">选择**更改**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-141">Select **Change**, and then select **Finish**.</span></span>  
  
6.  <span data-ttu-id="7b8e1-142">如果你选择在修复安装，**准备好修复 WCF LOB 适配器 SDK**对话框中，选择**修复**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-142">If you choose to repair the installation, in the **Ready to repair WCF LOB Adapter SDK** dialog box, select **Repair**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="7b8e1-143">如果你选择中删除适配器，**准备好删除 WCF LOB 适配器 SDK**对话框中，选择**删除**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-143">If you choose to remove the adapters, in the **Ready to remove WCF LOB Adapter SDK** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
  
#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="7b8e1-144">卸载 WCF LOB 适配器 SDK 后删除自定义适配器</span><span class="sxs-lookup"><span data-stu-id="7b8e1-144">Remove custom adapters after uninstalling the WCF LOB Adapter SDK</span></span>  

 <span data-ttu-id="7b8e1-145">如果您已开发使用任何自定义适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并且已在你的计算机上注册这些适配器，你还必须完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-145">If you have developed any custom adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and you have registered these adapters on your computer, you must also complete the following procedure.</span></span>  
  
1.  <span data-ttu-id="7b8e1-146">从全局程序集缓存 (GAC) 中删除自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-146">Remove the custom adapter from the global assembly cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="7b8e1-147">打开**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-147">Open a **Visual Studio command prompt**.</span></span>  
  
    2.  <span data-ttu-id="7b8e1-148">删除自定义**适配器.dll**从 GAC 使用**命令 gacutil /u**。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-148">Remove the custom **adapter .dll** from the GAC using **command gacutil /u**.</span></span>  
  
2.  <span data-ttu-id="7b8e1-149">删除自定义适配器绑定到 machine.config 中的引用</span><span class="sxs-lookup"><span data-stu-id="7b8e1-149">Remove the references to the custom adapter binding from machine.config</span></span>  
  
    1.  <span data-ttu-id="7b8e1-150">转到下的 machine.config 文件\<*系统驱动器*\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-150">Go to the machine.config file under \<*system drive*\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    2.  <span data-ttu-id="7b8e1-151">通过使用文本编辑器中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-151">Open the file by using a text editor.</span></span>  
  
    3.  <span data-ttu-id="7b8e1-152">元素 bindingExtensions、 客户端和 bindingElementExtensions system.serviceModel\extensions 下的搜索。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-152">Search for the element bindingExtensions, client and bindingElementExtensions under system.serviceModel\extensions.</span></span>  
  
    4.  <span data-ttu-id="7b8e1-153">删除与你自定义适配器 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-153">Remove the WCF binding that pertains to your custom adapter.</span></span>  
  
## <a name="do-a-silent-installation"></a><span data-ttu-id="7b8e1-154">执行无提示安装</span><span class="sxs-lookup"><span data-stu-id="7b8e1-154">Do a silent installation</span></span>  
 <span data-ttu-id="7b8e1-155">无提示安装非常适合于测试方案或在大型企业部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-155">A silent installation is ideal for test scenarios or as part of a large-scale enterprise deployment.</span></span> [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="7b8e1-156">提供命令行参数，你可以使用 AdapterFramework.msi 执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-156"> provides command line parameters that you can use with AdapterFramework.msi to perform a silent installation.</span></span>  
 
> [!NOTE]
>  <span data-ttu-id="7b8e1-157">若要执行无提示安装，应是计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-157">To perform silent installation, you should be an Administrator on the computer.</span></span> 

  
1.  <span data-ttu-id="7b8e1-158">以管理员身份打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-158">Open a command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="7b8e1-159">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-159">Type the following:</span></span>
  
    ```  
    AdapterFramework.msi /quiet MUOPTIN=”Yes”  
    ```  
  
    <span data-ttu-id="7b8e1-160">使用下列命令行选项与 AdapterFramework.msi 结合使用：</span><span class="sxs-lookup"><span data-stu-id="7b8e1-160">Use the following command line options in conjunction with AdapterFramework.msi:</span></span>  
  
    * <span data-ttu-id="7b8e1-161">使用`/quiet`安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以无提示方式。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-161">Use `/quiet` to install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] silently.</span></span>  
  
    * <span data-ttu-id="7b8e1-162">使用 MUOPTIN ="Yes"&#124;"否"以指示如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]应检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-162">Use MUOPTIN=”Yes”&#124;”No” to indicate if the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] should check for updates with Microsoft Update.</span></span>  
    
        <span data-ttu-id="7b8e1-163">当设置为 Yes，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查通过 Microsoft 更新的更新。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-163">When set to Yes, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] checks for updates through Microsoft Update.</span></span> <span data-ttu-id="7b8e1-164">当设置为 no[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不会检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-164">When set to no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not check for updates with Microsoft Update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b8e1-165">若要显示的命令行安装其他选项，请键入`AdapterFramework.msi /?`在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7b8e1-165">To display additional options for command line installation, type `AdapterFramework.msi /?`at the command prompt.</span></span>  
  
