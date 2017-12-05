---
title: "如何为侦听配置 Windows Communication Foundation 应用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f8328268b82a377bb6d73f3bd7305122a830c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a>如何为侦听配置 Windows Communication Foundation 应用
必须安装 BAM 侦听器软件并将应用程序配置为使用 BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 侦听器服务后才能开始收集 BAM 活动数据。 我们假定您已成功安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 及其依存关系，并至少创建了一个 BizTalk 组。  
  
## <a name="installing-the-bam-eventing-software"></a>安装 BAM 事件软件  
 在可以将您的 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 应用程序配置为对 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 使用 BAM 侦听器之前，您必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序安装 BAM-Eventing 软件。 有关安装 BAM 事件软件和注册性能计数器的详细信息，请参阅[安装 BAM 事件软件](../core/installing-the-bam-eventing-software.md)。  
  
## <a name="configuring-a-wcf-application-for-tracking"></a>配置对其进行跟踪的 WCF 应用程序  
 必须完成四项任务后，[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 应用程序才能开始编写 BAM 事件信息：  
  
-   必须通过创建观察模型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 工具，然后部署通过使用 BAM Manager 命令行工具 (bm.exe)。  
  
-   必须使用 BAM 管理器命令行工具 (bm.exe) 创建并部署侦听器配置文件。  
  
-   运行主机应用程序的用户必须是相应的 BAM 活动事件写入程序的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取配置信息的侦听器和写入BAM 活动中。  
  
-   必须修改服务器和客户端应用程序的 App.config 文件才能加载 BAM 跟踪服务。 修改 App.config 文件之后，必须重新启动应用程序。  
  
 只有成功完成这些任务之后，事件才开始出现在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中。  
  
### <a name="deploying-an-observation-model"></a>部署观察模型  
 您必须先部署观察模型，然后才能在应用程序中部署侦听器配置文件或捕获 BAM 活动。  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>若要使用 bm.exe 部署观察模型  
  
1.  单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2.  类型**cmd**中**打开**字段，然后再单击**确定**。  
  
3.  使用更改目录命令转至包含要部署的观察模型的目录。 例如， **cd c:\businessprocess\Orders**。  
  
4.  部署使用 bm.exe 观察模型：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 部署所有-Definitionfile:\<*definitionfile.xml*\>  
  
     请确保你替换\< *definitionfile.xml* \>替换为你想要部署的观察模型文件的名称。 有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  类型**退出**然后按 ENTER 可以关闭命令提示符。  
  
### <a name="deploying-an-interceptor-configuration-file"></a>部署拦截器配置文件  
 必须在部署侦听器配置文件之后您的应用程序才能捕获 BAM 活动。  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>若要使用 bm.exe 部署拦截器配置文件  
  
1.  单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  
  
2.  类型**cmd**中**打开**字段，然后再单击**确定**。  
  
3.  使用更改目录命令转至包含要部署的侦听器配置文件的目录。 例如， **cd c:\businessprocess\Orders**。  
  
4.  使用 bm.exe 部署侦听器配置文件：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 部署侦听器 Filename:\<*icfile.xml*\>  
  
     请确保你替换\< *icfile.xml* \>替换为你想要部署的侦听器配置文件的名称。  
  
    > [!NOTE]
    >  你可以使用**-Force: True**标志来重写你侦听器的配置文件中的这些相同的名称的现有事件源。 如果这样做，请确保使用备份的现有配置**get 侦听器**命令。 使用 -Force:True 标志可能会删除所有引用被覆盖的事件源的侦听器配置。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  类型**退出**然后按 ENTER 可以关闭命令提示符。  
  
 如果你已部署你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序中，直到下一步的轮询间隔将不加载新配置。 但是，如果对应用程序进行配置后重新启动它，则将立即提取该配置。  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>将用户添加到相应的 BAM 活动角色  
 BAM 侦听器框架使用每个活动的 SQL Server 角色控制对活动和配置信息的访问权限。 必须将运行 WCF 应用程序的用户帐户添加到 BAMPrimaryImport 数据库中相应的 BAM 活动角色。  
  
### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a>将 Windows Communication Foundation 应用程序配置为加载 BAM 跟踪服务  
 配置你的应用程序以加载 BAM 通过向你的服务器或客户端应用程序的 App.config 文件添加几行跟踪服务。  
  
 若要启用 BAM 中跟踪你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器或客户端应用程序，你将需要修改 App.config 配置文件，以包括其他终结点行为和行为扩展并添加行为配置属性。 服务和客户端模板的格式类似。  
  
 配置时[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序，请注意以下事项。 如果在 App.config 中为同一应用程序定义了多个 BAM 终结点行为（即同一客户端或服务），则 BAM 将采取以下操作。  
  
-   如果连接字符串不同，BAM 将引发异常。  
  
-   如果只有轮询间隔不同，BAM 将选择一个行为并继续。 在设计时无法确定将选择哪个行为。  
  
> [!NOTE]
>  如果连接字符串相同，即意味着它们引用的是同一台计算机，BAM 处理将正常进行。  
  
 下面的示例 App.config 模板配置为[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器应用程序。 该模板定义了一个使用自定义行为“bamEndpointBehavior”的终结点，该行为已配置为使用 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 侦听器。  
  
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
  
 在您自己的 App.config 文件中使用该模板之前，需要对该模板稍做更改。  
  
##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a>在 WCF 服务 App.config 文件中使用此模板  
  
1.  打开与您的应用程序关联的 App.config 文件。 可以使用 Notepad.exe 或其他文本编辑器执行此任务。  
  
2.  添加[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]BamEndpointBehavior 行为扩展到`extensions`通过使用下面的 XML 元素：  
  
    ```  
    <behaviorExtensions>  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
    ```  
  
    > [!NOTE]
    >  将行为扩展命名为“BamEndpointBehaviorExtension”并可根据需要更改为适合您的环境。  
  
3.  添加使用新的行为扩展到新终结点行为`behaviors`通过使用下面的 XML 元素。 行为扩展提供了一个连接字符串和轮询间隔（以秒为单位）。  
  
    ```  
    <endpointBehaviors>  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
    ```  
  
     将数据源替换为在您的环境中承载 BamPrimaryImport 数据库的计算机的名称。 更改轮询间隔，以满足你的要求;较大的数字意味着[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]侦听器需要较长时间检测配置更改。 如果已更改了行为扩展的名称，请使用该名称替换“BamEndpointBehaviorExtension”。  
  
    > [!NOTE]
    >  行为名称为“bamEndpointBehavior”，您可对其进行更改以适合您的环境。  
  
    > [!NOTE]
    >  避免使用明文形式用户名/密码组合，指定时`ConnectionString`。 这样做可能会危及您的数据库服务器安全。  
  
    > [!NOTE]
    >  必须指定`PollingIntervalSec`大于或等于 5 （秒）。 如果指定较低的值或忽略`PollingIntervalSec`元素，将引发错误，并将不会配置截获。  
  
4.  添加`behaviorConfiguration`到终结点，你将跟踪并提供新行为的名称属性：  
  
    ```  
    <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    ```  
  
    > [!NOTE]
    >  如果您使用的是其他行为名称，则请提供该名称。  
  
     可以将行为配置应用于多个终结点。  
  
5.  保存已修改的 App.config 文件并重新启动应用程序。