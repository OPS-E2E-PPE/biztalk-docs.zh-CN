---
title: 安装 WCF LOB 适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: 95fba9830bd97dd619cd16d18c0363a4525d1397
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999702"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="a1efa-102">安装 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="a1efa-102">Install the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="a1efa-103">安装和配置[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1efa-103">Install and configure the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> 

## <a name="requirements"></a><span data-ttu-id="a1efa-104">要求</span><span class="sxs-lookup"><span data-stu-id="a1efa-104">Requirements</span></span> 
<span data-ttu-id="a1efa-105">安装以下组件安装在系统上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1efa-105">Install following components on the system where you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> 

> [!NOTE]
> <span data-ttu-id="a1efa-106">**有关支持的版本的列表**，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a1efa-106">**For a list of the supported versions**, see:</span></span> 
> 
> [<span data-ttu-id="a1efa-107">BizTalk Server 2016 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="a1efa-107">Hardware and Software Requirements for BizTalk Server 2016</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [<span data-ttu-id="a1efa-108">BizTalk Server 2013 和 2013 R2 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="a1efa-108">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         <span data-ttu-id="a1efa-109">Windows</span><span class="sxs-lookup"><span data-stu-id="a1efa-109">Windows</span></span>                                          | <span data-ttu-id="a1efa-110">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="a1efa-110">x86 or x64</span></span> <br/><br/><span data-ttu-id="a1efa-111">所需的 OS 资源包括：</span><span class="sxs-lookup"><span data-stu-id="a1efa-111">Required OS resources include:</span></span><br/> <ul><li><span data-ttu-id="a1efa-112">支持 OleTx 事务所所需的 Microsoft 分布式事务处理协调器 (MSDTC):</span><span class="sxs-lookup"><span data-stu-id="a1efa-112">Microsoft Distributed Transaction Coordinator (MSDTC) : Required to support OleTx transactions</span></span></li><li><span data-ttu-id="a1efa-113">支持可靠消息传递所需的消息队列 (MSMQ):</span><span class="sxs-lookup"><span data-stu-id="a1efa-113">Message Queuing (MSMQ) : Required to support reliable messaging</span></span></li><li><span data-ttu-id="a1efa-114">Internet Information Services (IIS): 需要你想要托管在 IIS 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="a1efa-114">Internet Information Services (IIS) : Required if you want to host your application in IIS</span></span></li><li><span data-ttu-id="a1efa-115">Windows 进程激活服务 (WAS): 需要你想要承载在 WAS 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="a1efa-115">Windows Process Activation Service (WAS) : Required if you want to host your application in WAS</span></span></li></ul> |
|                             <span data-ttu-id="a1efa-116">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a1efa-116">Windows Communication Foundation</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     <span data-ttu-id="a1efa-117">如果要构建自定义适配器，或使用开发使用适配器的解决方案生成所需[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1efa-117">Required if you are building custom adapters, or developing solutions that use the adapters built with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 <span data-ttu-id="a1efa-118">如果在使用与适配器需要[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1efa-118">Required if you use the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>                                                                                                                                                                 |

## <a name="install"></a><span data-ttu-id="a1efa-119">Install</span><span class="sxs-lookup"><span data-stu-id="a1efa-119">Install</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="a1efa-120">关闭 Visual Studio 的所有实例</span><span class="sxs-lookup"><span data-stu-id="a1efa-120">Close all instances of Visual Studio</span></span>
> * <span data-ttu-id="a1efa-121">若要执行操作**完成**设置，请确保在计算机上是否安装了 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="a1efa-121">To do a **Complete** setup, confirm that BizTalk Server is installed on the computer.</span></span>  

1. <span data-ttu-id="a1efa-122">运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="a1efa-122">Run the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** as Administrator.</span></span>

2. <span data-ttu-id="a1efa-123">选择**安装 Microsoft BizTalk 适配器**，然后选择**安装 Microsoft WCF LOB 适配器 SDK**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-123">Select **Install Microsoft BizTalk Adapters**, and then select **Install Microsoft WCF LOB Adapter SDK**.</span></span>  

3. <span data-ttu-id="a1efa-124">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-124">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="a1efa-125">接受许可协议，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a1efa-125">Accept the license agreement, and select **Next**.</span></span>  

5. <span data-ttu-id="a1efa-126">在中**选择安装类型**，选择安装类型：</span><span class="sxs-lookup"><span data-stu-id="a1efa-126">In **Choose Setup Type**, select the type of installation:</span></span>  

   -   <span data-ttu-id="a1efa-127">若要安装的公共运行的时和工具，请选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-127">To install the common run time and tools, select **Typical**.</span></span>  

   -   <span data-ttu-id="a1efa-128">若要选择要安装和安装位置的功能，请选择**自定义**，然后选择你想要安装的功能。</span><span class="sxs-lookup"><span data-stu-id="a1efa-128">To select the features that you want to install and the installation location, select **Custom**, and then select the features you want to install.</span></span>  

   -   <span data-ttu-id="a1efa-129">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-129">To install all the features, select **Complete**.</span></span>  

6. <span data-ttu-id="a1efa-130">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="a1efa-130">Select **Install**.</span></span>  

## <a name="update-or-remove"></a><span data-ttu-id="a1efa-131">更新或删除</span><span class="sxs-lookup"><span data-stu-id="a1efa-131">Update or remove</span></span>

1. <span data-ttu-id="a1efa-132">打开**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-132">Open **Programs and Feature**.</span></span> 

2. <span data-ttu-id="a1efa-133">在列表中，选择**Windows Communication Foundation LOB 适配器 SDK**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-133">In the list, select **Windows Communication Foundation LOB Adapter SDK**, and then select **Change**.</span></span>  

3. <span data-ttu-id="a1efa-134">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-134">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="a1efa-135">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="a1efa-135">Do one of the following:</span></span>  

   - <span data-ttu-id="a1efa-136">若要选择你想要安装的组件，请选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-136">To select the components that you want to install, select **Change**.</span></span>  

   - <span data-ttu-id="a1efa-137">若要修复最新安装中的错误，请选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-137">To repair errors in the most recent installation, select **Repair**.</span></span>  

   - <span data-ttu-id="a1efa-138">若要删除[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从计算机上，选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-138">To remove the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] from the computer, select **Remove**.</span></span>  

5. <span data-ttu-id="a1efa-139">如果您选择修改安装：</span><span class="sxs-lookup"><span data-stu-id="a1efa-139">If you choose to modify the installation:</span></span>  

   1.  <span data-ttu-id="a1efa-140">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="a1efa-140">Select **Next**.</span></span>  

   2.  <span data-ttu-id="a1efa-141">选择**更改**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-141">Select **Change**, and then select **Finish**.</span></span>  

6. <span data-ttu-id="a1efa-142">如果您选择中的修复安装，**准备好修复 WCF LOB 适配器 SDK**对话框中，选择**修复**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-142">If you choose to repair the installation, in the **Ready to repair WCF LOB Adapter SDK** dialog box, select **Repair**, and then select **Finish**.</span></span>  

7. <span data-ttu-id="a1efa-143">如果您选择要删除适配器，在**准备好删除 WCF LOB 适配器 SDK**对话框中，选择**删除**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-143">If you choose to remove the adapters, in the **Ready to remove WCF LOB Adapter SDK** dialog box, select **Remove**, and then select **Finish**.</span></span>  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="a1efa-144">在卸载 WCF LOB 适配器 SDK 之后删除自定义适配器</span><span class="sxs-lookup"><span data-stu-id="a1efa-144">Remove custom adapters after uninstalling the WCF LOB Adapter SDK</span></span>  

 <span data-ttu-id="a1efa-145">如果您已开发使用任何自定义适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并已在计算机上注册这些适配器，你还必须完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="a1efa-145">If you have developed any custom adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and you have registered these adapters on your computer, you must also complete the following procedure.</span></span>  

1.  <span data-ttu-id="a1efa-146">从全局程序集缓存 (GAC) 中删除自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="a1efa-146">Remove the custom adapter from the global assembly cache (GAC).</span></span>  

    1.  <span data-ttu-id="a1efa-147">打开**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-147">Open a **Visual Studio command prompt**.</span></span>  

    2.  <span data-ttu-id="a1efa-148">删除自定义**适配器.dll**从 GAC 中使用**命令 gacutil /u**。</span><span class="sxs-lookup"><span data-stu-id="a1efa-148">Remove the custom **adapter .dll** from the GAC using **command gacutil /u**.</span></span>  

2.  <span data-ttu-id="a1efa-149">删除自定义适配器绑定到从 machine.config 的引用</span><span class="sxs-lookup"><span data-stu-id="a1efa-149">Remove the references to the custom adapter binding from machine.config</span></span>  

    1.  <span data-ttu-id="a1efa-150">转到下的 machine.config 文件\<*系统驱动器*\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="a1efa-150">Go to the machine.config file under \<*system drive*\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    2.  <span data-ttu-id="a1efa-151">使用文本编辑器打开该文件。</span><span class="sxs-lookup"><span data-stu-id="a1efa-151">Open the file by using a text editor.</span></span>  

    3.  <span data-ttu-id="a1efa-152">元素 bindingExtensions、 客户端和 bindingElementExtensions system.serviceModel\extensions 下的搜索。</span><span class="sxs-lookup"><span data-stu-id="a1efa-152">Search for the element bindingExtensions, client and bindingElementExtensions under system.serviceModel\extensions.</span></span>  

    4.  <span data-ttu-id="a1efa-153">移除与自定义适配器的 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="a1efa-153">Remove the WCF binding that pertains to your custom adapter.</span></span>  

## <a name="do-a-silent-installation"></a><span data-ttu-id="a1efa-154">执行无提示安装</span><span class="sxs-lookup"><span data-stu-id="a1efa-154">Do a silent installation</span></span>  
 <span data-ttu-id="a1efa-155">无提示安装非常适合于测试方案或大型企业部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1efa-155">A silent installation is ideal for test scenarios or as part of a large-scale enterprise deployment.</span></span> [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="a1efa-156"> 提供命令行参数，您可以使用与 AdapterFramework.msi 执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="a1efa-156"> provides command line parameters that you can use with AdapterFramework.msi to perform a silent installation.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a1efa-157">若要执行无提示安装，应是计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="a1efa-157">To perform silent installation, you should be an Administrator on the computer.</span></span> 


1. <span data-ttu-id="a1efa-158">以管理员身份打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a1efa-158">Open a command prompt as administrator.</span></span>  

2. <span data-ttu-id="a1efa-159">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="a1efa-159">Type the following:</span></span>

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   <span data-ttu-id="a1efa-160">使用下列命令行选项与 AdapterFramework.msi 结合使用：</span><span class="sxs-lookup"><span data-stu-id="a1efa-160">Use the following command line options in conjunction with AdapterFramework.msi:</span></span>  

   * <span data-ttu-id="a1efa-161">使用`/quiet`若要安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以无提示方式。</span><span class="sxs-lookup"><span data-stu-id="a1efa-161">Use `/quiet` to install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] silently.</span></span>  

   * <span data-ttu-id="a1efa-162">使用 MUOPTIN ="Yes"&#124;"否"以指示如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="a1efa-162">Use MUOPTIN=”Yes”&#124;”No” to indicate if the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] should check for updates with Microsoft Update.</span></span>  

       <span data-ttu-id="a1efa-163">当设置为 Yes，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查通过 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="a1efa-163">When set to Yes, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] checks for updates through Microsoft Update.</span></span> <span data-ttu-id="a1efa-164">当设置为 no[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不会检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="a1efa-164">When set to no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not check for updates with Microsoft Update.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a1efa-165">若要显示的命令行安装的其他选项，请键入`AdapterFramework.msi /?`在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="a1efa-165">To display additional options for command line installation, type `AdapterFramework.msi /?`at the command prompt.</span></span>  

