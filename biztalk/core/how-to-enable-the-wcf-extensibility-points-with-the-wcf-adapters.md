---
title: "如何启用与 WCF 适配器 WCF 扩展点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, WCF adapters
- WCF adapters, extensibility ports
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e481521ba651fe8c1e66ea4f730d05375451f111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a><span data-ttu-id="bc740-102">如何启用 WCF 适配器的 WCF 扩展点</span><span class="sxs-lookup"><span data-stu-id="bc740-102">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>
<span data-ttu-id="bc740-103">本主题说明如何对 WCF-Custom 和 WCF-CustomIsolated 适配器启用三种 WCF 扩展点：行为扩展、绑定元素扩展和绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="bc740-103">This topic describes how to enable three WCF extensibility points—behavior extension, binding element extension, and binding extension—with the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="bc740-104">若要执行此操作，首先应将用于实现 WCF 扩展点的程序集安装到全局程序集缓存 (GAC) 中，然后修改计算机上的 machine.config 文件，最后再使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置 WCF-Custom 或 WCF-CustomIsolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="bc740-104">To do so, you first install the assemblies implementing the WCF extensibility points in the global assembly cache (GAC), then modify the machine.config file on your computers, and then configure the WCF-Custom or the WCF-CustomIsolated adapter by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="bc740-105">有关 WCF 扩展性点的详细信息，请参阅"扩展 WCF"网址[http://go.microsoft.com/fwlink/?LinkId=86380](http://go.microsoft.com/fwlink/?LinkId=86380)。</span><span class="sxs-lookup"><span data-stu-id="bc740-105">For more information about the WCF extensibility points, see "Extending WCF" at [http://go.microsoft.com/fwlink/?LinkId=86380](http://go.microsoft.com/fwlink/?LinkId=86380).</span></span>  
  
 <span data-ttu-id="bc740-106">有关如何启用 WCF 扩展点的详细信息，请参阅"SDK 示例:: 使用自定义绑定扩展使用的 WCF 自定义适配器"网址[http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185)。</span><span class="sxs-lookup"><span data-stu-id="bc740-106">For more information about how to enable the WCF extensibility points, see "SDK Sample: Using Custom Binding Extensions with the WCF-Custom Adapters" at [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc740-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="bc740-107">Prerequisites</span></span>  
 <span data-ttu-id="bc740-108">若要执行本主题中的过程，你必须登录使用的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="bc740-108">To perform the procedures in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="bc740-109">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bc740-109">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a><span data-ttu-id="bc740-110">将实现 WCF 扩展点的程序集安装到 GAC</span><span class="sxs-lookup"><span data-stu-id="bc740-110">To install assemblies implementing a WCF extensibility point in the GAC</span></span>  
  
1.  <span data-ttu-id="bc740-111">将实现 WCF 扩展点的程序集复制到本地计算机上的某一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bc740-111">Copy the assemblies implementing the WCF extensibility point to a folder on your local computer.</span></span>  
  
2.  <span data-ttu-id="bc740-112">将 WCF 扩展点所使用的程序集（如果有）复制到本地计算机上的某一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bc740-112">Copy the assemblies that the WCF extensibility point uses, if any, to a folder on your local computer.</span></span>  
  
3.  <span data-ttu-id="bc740-113">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="bc740-113">Start the **Visual Studio Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="bc740-114">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="bc740-114">Type the following command:</span></span>  
  
     <span data-ttu-id="bc740-115">**gacutil.exe /if"\<**  *的程序集.dll 文件的路径* **>"**</span><span class="sxs-lookup"><span data-stu-id="bc740-115">**gacutil.exe /if "\<** *path to the assembly .dll file* **>"**</span></span>  
  
5.  <span data-ttu-id="bc740-116">此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="bc740-116">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
6.  <span data-ttu-id="bc740-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，针对你在此过程的步骤 1 和 2 中复制的所有程序集重复执行步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="bc740-117">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, repeat steps 4 and 5 against all the assemblies you copied in steps 1 and 2 of this procedure.</span></span>  
  
7.  <span data-ttu-id="bc740-118">如果你具有多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机和管理计算机，则在所有计算机上重复此过程的步骤 1 至 6。</span><span class="sxs-lookup"><span data-stu-id="bc740-118">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 6 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-119">若要启用 WCF 适配器的 WCF 扩展点，运行该适配器的 BizTalk 主机实例必须能够在运行时加载在其中实现 WCF 扩展点的程序集。</span><span class="sxs-lookup"><span data-stu-id="bc740-119">To enable WCF extensibility points for the WCF adapters, the BizTalk Host instance running the adapter must be able to load at run time the assemblies where the WCF extensibility points are implemented.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-binding-extension"></a><span data-ttu-id="bc740-120">为 WCF 绑定扩展配置 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="bc740-120">To configure the machine.config file for a WCF binding extension</span></span>  
  
1.  <span data-ttu-id="bc740-121">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-121">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="bc740-122">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel >\\< 扩展\>**元素，将这些元素内的添加 **\<配置 >**元素的 machine.config 文件，，然后添加 **\<bindingExtensions >**内的 WCF 绑定扩展元素 **\<system.serverModel >\\< 扩展\>**元素。</span><span class="sxs-lookup"><span data-stu-id="bc740-122">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<bindingExtensions>** element for a WCF binding extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="bc740-123">例如，若要启用的自定义绑定扩展，netHttpBinding，添加以下代码**\<配置 >** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="bc740-123">For example, to enable a custom binding extension, netHttpBinding, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="bc740-124">你可以找到通过使用的命令，来注册的程序集信息**gacutil /lr** *< 程序集 _ 名称 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-124">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-125">有关详细信息 **<bindingExtensions>** 元素，请参阅"<bindingExtensions>"在[http://go.microsoft.com/fwlink/?LinkID=86180](http://go.microsoft.com/fwlink/?LinkID=86180)。</span><span class="sxs-lookup"><span data-stu-id="bc740-125">For more information about the **<bindingExtensions>** element, see "<bindingExtensions>" at [http://go.microsoft.com/fwlink/?LinkID=86180](http://go.microsoft.com/fwlink/?LinkID=86180).</span></span>  
  
3.  <span data-ttu-id="bc740-126">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-126">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="bc740-127">如果你有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机，重复步骤 1 到 3 在此过程中的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="bc740-127">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-128">你必须在所有计算机上对 WCF 基础结构重复这些步骤，才能处理 BizTalk 主机实例和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的 WCF 扩展点。</span><span class="sxs-lookup"><span data-stu-id="bc740-128">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="bc740-129">使用 BizTalk 管理控制台配置 WCF 绑定扩展</span><span class="sxs-lookup"><span data-stu-id="bc740-129">To configure a WCF binding extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="bc740-130">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bc740-130">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-131">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台已经打开，则重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bc740-131">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="bc740-132">如果使用 WCF-Custom 适配器，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中依次展开“平台设置”、“主机实例”，然后重新启动运行该适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bc740-132">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="bc740-133">如果使用 WCF-CustomIsolated 适配器，则在 IIS 管理控制台中重新启动与 WCF 接收位置相关联的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="bc740-133">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="bc740-134">如果你想要配置接收位置以便使用中的 WCF 扩展性点，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*展开**接收位置**，，然后在右窗格中，双击*\<接收位置 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-134">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="bc740-135">在**接收位置属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**或**WCF CustomIsolated**具体取决于你想要使用，并依次 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-135">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="bc740-136">如果你想要配置发送端口以使用中的 WCF 扩展性点，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*，展开**发送端口**，，然后在右窗格中，双击*\<发送端口 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-136">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="bc740-137">在**发送端口属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-137">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="bc740-138">在传输属性对话框中，在**绑定**选项卡，选择绑定扩展，然后配置该传输的设置的其余部分。</span><span class="sxs-lookup"><span data-stu-id="bc740-138">In the transport properties dialog box, on the **Binding** tab, select the binding extension, and then configure the rest of the settings for the transport.</span></span>  
  
7.  <span data-ttu-id="bc740-139">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，通过单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="bc740-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a><span data-ttu-id="bc740-140">为 WCF 绑定元素扩展配置 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="bc740-140">To configure the machine.config file for a WCF binding element extension</span></span>  
  
1.  <span data-ttu-id="bc740-141">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-141">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="bc740-142">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel >\\< 扩展\>**元素，将这些元素内的添加 **\<配置 >**元素的 machine.config 文件，，然后添加 **\<bindingElementExtensions >**元素内的 WCF 绑定元素扩展 **\<system.serverModel >\\< 扩展\>**元素。</span><span class="sxs-lookup"><span data-stu-id="bc740-142">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<bindingElementExtensions>** element for a WCF binding element extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="bc740-143">例如，若要启用自定义绑定元素扩展，droppingInterceptor，添加以下代码**\<配置 >** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="bc740-143">For example, to enable a custom binding element extension, droppingInterceptor, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="bc740-144">你可以找到通过使用的命令，来注册的程序集信息**gacutil /lr** *< 程序集 _ 名称 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-144">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-145">有关详细信息 **<bindingElementExtensions>** 元素，请参阅"<bindingElementExtensions>"在[http://go.microsoft.com/fwlink/?LinkId=86381](http://go.microsoft.com/fwlink/?LinkId=86381)。</span><span class="sxs-lookup"><span data-stu-id="bc740-145">For more information about the **<bindingElementExtensions>** element, see "<bindingElementExtensions>" at [http://go.microsoft.com/fwlink/?LinkId=86381](http://go.microsoft.com/fwlink/?LinkId=86381).</span></span>  
  
3.  <span data-ttu-id="bc740-146">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-146">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="bc740-147">如果你有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机，重复步骤 1 到 3 在此过程中的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="bc740-147">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-148">你必须在所有计算机上对 WCF 基础结构重复这些步骤，才能处理 BizTalk 主机实例和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的 WCF 扩展点。</span><span class="sxs-lookup"><span data-stu-id="bc740-148">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="bc740-149">使用 BizTalk 管理控制台配置 WCF 绑定元素扩展</span><span class="sxs-lookup"><span data-stu-id="bc740-149">To configure a WCF binding element extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="bc740-150">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bc740-150">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-151">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台已经打开，则重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bc740-151">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="bc740-152">如果使用 WCF-Custom 适配器，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中依次展开“平台设置”、“主机实例”，然后重新启动运行该适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bc740-152">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="bc740-153">如果使用 WCF-CustomIsolated 适配器，则在 IIS 管理控制台中重新启动与 WCF 接收位置相关联的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="bc740-153">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="bc740-154">如果你想要配置接收位置以便使用中的 WCF 扩展性点，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*展开**接收位置**，，然后在右窗格中，双击*\<接收位置 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-154">If you want to configure a receive location to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="bc740-155">在**接收位置属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**或**WCF CustomIsolated**具体取决于你想要使用，并依次 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-155">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="bc740-156">如果你想要配置发送端口以使用中的 WCF 扩展性点，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*，展开**发送端口**，，然后在右窗格中，双击*\<发送端口 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-156">If you want to configure a send port to use a WCF extensibility point, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="bc740-157">在**发送端口属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-157">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="bc740-158">在传输属性对话框中，在**绑定**选项卡上，在**绑定类型**下拉列表中，选择**customBinding**。</span><span class="sxs-lookup"><span data-stu-id="bc740-158">In the transport properties dialog box, on the **Binding** tab, in the **Binding Type** drop-down list, select **customBinding**.</span></span>  
  
7.  <span data-ttu-id="bc740-159">在传输属性对话框中，在**绑定**选项卡上，右键单击的客户端区域**绑定**列表，，然后单击**将扩展添加**。</span><span class="sxs-lookup"><span data-stu-id="bc740-159">In the transport properties dialog box, on the **Binding** tab, right-click the client area of the **Binding** list, and then click **Add extension**.</span></span>  
  
8.  <span data-ttu-id="bc740-160">在**选择绑定元素扩展**对话框中，选择绑定元素扩展，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bc740-160">In the **Select Binding Element Extension** dialog box, select a binding element extension, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="bc740-161">在传输属性对话框中，在**绑定**选项卡上，调整中添加的绑定元素的顺序**绑定**具体取决于你在中添加的绑定元素扩展的类型的列表上一步，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc740-161">In the transport properties dialog box, on the **Binding** tab, adjust the order of the binding elements added in the **Binding** list depending on the type of the binding element extension you added in the previous step as follows:</span></span>  
  
    -   <span data-ttu-id="bc740-162">在**绑定**列表，绑定元素扩展，请右键单击，然后单击**移扩展**或**下移扩展**。</span><span class="sxs-lookup"><span data-stu-id="bc740-162">In the **Binding** list, right-click a binding element extension, and then click **Move extension up** or **Move extension down**.</span></span> <span data-ttu-id="bc740-163">中的最低绑定元素扩展**绑定**列表对应于通道堆栈的底部组件。</span><span class="sxs-lookup"><span data-stu-id="bc740-163">The lowest binding element extension in the **Binding** list corresponds to the bottom component of the channel stack.</span></span> <span data-ttu-id="bc740-164">中的最高的绑定元素**绑定**列表对应的通信堆栈的顶部组件。</span><span class="sxs-lookup"><span data-stu-id="bc740-164">The highest binding element in the **Binding** list corresponds to the top component of the communication stack.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bc740-165">有关自定义绑定的绑定元素的特定顺序的详细信息，请参阅"自定义绑定"网址[http://go.microsoft.com/fwlink/?LinkId=86383](http://go.microsoft.com/fwlink/?LinkId=86383)。</span><span class="sxs-lookup"><span data-stu-id="bc740-165">For more information about the specific order of the binding elements for the custom binding, see "Custom Bindings" at [http://go.microsoft.com/fwlink/?LinkId=86383](http://go.microsoft.com/fwlink/?LinkId=86383).</span></span>  
  
10. <span data-ttu-id="bc740-166">在“传输属性”对话框中，为传输配置其余设置。</span><span class="sxs-lookup"><span data-stu-id="bc740-166">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
11. <span data-ttu-id="bc740-167">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，通过单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="bc740-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a><span data-ttu-id="bc740-168">为 WCF 行为扩展配置 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="bc740-168">To configure the machine.config file for a WCF behavior extension</span></span>  
  
1.  <span data-ttu-id="bc740-169">在命令提示符处，转到 %frameworkdir%\v4。X.XXXXX\CONFIG 文件夹，然后打开**machine.config**通过使用记事本的文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-169">At a command prompt, go to the %FrameworkDir%\v4.X.XXXXX\CONFIG folder, and then open the **machine.config** file by using Notepad.</span></span>  
  
2.  <span data-ttu-id="bc740-170">在记事本中，如果 machine.config 文件不具有 **\<system.serverModel >\\< 扩展\>**元素，将这些元素内的添加 **\<配置 >**元素的 machine.config 文件，，然后添加 **\<behaviorExtensions >**内的 WCF 行为扩展元素 **\<system.serverModel >\\< 扩展\>**元素。</span><span class="sxs-lookup"><span data-stu-id="bc740-170">In Notepad, if the machine.config file does not have the **\<system.serverModel>\\<extensions\>** elements, add those elements inside the **\<configuration>** element of the machine.config file, and then add the **\<behaviorExtensions>** element for a WCF behavior extension inside the **\<system.serverModel>\\<extensions\>** elements.</span></span> <span data-ttu-id="bc740-171">例如，若要启用的自定义行为扩展，schemaValidator，添加以下代码**\<配置 >** machine.config 文件的元素：</span><span class="sxs-lookup"><span data-stu-id="bc740-171">For example, To enable a custom behavior extension, schemaValidator, add the following code inside the **\<configuration>** element of the machine.config file:</span></span>  
  
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
    >  <span data-ttu-id="bc740-172">你可以找到通过使用的命令，来注册的程序集信息**gacutil /lr** *< 程序集 _ 名称 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-172">You can find the information for the assemblies to register by using the command, **gacutil /lr** *<assembly_name>*.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-173">有关详细信息 **<behaviorExtensions>** 元素，请参阅"<behaviorExtensions>"在[http://go.microsoft.com/fwlink/?LinkId=86382](http://go.microsoft.com/fwlink/?LinkId=86382)。</span><span class="sxs-lookup"><span data-stu-id="bc740-173">For more information about the **<behaviorExtensions>** element, see "<behaviorExtensions>" at  [http://go.microsoft.com/fwlink/?LinkId=86382](http://go.microsoft.com/fwlink/?LinkId=86382).</span></span>  
  
3.  <span data-ttu-id="bc740-174">在记事本中，保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bc740-174">In Notepad, save the machine.config file.</span></span>  
  
4.  <span data-ttu-id="bc740-175">如果你有多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和管理计算机，重复步骤 1 到 3 在此过程中的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="bc740-175">If you have multiple [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers and administration computers, repeat steps 1 through 3 of this procedure on all the computers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-176">你必须在所有计算机上对 WCF 基础结构重复这些步骤，才能处理 BizTalk 主机实例和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的 WCF 扩展点。</span><span class="sxs-lookup"><span data-stu-id="bc740-176">You have to repeat these steps on all the computers for the WCF infrastructure to process the WCF extensibility point for the BizTalk Host instance and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="to-configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a><span data-ttu-id="bc740-177">使用 BizTalk 管理控制台配置 WCF 行为扩展</span><span class="sxs-lookup"><span data-stu-id="bc740-177">To configure a WCF behavior extension by using the BizTalk Administration console</span></span>  
  
1.  <span data-ttu-id="bc740-178">单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bc740-178">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc740-179">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台已经打开，则重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bc740-179">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console is already opened, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="bc740-180">如果使用 WCF-Custom 适配器，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中依次展开“平台设置”、“主机实例”，然后重新启动运行该适配器的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bc740-180">If you use the WCF-Custom adapter, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand Platform Settings, expand Host Instances, and then restart the BizTalk Host instance running the adapter.</span></span>  
  
3.  <span data-ttu-id="bc740-181">如果使用 WCF-CustomIsolated 适配器，则在 IIS 管理控制台中重新启动与 WCF 接收位置相关联的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="bc740-181">If you use the WCF-CustomIsolated adapter, in the IIS Management console, restart the application pool associated with the WCF receive location.</span></span>  
  
4.  <span data-ttu-id="bc740-182">如果你想要配置接收位置以便使用 WCF 扩展性点时，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*，展开**接收位置**，，然后在右窗格中，双击*\<接收位置 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-182">If you want to configure a receive location to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Receive Locations**, and then in the right pane, double-click *\<Receive location>*.</span></span>  
  
    -   <span data-ttu-id="bc740-183">在**接收位置属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**或**WCF CustomIsolated**具体取决于你想要使用，并依次 WCF 适配器**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-183">In the **Receive Location Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom** or **WCF-CustomIsolated** depending on the WCF adapter that you want to use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="bc740-184">如果你想要配置发送端口以使用 WCF 扩展性点时，在 BizTalk 管理控制台中，展开**BizTalk 组**，展开 *\<BizTalk 应用程序 >*，展开**发送端口**，，然后在右窗格中，双击*\<发送端口 >*。</span><span class="sxs-lookup"><span data-stu-id="bc740-184">If you want to configure a send port to use a WCF extensibility point, in the BizTalk Administration console, expand **BizTalk Group**, expand *\<BizTalk application>*, expand **Send Ports**, and then in the right pane, double-click *\<Send port>*.</span></span>  
  
    -   <span data-ttu-id="bc740-185">在**发送端口属性**对话框中，在**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="bc740-185">In the **Send Port Properties** dialog box, in the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="bc740-186">在传输属性对话框中，在**行为**选项卡上，右键单击**ServiceBehavior**或**EndpointBehavior**根据行为扩展的类型然后，在**选择行为扩展**对话框中，选择行为扩展，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bc740-186">In the transport properties dialog box, on the **Behavior** tab, right-click **ServiceBehavior** or **EndpointBehavior** depending on the type of the behavior extension, and then, in the **Select Behavior Extension** dialog box, select the behavior extension, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="bc740-187">在“传输属性”对话框中，为传输配置其余设置。</span><span class="sxs-lookup"><span data-stu-id="bc740-187">In the transport properties dialog box, configure the rest of the settings for the transport.</span></span>  
  
8.  <span data-ttu-id="bc740-188">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，通过单击关闭所有打开的对话框**确定**按钮，并确保不出现任何错误消息和错误事件日志。</span><span class="sxs-lookup"><span data-stu-id="bc740-188">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, close all open dialog boxes by clicking the **OK** buttons, and then make sure that no error messages and erroneous event logs appear.</span></span>  
  
### <a name="to-configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a><span data-ttu-id="bc740-189">配置带有 SSL 证书的 WCF-Custom 接收位置</span><span class="sxs-lookup"><span data-stu-id="bc740-189">To configure a WCF-Custom receive location with an SSL certificate</span></span>  
  
-   <span data-ttu-id="bc740-190">如果 WCF 自定义接收位置碰巧使用 HTTP 内核模式驱动程序 (HTTP.sys)，如**httpsTransport**绑定元素，用于安全套接字层 (SSL) 进行通信，接收位置必须具有证书注册为每个套接字 （IP 地址/端口组合）。</span><span class="sxs-lookup"><span data-stu-id="bc740-190">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element, for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="bc740-191">使用 HttpCfg.exe 工具可将 SSL 证书绑定到计算机上的端口。</span><span class="sxs-lookup"><span data-stu-id="bc740-191">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="bc740-192">有关详细信息，请参阅"如何为:: 配置端口使用 SSL 证书" [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384)。</span><span class="sxs-lookup"><span data-stu-id="bc740-192">For more information, see "How To: Configure a Port with An SSL Certificate" at [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384).</span></span>