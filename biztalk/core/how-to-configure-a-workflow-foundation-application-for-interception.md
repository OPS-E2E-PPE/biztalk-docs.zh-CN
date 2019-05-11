---
title: 如何配置 Workflow Foundation 应用程序用于侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 445a83fc4b1e88c4c0c7cb938cabd0e7df5fca25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341821"
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a>如何配置 Workflow Foundation 应用程序用于侦听
必须安装 BAM 侦听器软件并配置应用程序以使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器服务，然后才能开始收集 BAM 活动数据。 假定您已成功安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]及其依赖项，并已创建至少一个 BizTalk 组。  
  
## <a name="installing-the-bam-eventing-software"></a>安装 Bam-eventing 软件  
 然后才可以配置你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序使用的 BAM 侦听器[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]，必须使用安装 Bam-eventing 软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 有关安装 Bam-eventing 软件和注册性能计数器的详细信息，请参阅[安装 Bam-eventing 软件](../core/installing-the-bam-eventing-software.md)。  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a>配置 Windows Workflow Foundation 应用程序对其进行跟踪  
 之前，必须完成四个任务在[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序可以开始编写 BAM 事件信息：  
  
- 必须使用创建观察模型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 工具，并将使用 BAM 管理器命令行工具 (bm.exe) 部署。  
  
- 必须创建和使用 BAM 管理器命令行的工具 (bm.exe) 部署侦听器配置文件。  
  
- 运行主机应用程序的用户必须是相应的 BAM 活动事件编写器的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取侦听器配置信息和写入到 BAM 活动中。  
  
- 必须修改 App.config 文件或应用程序本身，以加载 BAM 跟踪服务，然后重新启动该应用程序。  
  
  这些任务是仅成功完成后，事件才开始显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 数据库。  
  
### <a name="deploying-an-observation-model"></a>部署观察模型  
 必须先部署观察模型可以部署侦听器配置文件，也可以在应用程序中捕获 BAM 活动。  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>若要使用 bm.exe 部署观察模型  
  
1. 单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2. 类型**cmd**中**打开**字段，，然后单击**确定**。  
  
3. 使用更改目录命令转到包含观察模型的目录来部署。 例如， **cd c:\businessprocess\Orders**。  
  
4. 使用 bm.exe 部署观察模型：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 部署所有-definitionfile:\<*definitionfile.xml*\>  
  
    请确保您替换\< *definitionfile.xml* \>与你想要部署的观察文件的名称。 有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5. 类型**退出**，然后按 ENTER 以关闭命令提示符。  
  
### <a name="deploying-an-interceptor-configuration-file"></a>部署侦听器配置文件  
 你的应用程序可以捕获 BAM 活动之前，必须部署侦听器配置文件。  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>若要使用 bm.exe 部署侦听器配置文件  
  
1. 单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2. 类型**cmd**中**打开**字段，，然后单击**确定**。  
  
3. 使用更改目录命令转到包含侦听器配置文件的目录来部署。 例如， **cd c:\businessprocess\Orders**。  
  
4. 使用 bm.exe 部署侦听器配置文件：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 部署侦听器-filename:\<*icfile.xml*\>  
  
    请确保您替换\< *icfile.xml* \>具有你想要部署侦听器配置文件的名称。  
  
   > [!NOTE]
   >  可以使用 **-Force: True**标志来覆盖具有名称相同的侦听器配置文件中的现有事件源。 如果这样做，请确保使用备份现有配置**get 侦听器**命令。 使用-Force: True 标志可能会删除任何引用被覆盖的事件源的侦听器配置。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5. 类型**退出**，然后按 ENTER 以关闭命令提示符。  
  
   如果已部署了你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序中，直到下一个轮询间隔将不加载新配置。 但是，如果你配置你的应用程序和重新启动它，配置将立即提取。  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>将用户添加到相应的 BAM 活动角色  
 BAM 侦听器框架使用每个活动 SQL Server 角色来控制对活动和配置信息的访问。 必须添加运行的用户帐户在[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]到 BAM 主导入数据库中相应的 BAM 活动角色的应用程序。  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a>配置应用程序以加载 BAM 跟踪服务  
 有三种方案用于加载 BAM 跟踪服务中的你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序：  
  
- 如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序已使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，可以添加 BAM 跟踪服务信息对现有节。  
  
- 如果你[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序不使用 WorkflowRuntime 加载[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]配置部分中，你将需要添加代码以从应用程序配置文件加载自定义部分。 您需要创建的部分并添加 BAM 跟踪服务信息给它。  
  
- 如果您愿意硬编码配置，则可以使用[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]API 以编程方式加载的跟踪服务不使用配置文件，或若要从自定义源加载配置。  
  
  配置时[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]应用程序，请注意以下事项：  
  
- [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持一个 WorkflowRuntime 添加仅一个 BamTrackingService。  
  
- [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]侦听器支持每个应用程序域的多个 BamTrackingService 实例。  
  
  -   N 个 WorkflowRuntime 支持 N 个 BamTrackingService。  
  
- 如果使用不同的连接字符串来进行相同的应用程序域中的不同 BamTrackingService 实例，侦听器将引发异常。  
  
- 侦听器获取 IC 轮询间隔值从启动的第一个 BamTrackingService 实例。  
  
- 应用程序域中的最后一个 BamTrackingService 停止时，侦听器将停止 IC 轮询线程  
  
  有关 WorkflowRuntime 和加载配置信息的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=83314 ](http://go.microsoft.com/fwlink/?LinkId=83314)。  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a>若要为 BAM 跟踪服务配置 App.config 文件  
  
1.  打开与应用程序关联的 App.config 文件。 此任务，可以使用 Notepad.exe 或其他文本编辑器。  
  
2.  通过将以下配置信息插入 App.config 文件添加 BAM 跟踪服务。 它应定位，以便子级`configuration`元素。  
  
    > [!NOTE]
    >  Section 元素应该对应于应用程序代码使用 WorkflowRuntime 类时所使用的名称。  
  
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
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a>若要修改应用程序以加载自定义配置部分  
  
1.  在 Visual Studio 中打开你的 Windows Workflow Foundation 项目。  
  
2.  将使用适当的参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  重新编译并部署修改后的应用程序。  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a>若要修改应用程序以编程方式加载 BAM 跟踪服务  
  
1.  在 Visual Studio 中打开你的 Windows Workflow Foundation 项目。  
  
2.  将使用适当的参数的 BamTrackingService 新实例添加到应用程序的 WorkflowRuntime 实例：  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     您可以添加或删除基于你的特定环境的参数。  
  
3.  重新编译并部署修改后的应用程序。