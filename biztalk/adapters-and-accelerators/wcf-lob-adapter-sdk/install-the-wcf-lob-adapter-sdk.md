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
ms.openlocfilehash: a0987052ec5c29b321fdef8ec82a57ab582950dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363643"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="2a6db-102">安装 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="2a6db-102">Install the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="2a6db-103">安装和配置[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2a6db-103">Install and configure the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> 

## <a name="requirements"></a><span data-ttu-id="2a6db-104">要求</span><span class="sxs-lookup"><span data-stu-id="2a6db-104">Requirements</span></span> 
<span data-ttu-id="2a6db-105">安装以下组件安装在系统上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2a6db-105">Install following components on the system where you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> 

> [!NOTE]
> <span data-ttu-id="2a6db-106">**有关支持的版本的列表**，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2a6db-106">**For a list of the supported versions**, see:</span></span> 
> 
> [<span data-ttu-id="2a6db-107">硬件和软件要求适用于 BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="2a6db-107">Hardware and Software Requirements for BizTalk Server 2016</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [<span data-ttu-id="2a6db-108">BizTalk Server 2013 和 2013 R2 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="2a6db-108">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         <span data-ttu-id="2a6db-109">Windows</span><span class="sxs-lookup"><span data-stu-id="2a6db-109">Windows</span></span>                                          | <span data-ttu-id="2a6db-110">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="2a6db-110">x86 or x64</span></span> <br/><br/><span data-ttu-id="2a6db-111">所需的 OS 资源包括：</span><span class="sxs-lookup"><span data-stu-id="2a6db-111">Required OS resources include:</span></span><br/> <ul><li><span data-ttu-id="2a6db-112">Microsoft 分布式事务处理协调器 (MSDTC):支持 OleTx 事务所需</span><span class="sxs-lookup"><span data-stu-id="2a6db-112">Microsoft Distributed Transaction Coordinator (MSDTC) : Required to support OleTx transactions</span></span></li><li><span data-ttu-id="2a6db-113">消息队列 (MSMQ):支持可靠消息传递所需</span><span class="sxs-lookup"><span data-stu-id="2a6db-113">Message Queuing (MSMQ) : Required to support reliable messaging</span></span></li><li><span data-ttu-id="2a6db-114">Internet 信息服务 (IIS):如果你想要托管在 IIS 中的应用程序所需</span><span class="sxs-lookup"><span data-stu-id="2a6db-114">Internet Information Services (IIS) : Required if you want to host your application in IIS</span></span></li><li><span data-ttu-id="2a6db-115">Windows 进程激活服务 (WAS):如果你想要承载在 WAS 中的应用程序所需</span><span class="sxs-lookup"><span data-stu-id="2a6db-115">Windows Process Activation Service (WAS) : Required if you want to host your application in WAS</span></span></li></ul> |
|                             <span data-ttu-id="2a6db-116">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2a6db-116">Windows Communication Foundation</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     <span data-ttu-id="2a6db-117">如果要构建自定义适配器，或使用开发使用适配器的解决方案生成所需[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2a6db-117">Required if you are building custom adapters, or developing solutions that use the adapters built with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 <span data-ttu-id="2a6db-118">如果在使用与适配器需要[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2a6db-118">Required if you use the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>                                                                                                                                                                 |

## <a name="install"></a><span data-ttu-id="2a6db-119">安装</span><span class="sxs-lookup"><span data-stu-id="2a6db-119">Install</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="2a6db-120">关闭 Visual Studio 的所有实例</span><span class="sxs-lookup"><span data-stu-id="2a6db-120">Close all instances of Visual Studio</span></span>
> * <span data-ttu-id="2a6db-121">若要执行操作**完成**设置，请确保在计算机上是否安装了 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="2a6db-121">To do a **Complete** setup, confirm that BizTalk Server is installed on the computer.</span></span>  

1. <span data-ttu-id="2a6db-122">运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="2a6db-122">Run the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** as Administrator.</span></span>

2. <span data-ttu-id="2a6db-123">选择**安装 Microsoft BizTalk 适配器**，然后选择**安装 Microsoft WCF LOB 适配器 SDK**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-123">Select **Install Microsoft BizTalk Adapters**, and then select **Install Microsoft WCF LOB Adapter SDK**.</span></span>  

3. <span data-ttu-id="2a6db-124">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-124">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="2a6db-125">接受许可协议，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-125">Accept the license agreement, and select **Next**.</span></span>  

5. <span data-ttu-id="2a6db-126">在中**选择安装类型**，选择安装类型：</span><span class="sxs-lookup"><span data-stu-id="2a6db-126">In **Choose Setup Type**, select the type of installation:</span></span>  

   -   <span data-ttu-id="2a6db-127">若要安装的公共运行的时和工具，请选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-127">To install the common run time and tools, select **Typical**.</span></span>  

   -   <span data-ttu-id="2a6db-128">若要选择要安装和安装位置的功能，请选择**自定义**，然后选择你想要安装的功能。</span><span class="sxs-lookup"><span data-stu-id="2a6db-128">To select the features that you want to install and the installation location, select **Custom**, and then select the features you want to install.</span></span>  

   -   <span data-ttu-id="2a6db-129">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-129">To install all the features, select **Complete**.</span></span>  

6. <span data-ttu-id="2a6db-130">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="2a6db-130">Select **Install**.</span></span>  

## <a name="update-or-remove"></a><span data-ttu-id="2a6db-131">更新或删除</span><span class="sxs-lookup"><span data-stu-id="2a6db-131">Update or remove</span></span>

1. <span data-ttu-id="2a6db-132">打开**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-132">Open **Programs and Feature**.</span></span> 

2. <span data-ttu-id="2a6db-133">在列表中，选择**Windows Communication Foundation LOB 适配器 SDK**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-133">In the list, select **Windows Communication Foundation LOB Adapter SDK**, and then select **Change**.</span></span>  

3. <span data-ttu-id="2a6db-134">上**欢迎**屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-134">On the **Welcome** screen, select **Next**.</span></span>  

4. <span data-ttu-id="2a6db-135">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="2a6db-135">Do one of the following:</span></span>  

   - <span data-ttu-id="2a6db-136">若要选择你想要安装的组件，请选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-136">To select the components that you want to install, select **Change**.</span></span>  

   - <span data-ttu-id="2a6db-137">若要修复最新安装中的错误，请选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-137">To repair errors in the most recent installation, select **Repair**.</span></span>  

   - <span data-ttu-id="2a6db-138">若要删除[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从计算机上，选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-138">To remove the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] from the computer, select **Remove**.</span></span>  

5. <span data-ttu-id="2a6db-139">如果您选择修改安装：</span><span class="sxs-lookup"><span data-stu-id="2a6db-139">If you choose to modify the installation:</span></span>  

   1.  <span data-ttu-id="2a6db-140">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2a6db-140">Select **Next**.</span></span>  

   2.  <span data-ttu-id="2a6db-141">选择**更改**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-141">Select **Change**, and then select **Finish**.</span></span>  

6. <span data-ttu-id="2a6db-142">如果您选择中的修复安装，**准备好修复 WCF LOB 适配器 SDK**对话框中，选择**修复**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-142">If you choose to repair the installation, in the **Ready to repair WCF LOB Adapter SDK** dialog box, select **Repair**, and then select **Finish**.</span></span>  

7. <span data-ttu-id="2a6db-143">如果您选择要删除适配器，在**准备好删除 WCF LOB 适配器 SDK**对话框中，选择**删除**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-143">If you choose to remove the adapters, in the **Ready to remove WCF LOB Adapter SDK** dialog box, select **Remove**, and then select **Finish**.</span></span>  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="2a6db-144">在卸载 WCF LOB 适配器 SDK 之后删除自定义适配器</span><span class="sxs-lookup"><span data-stu-id="2a6db-144">Remove custom adapters after uninstalling the WCF LOB Adapter SDK</span></span>  

 <span data-ttu-id="2a6db-145">如果您已开发使用任何自定义适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并已在计算机上注册这些适配器，你还必须完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="2a6db-145">If you have developed any custom adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and you have registered these adapters on your computer, you must also complete the following procedure.</span></span>  

1.  <span data-ttu-id="2a6db-146">从全局程序集缓存 (GAC) 中删除自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="2a6db-146">Remove the custom adapter from the global assembly cache (GAC).</span></span>  

    1.  <span data-ttu-id="2a6db-147">打开**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-147">Open a **Visual Studio command prompt**.</span></span>  

    2.  <span data-ttu-id="2a6db-148">删除自定义**适配器.dll**从 GAC 中使用**命令 gacutil /u**。</span><span class="sxs-lookup"><span data-stu-id="2a6db-148">Remove the custom **adapter .dll** from the GAC using **command gacutil /u**.</span></span>  

2.  <span data-ttu-id="2a6db-149">删除自定义适配器绑定到从 machine.config 的引用</span><span class="sxs-lookup"><span data-stu-id="2a6db-149">Remove the references to the custom adapter binding from machine.config</span></span>  

    1.  <span data-ttu-id="2a6db-150">转到下的 machine.config 文件\<*系统驱动器*\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="2a6db-150">Go to the machine.config file under \<*system drive*\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    2.  <span data-ttu-id="2a6db-151">使用文本编辑器打开该文件。</span><span class="sxs-lookup"><span data-stu-id="2a6db-151">Open the file by using a text editor.</span></span>  

    3.  <span data-ttu-id="2a6db-152">元素 bindingExtensions、 客户端和 bindingElementExtensions system.serviceModel\extensions 下的搜索。</span><span class="sxs-lookup"><span data-stu-id="2a6db-152">Search for the element bindingExtensions, client and bindingElementExtensions under system.serviceModel\extensions.</span></span>  

    4.  <span data-ttu-id="2a6db-153">移除与自定义适配器的 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="2a6db-153">Remove the WCF binding that pertains to your custom adapter.</span></span>  

## <a name="do-a-silent-installation"></a><span data-ttu-id="2a6db-154">执行无提示安装</span><span class="sxs-lookup"><span data-stu-id="2a6db-154">Do a silent installation</span></span>  
 <span data-ttu-id="2a6db-155">无提示安装非常适合于测试方案或大型企业部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a6db-155">A silent installation is ideal for test scenarios or as part of a large-scale enterprise deployment.</span></span> [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] <span data-ttu-id="2a6db-156">提供命令行参数，您可以使用与 AdapterFramework.msi 执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="2a6db-156">provides command line parameters that you can use with AdapterFramework.msi to perform a silent installation.</span></span>  

> [!NOTE]
>  <span data-ttu-id="2a6db-157">若要执行无提示安装，应是计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="2a6db-157">To perform silent installation, you should be an Administrator on the computer.</span></span> 


1. <span data-ttu-id="2a6db-158">以管理员身份打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2a6db-158">Open a command prompt as administrator.</span></span>  

2. <span data-ttu-id="2a6db-159">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="2a6db-159">Type the following:</span></span>

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   <span data-ttu-id="2a6db-160">使用下列命令行选项与 AdapterFramework.msi 结合使用：</span><span class="sxs-lookup"><span data-stu-id="2a6db-160">Use the following command line options in conjunction with AdapterFramework.msi:</span></span>  

   * <span data-ttu-id="2a6db-161">使用`/quiet`若要安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以无提示方式。</span><span class="sxs-lookup"><span data-stu-id="2a6db-161">Use `/quiet` to install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] silently.</span></span>  

   * <span data-ttu-id="2a6db-162">使用 MUOPTIN ="Yes"&#124;"否"以指示如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="2a6db-162">Use MUOPTIN=”Yes”&#124;”No” to indicate if the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] should check for updates with Microsoft Update.</span></span>  

       <span data-ttu-id="2a6db-163">当设置为 Yes，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查通过 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="2a6db-163">When set to Yes, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] checks for updates through Microsoft Update.</span></span> <span data-ttu-id="2a6db-164">当设置为 no[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不会检查与 Microsoft Update 的更新。</span><span class="sxs-lookup"><span data-stu-id="2a6db-164">When set to no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not check for updates with Microsoft Update.</span></span>  

> [!NOTE]
>  <span data-ttu-id="2a6db-165">若要显示的命令行安装的其他选项，请键入`AdapterFramework.msi /?`在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="2a6db-165">To display additional options for command line installation, type `AdapterFramework.msi /?`at the command prompt.</span></span>  

