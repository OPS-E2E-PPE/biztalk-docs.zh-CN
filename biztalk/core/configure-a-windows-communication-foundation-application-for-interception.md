---
title: 如何配置 Windows Communication Foundation 应用程序用于侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b18790784f58dbdab7f917a73d041f382943d2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988902"
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a><span data-ttu-id="ec35d-102">如何配置 Windows Communication Foundation 应用程序用于侦听</span><span class="sxs-lookup"><span data-stu-id="ec35d-102">How to Configure a Windows Communication Foundation Application for Interception</span></span>
<span data-ttu-id="ec35d-103">必须安装 BAM 侦听器软件并将应用程序配置为使用 BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 侦听器服务后才能开始收集 BAM 活动数据。</span><span class="sxs-lookup"><span data-stu-id="ec35d-103">You must install the BAM interceptor software and configure your application to use the BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="ec35d-104">我们假定您已成功安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 及其依存关系，并至少创建了一个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="ec35d-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  

## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="ec35d-105">安装 Bam-eventing 软件</span><span class="sxs-lookup"><span data-stu-id="ec35d-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="ec35d-106">在可以将您的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 应用程序配置为对 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 使用 BAM 侦听器之前，您必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序安装 BAM-Eventing 软件。</span><span class="sxs-lookup"><span data-stu-id="ec35d-106">Before you can configure your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="ec35d-107">有关安装 Bam-eventing 软件和注册性能计数器的详细信息，请参阅[安装 Bam-eventing 软件](../core/installing-the-bam-eventing-software.md)。</span><span class="sxs-lookup"><span data-stu-id="ec35d-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  

