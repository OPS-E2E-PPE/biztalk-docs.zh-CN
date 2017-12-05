---
title: "如何为侦听配置工作流 Foundation 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70afa4ffae47abf5cdd541846831b4054414eff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a>如何配置 Workflow Foundation 应用程序用于侦听
你必须安装 BAM 拦截器软件和配置应用程序使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器服务，然后才能开始收集 BAM 活动数据。 我们假定您已成功安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 及其依存关系，并至少创建了一个 BizTalk 组。  
  
## <a name="installing-the-bam-eventing-software"></a>安装 BAM 事件软件  
 在可以将您的 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 应用程序配置为对 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 使用 BAM 侦听器之前，您必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序安装 BAM-Eventing 软件。 有关安装 BAM 事件软件和注册性能计数器的详细信息，请参阅[安装 BAM 事件软件](../core/installing-the-bam-eventing-software.md)。  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a>配置 Windows Workflow Foundation 应用程序用于跟踪  
 必须完成四项任务后，[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 应用程序才能开始编写 BAM 事件信息：  
  
-   必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM 工具创建观察模型，然后使用 BAM 管理器命令行工具 (bm.exe) 部署该模型。  
  
-   必须创建并部署通过使用 BAM Manager 命令行的工具 (bm.exe) 拦截器配置文件。  
  
-   运行主机应用程序的用户必须是相应的 BAM 活动事件写入程序的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取配置信息的侦听器和写入BAM 活动中。  
  
-   必须修改 App.config 文件和该应用程序本身才能加载 BAM 跟踪服务并重新启动该应用程序。  
  
 只有成功完成这些任务之后，事件才开始出现在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中。  
  
### <a name="deploying-an-observation-model"></a>部署观察模型  
 您必须先部署观察模型，然后才能在应用程序中部署侦听器配置文件或捕获 BAM 活动。  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>若要使用 bm.exe 部署观察模型  
  
1.  单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2.  类型**cmd**中**打开**字段，然后再单击**确定**。  
  
3.  使用更改目录命令转至包含要部署的观察模型的目录。 例如， **cd c:\businessprocess\Orders**。  
  
4.  使用 bm.exe 部署观察模型：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 部署所有-definitionfile:\<*definitionfile.xml*\>  
  
     请确保你替换\< *definitionfile.xml* \>替换为你想要部署的观察文件的名称。 有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  类型**退出**，然后按 ENTER 可以关闭命令提示符。  
  
### <a name="deploying-an-interceptor-configuration-file"></a>部署拦截器配置文件  
 你的应用程序可以捕获 BAM 活动之前，你必须部署拦截器配置文件。  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>若要使用 bm.exe 部署拦截器配置文件  
  
1.  单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2.  类型**cmd**中**打开**字段，然后再单击**确定**。  
  
3.  使用更改目录命令转至包含要部署的侦听器配置文件的目录。 例如， **cd c:\businessprocess\Orders**。  
  
4.  使用 bm.exe 部署侦听器配置文件：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 部署侦听器 filename:\<*icfile.xml*\>  
  
     请确保你替换\< *icfile.xml* \>替换为你想要部署的侦听器配置文件的名称。  
  
    > [!NOTE]
    >  你可以使用**-Force: True**标志来重写你侦听器的配置文件中的这些相同的名称的现有事件源。 如果这样做，请确保使用备份的现有配置**get 侦听器**命令。 使用 -Force:True 标志可能会删除所有引用被覆盖的事件源的侦听器配置。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  类型**退出**，然后按 ENTER 可以关闭命令提示符。  
  
 如果你已部署你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序中，直到下一步的轮询间隔将不加载新配置。 但是，如果对应用程序进行配置后重新启动它，则将立即提取该配置。  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>将用户添加到相应的 BAM 活动角色  
 BAM 侦听器框架使用每个活动的 SQL Server 角色控制对活动和配置信息的访问权限。 你必须将运行的用户帐户添加你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]到 BAM 主导入数据库中的相应 BAM 活动角色的应用程序。  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a>将该应用程序配置为加载 BAM 跟踪服务  
 有三种方案为加载跟踪中的服务 BAM 你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序：  
  
-   如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序已使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，你可以添加到现有的部分跟踪服务信息的 BAM。  
  
-   如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序不使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，你将需要添加代码以从应用程序配置文件加载自定义的部分。 您必须创建该配置部分，然后将 BAM 跟踪服务信息添加到该配置部分。  
  
-   如果你愿意硬编码配置，则可以使用[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]API 以编程方式加载跟踪服务没有配置文件，或从自定义的源加载配置。  
  
 配置时[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序，请注意以下事项：  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持每一个 WorkflowRuntime 只有一个 BamTrackingService。  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持每个应用程序域的多个 BamTrackingService 实例。  
  
    -   N 个 WorkflowRuntime 支持 N 个 BamTrackingService。  
  
-   如果不同的连接字符串用于同一应用程序域中的不同 BamTrackingService 实例，侦听器将引发异常。  
  
-   侦听器从其启动的首个 BamTrackingService 实例获取 IC 轮询间隔值。  
  
-   应用程序域中的最后一个 BamTrackingService 停止后，侦听器将停止 IC 轮询线程  
  
 WorkflowRuntime 和加载配置信息的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314)。  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a>为 BAM 跟踪服务配置 App.config 文件  
  
1.  打开与您的应用程序关联的 App.config 文件。 可以使用 Notepad.exe 或其他文本编辑器执行此任务。  
  
2.  添加 BAM 跟踪服务，方法为将以下配置信息插入 App.config 文件。 此类信息应放置为 `configuration` 元素的子级。  
  
    > [!NOTE]
    >  此部分元素应与在使用 WorkflowRuntime 类时您的应用程序代码所使用的名称对应。  
  
    ```  
    <!-- The element name must match the one expected by WorkflowRuntime in your WF application -->  
    <WorkflowServiceContainer>  
      <Services>  
        <add type="Microsoft.BizTalk.Bam.Interceptors.Workflow.BamTrackingService, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  
       ConnectionString="Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"   
          PollingIntervalSec="5"/>  
        </Services>  
    </WorkflowServiceContainer>  
    ```  
  
3.  修改**ConnectionString**属性以匹配你的环境。  
  
4.  重新启动应用程序。  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a>修改应用程序以加载自定义配置部分  
  
1.  在 Visual Studio 中打开 Windows Workflow Foundation 项目。  
  
2.  将带有适当参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  重新编译并部署修改后的应用程序。  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a>修改应用程序以通过编程方式加载 BAM 跟踪服务  
  
1.  在 Visual Studio 中打开 Windows Workflow Foundation 项目。  
  
2.  将带有适当参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     根据环境的具体情况，您可以添加或删除参数。  
  
3.  重新编译并部署修改后的应用程序。