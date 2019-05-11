---
title: 启用使用 WCF 适配器的 WCF 扩展点 |Microsoft Docs
description: 安装程序集、 配置 machine.config，将扩展添加到 BizTalk 管理员、 创建接收位置启用 WCF 适配器在 BizTalk Server 中的 WCF 扩展点
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7b45169a80b0acbb1a51ca410932815c1bd773
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337892"
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a><span data-ttu-id="be021-103">如何启用 WCF 适配器的 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="be021-103">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>
<span data-ttu-id="be021-104">启用三种 WCF 扩展点，行为扩展、 绑定元素扩展和绑定扩展 — 通过 Wcf-custom 和 Wcf-customisolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="be021-104">Enable three WCF extensibility points—behavior extension, binding element extension, and binding extension—with the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="be021-105">若要执行此操作，首先安装在全局程序集缓存 (GAC) 中实现 WCF 扩展点的程序集，然后修改你的计算机上的 machine.config 文件然后使用和配置 Wcf-custom 或 Wcf-customisolated 适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-105">To do so, you first install the assemblies implementing the WCF extensibility points in the global assembly cache (GAC), then modify the machine.config file on your computers, and then configure the WCF-Custom or the WCF-CustomIsolated adapter by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
<span data-ttu-id="be021-106">请参阅[Extending WCF](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf)有关 WCF 扩展点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be021-106">See [Extending WCF](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf) for more info on WCF extensibility points.</span></span>
  
 
## <a name="prerequisites"></a><span data-ttu-id="be021-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="be021-107">Prerequisites</span></span>  
<span data-ttu-id="be021-108">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="be021-108">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="be021-109">[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="be021-109">[Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md) provides more info.</span></span>  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a><span data-ttu-id="be021-110">安装在 GAC 中实现 WCF 扩展点的程序集</span><span class="sxs-lookup"><span data-stu-id="be021-110">Install assemblies implementing a WCF extensibility point in the GAC</span></span>  
  
1. <span data-ttu-id="be021-111">将复制到的文件夹的 WCF 扩展点实现在本地计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="be021-111">Copy the assemblies implementing the WCF extensibility point to a folder on your local computer.</span></span>  
  
2. <span data-ttu-id="be021-112">将复制的程序集的使用 WCF 扩展点，如果有，到在本地计算机上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="be021-112">Copy the assemblies that the WCF extensibility point uses, if any, to a folder on your local computer.</span></span>  
  
3. <span data-ttu-id="be021-113">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="be021-113">Start the **Visual Studio Command Prompt**.</span></span>  
  
4. <span data-ttu-id="be021-114">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="be021-114">Type the following command:</span></span>  
  
    <span data-ttu-id="be021-115">**gacutil.exe /if"\<**  *程序集.dll 文件路径*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="be021-115">**gacutil.exe /if "\<** *path to the assembly .dll file* **\>"**</span></span>  
  
5. <span data-ttu-id="be021-116">这会将程序集安装到 GAC，覆盖任何现有的程序集都具有相同的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="be021-116">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
6. <span data-ttu-id="be021-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，针对你在此过程的步骤 1 和 2 中复制的所有程序集重复执行步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="be021-117">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, repeat steps 4 and 5 against all the assemblies you copied in steps 1 and 2 of this procedure.</span></span>  
  
7. <span data-ttu-id="be021-118">如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 至 6 在此过程的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="be021-118">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 6 of this procedure on all the computers.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-119">若要启用 WCF 适配器的 WCF 扩展点，运行该适配器的 BizTalk 主机实例必须能够在运行时加载程序集实现 WCF 扩展点的位置。</span><span class="sxs-lookup"><span data-stu-id="be021-119">To enable WCF extensibility points for the WCF adapters, the BizTalk Host instance running the adapter must be able to load at run time the assemblies where the WCF extensibility points are implemented.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a><span data-ttu-id="be021-120">配置 WCF 绑定扩展在 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="be021-120">Configure the machine.config file for a WCF binding extension</span></span>  
  
1. <span data-ttu-id="be021-121">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="be021-121">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2. <span data-ttu-id="be021-122">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<bindingExtensions\>** 内部 WCF 绑定扩展元素 **\<system.serverModel\>\\< 扩展\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="be021-122">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<bindingExtensions\>** element for a WCF binding extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="be021-123">例如，若要启用自定义绑定扩展 netHttpBinding，添加以下代码**\<配置\>** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="be021-123">For example, to enable a custom binding extension, netHttpBinding, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
         <add name="netHttpBinding" type="Microsoft.Samples.Channels.NetHttpBindingCollectionElement, NetHttpBinding, Version=3.0.0.0, Culture=neutral, PublicKeyToken=5b637b51c4aaa2a8" />  
       </bindingExtensions>        
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - <span data-ttu-id="be021-124">您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。</span><span class="sxs-lookup"><span data-stu-id="be021-124">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
   >  - <span data-ttu-id="be021-125">请参阅[bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions)此元素上。</span><span class="sxs-lookup"><span data-stu-id="be021-125">See [bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions) on this element.</span></span>
  
3. <span data-ttu-id="be021-126">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="be021-126">In Notepad, save the machine.config file.</span></span>  
  
4. <span data-ttu-id="be021-127">如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="be021-127">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-128">您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-128">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="be021-129">使用 BizTalk 管理控制台配置 WCF 绑定扩展</span><span class="sxs-lookup"><span data-stu-id="be021-129">Configure a WCF binding extension by using the BizTalk Administration console</span></span>  
  
1. <span data-ttu-id="be021-130">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="be021-130">Open **BizTalk Server Administration**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-131">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-131">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="be021-132">如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="be021-132">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3. <span data-ttu-id="be021-133">如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="be021-133">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4. <span data-ttu-id="be021-134">如果你想要配置接收位置以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-134">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
   -   <span data-ttu-id="be021-135">在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-135">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="be021-136">如果你想要配置发送端口以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中双击*\<发送端口\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-136">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
   -   <span data-ttu-id="be021-137">在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-137">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="be021-138">在传输属性对话框中，在**绑定**选项卡上，选择绑定扩展，然后配置该传输的设置的其余部分。</span><span class="sxs-lookup"><span data-stu-id="be021-138">In the transport properties dialog box, on the **Binding** tab, select the binding extension, and then configure the rest of the settings for the transport.</span></span>  
  
7. <span data-ttu-id="be021-139">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="be021-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a><span data-ttu-id="be021-140">配置 WCF 绑定元素扩展在 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="be021-140">Configure the machine.config file for a WCF binding element extension</span></span>  
  
1. <span data-ttu-id="be021-141">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="be021-141">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2. <span data-ttu-id="be021-142">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<bindingElementExtensions\>** WCF 绑定元素的元素扩展内部 **\<system.serverModel\>\\< 扩展\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="be021-142">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<bindingElementExtensions\>** element for a WCF binding element extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="be021-143">例如，若要启用的自定义绑定元素扩展 Roppinginterceptor，请添加以下代码**\<配置\>** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="be021-143">For example, to enable a custom binding element extension, droppingInterceptor, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="droppingInterceptor" type="Microsoft.ServiceModel.Samples.DroppingServerElement, MessageInterceptor, Version=0.0.0.0, Culture=neutral, PublicKeyToken=098514eef14aa34a"/>  
       </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   > - <span data-ttu-id="be021-144">您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。</span><span class="sxs-lookup"><span data-stu-id="be021-144">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
   > - <span data-ttu-id="be021-145">请参阅[bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions)此元素上。</span><span class="sxs-lookup"><span data-stu-id="be021-145">See [bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions) on this element.</span></span>
  
3. <span data-ttu-id="be021-146">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="be021-146">In Notepad, save the machine.config file.</span></span>  
  
4. <span data-ttu-id="be021-147">如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="be021-147">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-148">您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-148">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="be021-149">使用 BizTalk 管理控制台配置 WCF 绑定元素扩展</span><span class="sxs-lookup"><span data-stu-id="be021-149">Configure a WCF binding element extension by using the BizTalk Administration console</span></span>  
  
1. <span data-ttu-id="be021-150">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="be021-150">Open **BizTalk Server Administration**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-151">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-151">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="be021-152">如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="be021-152">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3. <span data-ttu-id="be021-153">如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="be021-153">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4. <span data-ttu-id="be021-154">如果你想要配置接收位置以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-154">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
   -   <span data-ttu-id="be021-155">在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-155">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="be021-156">如果你想要配置发送端口以使用 WCF 扩展点，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中双击*\<发送端口\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-156">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
   -   <span data-ttu-id="be021-157">在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-157">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="be021-158">在传输属性对话框中，在**绑定**选项卡上，在**绑定类型**下拉列表中，选择**customBinding**。</span><span class="sxs-lookup"><span data-stu-id="be021-158">In the transport properties dialog box, on the **Binding** tab, in the **Binding Type** drop-down list, select **customBinding**.</span></span>  
  
7. <span data-ttu-id="be021-159">在传输属性对话框中，在**绑定**选项卡上，右键单击的工作区**绑定**列表，，然后单击**将扩展添加**。</span><span class="sxs-lookup"><span data-stu-id="be021-159">In the transport properties dialog box, on the **Binding** tab, right-click the client area of the **Binding** list, and then click **Add extension**.</span></span>  
  
8. <span data-ttu-id="be021-160">在中**选择绑定元素扩展**对话框中，选择绑定元素扩展，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="be021-160">In the **Select Binding Element Extension** dialog box, select a binding element extension, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="be021-161">在传输属性对话框中，在**绑定**选项卡上，调整中添加的绑定元素的顺序**绑定**具体取决于您在中添加的绑定元素扩展的类型的列表按如下所示的上一步：</span><span class="sxs-lookup"><span data-stu-id="be021-161">In the transport properties dialog box, on the **Binding** tab, adjust the order of the binding elements added in the **Binding** list depending on the type of the binding element extension you added in the previous step as follows:</span></span>  
  
    -   <span data-ttu-id="be021-162">在中**绑定**列表中，右键单击绑定元素扩展，然后单击**移扩展**或**下移扩展**。</span><span class="sxs-lookup"><span data-stu-id="be021-162">In the **Binding** list, right-click a binding element extension, and then click **Move extension up** or **Move extension down**.</span></span> <span data-ttu-id="be021-163">在最低的绑定元素扩展**绑定**列表与通道堆栈的底部组件相对应。</span><span class="sxs-lookup"><span data-stu-id="be021-163">The lowest binding element extension in the **Binding** list corresponds to the bottom component of the channel stack.</span></span> <span data-ttu-id="be021-164">中的最高的绑定元素**绑定**列表与通信堆栈的顶部组件相对应。</span><span class="sxs-lookup"><span data-stu-id="be021-164">The highest binding element in the **Binding** list corresponds to the top component of the communication stack.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="be021-165">请参阅[自定义绑定](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings)有关自定义绑定的绑定元素的特定顺序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be021-165">See [Custom Bindings](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings) for details about the specific order of the binding elements for the custom binding.</span></span>
  
10. <span data-ttu-id="be021-166">在传输属性对话框中，将配置该传输的设置的其余部分。</span><span class="sxs-lookup"><span data-stu-id="be021-166">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
11. <span data-ttu-id="be021-167">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="be021-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a><span data-ttu-id="be021-168">配置 WCF 行为扩展在 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="be021-168">Configure the machine.config file for a WCF behavior extension</span></span>  
  
1. <span data-ttu-id="be021-169">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="be021-169">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2. <span data-ttu-id="be021-170">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel\>\\< 扩展\>** 元素，将这些元素添加 **\<配置\>** 元素在 machine.config 文件，并添加**\<behaviorExtensions\>** WCF 行为扩展元素内部 **\<system.serverModel\>\\< 扩展\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="be021-170">In Notepad, if the machine.config file does not have the **\<system.serverModel\>\\<extensions\>** elements, add those elements inside the **\<configuration\>** element of the machine.config file, and then add the **\<behaviorExtensions\>** element for a WCF behavior extension inside the **\<system.serverModel\>\\<extensions\>** elements.</span></span> <span data-ttu-id="be021-171">例如，若要启用自定义行为扩展 schemaValidator，添加以下代码**\<配置\>** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="be021-171">For example, To enable a custom behavior extension, schemaValidator, add the following code inside the **\<configuration\>** element of the machine.config file:</span></span>  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <behaviorExtensions>  
         <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ad307e213604f592"/>  
       </behaviorExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - <span data-ttu-id="be021-172">您可以找到要使用该命令，注册的程序集的信息**gacutil /lr** *< assembly_name >*。</span><span class="sxs-lookup"><span data-stu-id="be021-172">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
   >  - <span data-ttu-id="be021-173">请参阅[behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions)此元素上。</span><span class="sxs-lookup"><span data-stu-id="be021-173">See [behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions) on this element.</span></span>
  
3. <span data-ttu-id="be021-174">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="be021-174">In Notepad, save the machine.config file.</span></span>  
  
4. <span data-ttu-id="be021-175">如果有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机重复步骤 1 到 3 在此过程的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="be021-175">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-176">您必须对 WCF 基础结构来处理的 BizTalk 主机实例的 WCF 扩展点的所有计算机上重复这些步骤和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-176">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="be021-177">使用 BizTalk 管理控制台配置 WCF 行为扩展</span><span class="sxs-lookup"><span data-stu-id="be021-177">Configure a WCF behavior extension by using the BizTalk Administration console</span></span>  
  
1. <span data-ttu-id="be021-178">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="be021-178">Open **BizTalk Server Administration**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="be021-179">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台已经打开，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="be021-179">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="be021-180">如果使用 Wcf-custom 适配器，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开平台设置、 主机实例，，然后重新启动运行适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="be021-180">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3. <span data-ttu-id="be021-181">如果使用 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动应用程序池关联通过 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="be021-181">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4. <span data-ttu-id="be021-182">如果你想要配置接收位置以使用 WCF 扩展点，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**接收位置**，然后在右窗格中双击*\<接收位置\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-182">If you want to configure a receive location to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location\>*.</span></span>  
  
   -   <span data-ttu-id="be021-183">在中**接收位置属性**对话框中**类型**下拉列表中，选择**WCF 自定义**或者**Wcf-customisolated**根据你想要使用，然后单击的 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-183">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="be021-184">如果你想要配置发送端口以使用 WCF 扩展点，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序\>*，展开**发送端口**，然后在右窗格中，双击*\<发送端口\>*。</span><span class="sxs-lookup"><span data-stu-id="be021-184">If you want to configure a send port to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application\>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port\>*.</span></span>  
  
   -   <span data-ttu-id="be021-185">在中**发送端口属性**对话框中**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="be021-185">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="be021-186">在传输属性对话框中，在**行为**选项卡上，右键单击**ServiceBehavior**或**EndpointBehavior**根据行为扩展的类型然后，在**选择行为扩展**对话框中，选择行为扩展，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="be021-186">In the transport properties dialog box, on the **Behavior** tab, right-click **ServiceBehavior** or **EndpointBehavior** depending on the type of the behavior extension, and then, in the **Select Behavior Extension** dialog box, select the behavior extension, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="be021-187">在传输属性对话框中，将配置该传输的设置的其余部分。</span><span class="sxs-lookup"><span data-stu-id="be021-187">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
8. <span data-ttu-id="be021-188">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="be021-188">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a><span data-ttu-id="be021-189">配置 WCF 自定义接收位置使用 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="be021-189">Configure a WCF-Custom receive location with an SSL certificate</span></span>  
  
-   <span data-ttu-id="be021-190">如果 WCF 自定义接收位置正好在使用 HTTP 内核模式驱动程序 (HTTP.sys)，如**httpsTransport**绑定元素，对于安全套接字层 (SSL) 通信，接收位置必须具有证书为每个套接字 （IP 地址/端口组合） 注册。</span><span class="sxs-lookup"><span data-stu-id="be021-190">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element, for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="be021-191">使用 HttpCfg.exe 工具将 SSL 证书绑定到的计算机上的端口。</span><span class="sxs-lookup"><span data-stu-id="be021-191">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="be021-192">有关详细信息，请参阅本主题中的[如何使用 SSL 证书配置端口](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)。</span><span class="sxs-lookup"><span data-stu-id="be021-192">For more information, see [How To: Configure a Port with An SSL Certificate](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate).</span></span>