## <a name="configuring-a-wcf-application-for-tracking"></a><span data-ttu-id="ec35d-108">配置 WCF 应用程序对其进行跟踪</span><span class="sxs-lookup"><span data-stu-id="ec35d-108">Configuring a WCF Application for Tracking</span></span>  
 <span data-ttu-id="ec35d-109">必须完成四项任务后，[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 应用程序才能开始编写 BAM 事件信息：</span><span class="sxs-lookup"><span data-stu-id="ec35d-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application can begin writing BAM event information:</span></span>  

- <span data-ttu-id="ec35d-110">必须使用创建观察模型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 工具，然后使用 BAM 管理器命令行工具 (bm.exe) 部署。</span><span class="sxs-lookup"><span data-stu-id="ec35d-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="ec35d-111">必须使用 BAM 管理器命令行工具 (bm.exe) 创建并部署侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec35d-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="ec35d-112">运行主机应用程序的用户必须是相应的 BAM 活动事件编写器的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取侦听器配置信息和写入到 BAM 活动中。</span><span class="sxs-lookup"><span data-stu-id="ec35d-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity\>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  

- <span data-ttu-id="ec35d-113">必须修改服务器和客户端应用程序的 App.config 文件才能加载 BAM 跟踪服务。</span><span class="sxs-lookup"><span data-stu-id="ec35d-113">The App.config file for the server and client application must be modified to load the BAM tracking service.</span></span> <span data-ttu-id="ec35d-114">修改 App.config 文件之后，必须重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec35d-114">After the App.config file has been modified, the application must be restarted.</span></span>  

  <span data-ttu-id="ec35d-115">只有成功完成这些任务之后，事件才开始出现在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中。</span><span class="sxs-lookup"><span data-stu-id="ec35d-115">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  

### <a name="deploying-an-observation-model"></a><span data-ttu-id="ec35d-116">部署观察模型</span><span class="sxs-lookup"><span data-stu-id="ec35d-116">Deploying an Observation Model</span></span>  
 <span data-ttu-id="ec35d-117">您必须先部署观察模型，然后才能在应用程序中部署侦听器配置文件或捕获 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="ec35d-117">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  

##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="ec35d-118">若要使用 bm.exe 部署观察模型</span><span class="sxs-lookup"><span data-stu-id="ec35d-118">To deploy an observation model by using bm.exe</span></span>  

1. <span data-ttu-id="ec35d-119">单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ec35d-119">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="ec35d-120">类型**cmd**中**打开**字段，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ec35d-120">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="ec35d-121">使用更改目录命令转至包含要部署的观察模型的目录。</span><span class="sxs-lookup"><span data-stu-id="ec35d-121">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="ec35d-122">例如， **cd c:\businessprocess\Orders**。</span><span class="sxs-lookup"><span data-stu-id="ec35d-122">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="ec35d-123">部署观察模型使用 bm.exe:</span><span class="sxs-lookup"><span data-stu-id="ec35d-123">Deploy the observation model using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ec35d-124">Tracking\bm.exe 部署所有-Definitionfile:\<*definitionfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="ec35d-124">Tracking\bm.exe deploy-all -Definitionfile:\<*definitionfile.xml*\></span></span>  

    <span data-ttu-id="ec35d-125">请确保您替换\< *definitionfile.xml* \>与你想要部署的观察模型文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ec35d-125">Make sure you replace \<*definitionfile.xml*\> with the name of the observation model file you want to deploy.</span></span> <span data-ttu-id="ec35d-126">有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="ec35d-126">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-127">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="ec35d-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="ec35d-128">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ec35d-128">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="ec35d-129">部署侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="ec35d-129">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="ec35d-130">必须在部署侦听器配置文件之后您的应用程序才能捕获 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="ec35d-130">You must deploy an interceptor configuration file before your application will be able to capture BAM activities.</span></span>  

##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="ec35d-131">若要使用 bm.exe 部署侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="ec35d-131">To deploy an interceptor configuration file by using bm.exe</span></span>  

1. <span data-ttu-id="ec35d-132">单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ec35d-132">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="ec35d-133">类型**cmd**中**打开**字段，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ec35d-133">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="ec35d-134">使用更改目录命令转至包含要部署的侦听器配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="ec35d-134">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="ec35d-135">例如， **cd c:\businessprocess\Orders**。</span><span class="sxs-lookup"><span data-stu-id="ec35d-135">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="ec35d-136">使用 bm.exe 部署侦听器配置文件：</span><span class="sxs-lookup"><span data-stu-id="ec35d-136">Deploy the interceptor configuration file by using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ec35d-137">Tracking\bm.exe 部署侦听器-Filename:\<*icfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="ec35d-137">Tracking\bm.exe deploy-interceptor -Filename:\<*icfile.xml*\></span></span>  

    <span data-ttu-id="ec35d-138">请确保您替换\< *icfile.xml* \>具有你想要部署侦听器配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ec35d-138">Make sure you replace \<*icfile.xml*\> with the name of the interceptor configuration file you want to deploy.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-139">可以使用 **-Force: True**标志来覆盖具有名称相同的侦听器配置文件中的现有事件源。</span><span class="sxs-lookup"><span data-stu-id="ec35d-139">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="ec35d-140">如果这样做，请确保使用备份现有配置**get 侦听器**命令。</span><span class="sxs-lookup"><span data-stu-id="ec35d-140">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="ec35d-141">使用 -Force:True 标志可能会删除所有引用被覆盖的事件源的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="ec35d-141">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-142">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="ec35d-142">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="ec35d-143">类型**退出**，然后按 ENTER 以关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ec35d-143">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

   <span data-ttu-id="ec35d-144">如果已部署了你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序中，直到下一个轮询间隔将不加载新配置。</span><span class="sxs-lookup"><span data-stu-id="ec35d-144">If you have already deployed your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="ec35d-145">但是，如果对应用程序进行配置后重新启动它，则将立即提取该配置。</span><span class="sxs-lookup"><span data-stu-id="ec35d-145">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  

### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="ec35d-146">将用户添加到相应的 BAM 活动角色</span><span class="sxs-lookup"><span data-stu-id="ec35d-146">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="ec35d-147">BAM 侦听器框架使用每个活动的 SQL Server 角色控制对活动和配置信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ec35d-147">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="ec35d-148">必须将运行 WCF 应用程序的用户帐户添加到 BAMPrimaryImport 数据库中相应的 BAM 活动角色。</span><span class="sxs-lookup"><span data-stu-id="ec35d-148">You must add the user account running your WCF application to the appropriate BAM activity role(s) in the BAMPrimaryImport database.</span></span>  

### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="ec35d-149">将 Windows Communication Foundation 应用程序配置为加载 BAM 跟踪服务</span><span class="sxs-lookup"><span data-stu-id="ec35d-149">Configuring the Windows Communication Foundation Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="ec35d-150">配置应用程序以加载 BAM 跟踪服务通过向您的服务器或客户端应用程序的 App.config 文件添加几行。</span><span class="sxs-lookup"><span data-stu-id="ec35d-150">You configure your application to load the BAM tracking service by adding a few lines to the App.config file for your server or client application.</span></span>  

 <span data-ttu-id="ec35d-151">若要启用 BAM 跟踪在你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器或客户端应用程序，你将需要修改 App.config 配置文件，以包括其他终结点行为和行为扩展并添加行为配置属性。</span><span class="sxs-lookup"><span data-stu-id="ec35d-151">To enable BAM tracking in your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server or client application, you will need to modify the App.config configuration file to include an additional endpoint behavior and behavior extension and add a behavior configuration attribute.</span></span> <span data-ttu-id="ec35d-152">服务和客户端模板的格式类似。</span><span class="sxs-lookup"><span data-stu-id="ec35d-152">The formats of the service and client templates are similar.</span></span>  

 <span data-ttu-id="ec35d-153">配置时[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序，请注意以下事项。</span><span class="sxs-lookup"><span data-stu-id="ec35d-153">When configuring the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, note the following.</span></span> <span data-ttu-id="ec35d-154">如果在 App.config 中为同一应用程序定义了多个 BAM 终结点行为（即同一客户端或服务），则 BAM 将采取以下操作。</span><span class="sxs-lookup"><span data-stu-id="ec35d-154">If there is more than one BAM endpoint behaviors defined in the App.config for the same application, that is, the same client or service, BAM will take the following actions.</span></span>  

-   <span data-ttu-id="ec35d-155">如果连接字符串不同，BAM 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="ec35d-155">If the connection strings differ, BAM will raise and exception.</span></span>  

-   <span data-ttu-id="ec35d-156">如果只有轮询间隔不同，BAM 将选择一个行为并继续。</span><span class="sxs-lookup"><span data-stu-id="ec35d-156">If only the polling interval differs, BAM will select one and move on.</span></span> <span data-ttu-id="ec35d-157">在设计时无法确定将选择哪个行为。</span><span class="sxs-lookup"><span data-stu-id="ec35d-157">It is not possible at design time to determine which one will be selected.</span></span>  

> [!NOTE]
>  <span data-ttu-id="ec35d-158">如果连接字符串相同，即意味着它们引用的是同一台计算机，BAM 处理将正常进行。</span><span class="sxs-lookup"><span data-stu-id="ec35d-158">If the connection strings are the same, meaning that they reference the same computer, BAM processing will proceed normally.</span></span>  

 <span data-ttu-id="ec35d-159">以下 App.config 模板示例配置为[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec35d-159">The following sample App.config template is configured for a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server application.</span></span> <span data-ttu-id="ec35d-160">该模板定义了一个使用自定义行为“bamEndpointBehavior”的终结点，该行为已配置为使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec35d-160">It defines an endpoint that uses a custom behavior "bamEndpointBehavior" that is configured to use the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor.</span></span>  

```  
<system.serviceModel>  
  <services>  
    <service name="Service.CreditCardAuthorization">  
      <!-- The endpoint will use the "bamEndpointBehavior" -->   
      <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    </service>  
  </services>  
  <bindings>  
    <wsDualHttpBinding>  
      <binding name="wsDualHttpBinding_ICreditCardAuthorization" transactionFlow="true" />  
    </wsDualHttpBinding>  
  </bindings>  
  <behaviors>  
    <endpointBehaviors>  
      <!-- Define a new behavior named "bamEndpointBehavior" -->  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <extensions>  
    <behaviorExtensions>  
      <!-- Define a new enpoint behavior extension using WCF interceptor -->  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
  </extensions>  
</system.serviceModel>  
```  

 <span data-ttu-id="ec35d-161">在您自己的 App.config 文件中使用该模板之前，需要对该模板稍做更改。</span><span class="sxs-lookup"><span data-stu-id="ec35d-161">You will need to make small changes to this template before using it in your own App.config file.</span></span>  

##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a><span data-ttu-id="ec35d-162">在 WCF 服务 App.config 文件中使用此模板</span><span class="sxs-lookup"><span data-stu-id="ec35d-162">To use this template in your WCF service App.config file</span></span>  

1. <span data-ttu-id="ec35d-163">打开与您的应用程序关联的 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ec35d-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="ec35d-164">可以使用 Notepad.exe 或其他文本编辑器执行此任务。</span><span class="sxs-lookup"><span data-stu-id="ec35d-164">You can use Notepad.exe or another text editor for this task.</span></span>  

2. <span data-ttu-id="ec35d-165">添加[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]BamEndpointBehavior 行为扩展到`extensions`元素中的使用以下 XML:</span><span class="sxs-lookup"><span data-stu-id="ec35d-165">Add the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] BamEndpointBehavior behavior extension to the `extensions` element by using the following XML:</span></span>  

   ```  
   <behaviorExtensions>  
     <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
   </behaviorExtensions>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-166">将行为扩展命名为“BamEndpointBehaviorExtension”并可根据需要更改为适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="ec35d-166">The behavior extension is named "BamEndpointBehaviorExtension" and can be changed as needed to suit your environment.</span></span>  

3. <span data-ttu-id="ec35d-167">添加新的终结点行为，使用新的行为扩展到`behaviors`通过使用下面的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="ec35d-167">Add a new endpoint behavior that uses the new behavior extension to the `behaviors` element by using the following XML.</span></span> <span data-ttu-id="ec35d-168">行为扩展提供了一个连接字符串和轮询间隔（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ec35d-168">The behavior extension provides a connection string and polling interval in seconds.</span></span>  

   ```  
   <endpointBehaviors>  
     <behavior name="bamEndpointBehavior">  
       <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
     </behavior>  
   </endpointBehaviors>  
   ```  

    <span data-ttu-id="ec35d-169">将数据源替换为在您的环境中承载 BamPrimaryImport 数据库的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="ec35d-169">Replace the Data Source with the name of the computer hosting the BamPrimaryImport database in your environment.</span></span> <span data-ttu-id="ec35d-170">更改轮询间隔以适合您的要求;较大的数字表示[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]侦听器将花费更长时间才能检测配置更改。</span><span class="sxs-lookup"><span data-stu-id="ec35d-170">Change the polling interval to suit your requirements; a higher number means that the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor will take longer to detect configuration changes.</span></span> <span data-ttu-id="ec35d-171">如果已更改了行为扩展的名称，请使用该名称替换“BamEndpointBehaviorExtension”。</span><span class="sxs-lookup"><span data-stu-id="ec35d-171">If you changed the name of the behavior extension, use it to replace "BamEndpointBehaviorExtension".</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-172">行为名称为“bamEndpointBehavior”，您可对其进行更改以适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="ec35d-172">The behavior name is "bamEndpointBehavior" and can be changed to suit your environment.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-173">避免使用明文用户名/密码组合，指定时`ConnectionString`。</span><span class="sxs-lookup"><span data-stu-id="ec35d-173">Avoid using a cleartext username/password combination when specifying `ConnectionString`.</span></span> <span data-ttu-id="ec35d-174">这样做可能会危及您的数据库服务器安全。</span><span class="sxs-lookup"><span data-stu-id="ec35d-174">Doing so may compromise your database server.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-175">必须指定`PollingIntervalSec`大于或等于 5 （秒）。</span><span class="sxs-lookup"><span data-stu-id="ec35d-175">You must specify an `PollingIntervalSec` greater than or equal to 5 (seconds).</span></span> <span data-ttu-id="ec35d-176">如果指定较低的值或忽略`PollingIntervalSec`元素中，将引发错误且不会配置拦截。</span><span class="sxs-lookup"><span data-stu-id="ec35d-176">If you specify a lower value or omit the `PollingIntervalSec` element, an error will be raised and interception will not be configured.</span></span>  

4. <span data-ttu-id="ec35d-177">添加`behaviorConfiguration`到终结点，您将跟踪并提供新行为的名称属性：</span><span class="sxs-lookup"><span data-stu-id="ec35d-177">Add the `behaviorConfiguration` attribute to the endpoint you will be tracking and provide the name of the new behavior:</span></span>  

   ```  
   <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="ec35d-178">如果您使用的是其他行为名称，则请提供该名称。</span><span class="sxs-lookup"><span data-stu-id="ec35d-178">If you used a different behavior name, supply it instead.</span></span>  

    <span data-ttu-id="ec35d-179">可以将行为配置应用于多个终结点。</span><span class="sxs-lookup"><span data-stu-id="ec35d-179">You can apply the behavior configuration to multiple endpoints.</span></span>  

5. <span data-ttu-id="ec35d-180">保存已修改的 App.config 文件并重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec35d-180">Save the modified App.config file and restart your application.</span></span>
