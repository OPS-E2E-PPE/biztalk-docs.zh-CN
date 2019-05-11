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
ms.openlocfilehash: 9b62a2eef5135ad75626b08675d73e6bae310f5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391479"
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a>如何配置 Windows Communication Foundation 应用程序用于侦听
必须安装 BAM 侦听器软件并配置应用程序以使用 BAM[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]侦听器服务，然后才能开始收集 BAM 活动数据。 假定您已成功安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]及其依赖项，并已创建至少一个 BizTalk 组。  

## <a name="installing-the-bam-eventing-software"></a>安装 Bam-eventing 软件  
 然后才可以配置你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序使用的 BAM 侦听器[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]，必须使用安装 Bam-eventing 软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 有关安装 Bam-eventing 软件和注册性能计数器的详细信息，请参阅[安装 Bam-eventing 软件](../core/installing-the-bam-eventing-software.md)。  

## <a name="configuring-a-wcf-application-for-tracking"></a>配置 WCF 应用程序对其进行跟踪  
 之前，必须完成四个任务在[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序可以开始编写 BAM 事件信息：  

- 必须使用创建观察模型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 工具，然后使用 BAM 管理器命令行工具 (bm.exe) 部署。  

- 必须创建和使用 BAM 管理器命令行工具 (bm.exe) 部署侦听器配置文件。  

- 运行主机应用程序的用户必须是相应的 BAM 活动事件编写器的成员 (bam_\<活动\>_EventWriter) SQL Server 角色，以使应用程序读取侦听器配置信息和写入到 BAM 活动中。  

- 必须修改服务器和客户端应用程序的 App.config 文件，以加载 BAM 跟踪服务。 修改 App.config 文件后，必须重新启动该应用程序。  

  这些任务是仅成功完成后，事件才开始显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BAM 数据库。  

### <a name="deploying-an-observation-model"></a>部署观察模型  
 必须先部署观察模型可以部署侦听器配置文件，也可以在应用程序中捕获 BAM 活动。  

##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>若要使用 bm.exe 部署观察模型  

1. 单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  

2. 类型**cmd**中**打开**字段，，然后单击**确定**。  

3. 使用更改目录命令转到包含观察模型的目录来部署。 例如， **cd c:\businessprocess\Orders**。  

4. 部署观察模型使用 bm.exe:  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 部署所有-Definitionfile:\<*definitionfile.xml*\>  

    请确保您替换\< *definitionfile.xml* \>与你想要部署的观察模型文件的名称。 有关更多选项，请参阅[侦听器管理命令](../core/interceptor-management-commands.md)。  

   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  

5. 类型**退出**，然后按 ENTER 以关闭命令提示符。  

### <a name="deploying-an-interceptor-configuration-file"></a>部署侦听器配置文件  
 你的应用程序将能够捕获 BAM 活动之前，必须部署侦听器配置文件。  

##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>若要使用 bm.exe 部署侦听器配置文件  

1. 单击**启动**，然后单击**运行**若要打开 Windows 命令提示符。  

2. 类型**cmd**中**打开**字段，，然后单击**确定**。  

3. 使用更改目录命令转到包含侦听器配置文件的目录来部署。 例如， **cd c:\businessprocess\Orders**。  

4. 使用 bm.exe 部署侦听器配置文件：  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 部署侦听器-Filename:\<*icfile.xml*\>  

    请确保您替换\< *icfile.xml* \>具有你想要部署侦听器配置文件的名称。  

   > [!NOTE]
   >  可以使用 **-Force: True**标志来覆盖具有名称相同的侦听器配置文件中的现有事件源。 如果这样做，请确保使用备份现有配置**get 侦听器**命令。 使用-Force: True 标志可能会删除任何引用被覆盖的事件源的侦听器配置。  

   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  

5. 类型**退出**，然后按 ENTER 以关闭命令提示符。  

   如果已部署了你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序中，直到下一个轮询间隔将不加载新配置。 但是，如果你配置你的应用程序和重新启动它，配置将立即提取。  

### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>将用户添加到相应的 BAM 活动角色  
 BAM 侦听器框架使用每个活动 SQL Server 角色来控制对活动和配置信息的访问。 必须添加在 BAMPrimaryImport 数据库中运行 WCF 应用程序与相应的 BAM 活动角色的用户帐户。  

### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a>配置 Windows Communication Foundation 应用程序为加载 BAM 跟踪服务  
 配置应用程序以加载 BAM 跟踪服务通过向您的服务器或客户端应用程序的 App.config 文件添加几行。  

 若要启用 BAM 跟踪在你[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器或客户端应用程序，你将需要修改 App.config 配置文件，以包括其他终结点行为和行为扩展并添加行为配置属性。 服务和客户端模板的格式很相似。  

 配置时[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]应用程序，请注意以下事项。 如果没有，它是在同一应用程序的 App.config 中定义的多个 BAM 终结点行为、 相同的客户端或服务，则 BAM 将执行以下操作。  

-   如果连接字符串不同，BAM 将引发和异常。  

-   如果只有轮询间隔不同，BAM 将选择其中一个，然后继续。 不能在设计时，若要确定将选择哪一个。  

> [!NOTE]
>  如果连接字符串相同，这意味着它们引用在同一台计算机，BAM 处理将正常进行。  

 以下 App.config 模板示例配置为[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务器应用程序。 它定义终结点使用自定义行为"bamEndpointBehavior"的配置为使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]侦听器。  

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

 你将需要对此模板在 App.config 文件中使用它之前进行微小的更改。  

##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a>若要在 WCF 服务 App.config 文件中使用此模板  

1. 打开与应用程序关联的 App.config 文件。 此任务，可以使用 Notepad.exe 或其他文本编辑器。  

2. 添加[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]BamEndpointBehavior 行为扩展到`extensions`元素中的使用以下 XML:  

   ```  
   <behaviorExtensions>  
     <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
   </behaviorExtensions>  
   ```  

   > [!NOTE]
   >  行为扩展名为"BamEndpointBehaviorExtension"，并可根据需要以满足您的环境更改。  

3. 添加新的终结点行为，使用新的行为扩展到`behaviors`通过使用下面的 XML 元素。 行为扩展提供的连接字符串和轮询间隔以秒为单位。  

   ```  
   <endpointBehaviors>  
     <behavior name="bamEndpointBehavior">  
       <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
     </behavior>  
   </endpointBehaviors>  
   ```  

    将承载您的环境中在 BamPrimaryImport 数据库的计算机的名称替换为数据源。 更改轮询间隔以适合您的要求;较大的数字表示[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]侦听器将花费更长时间才能检测配置更改。 如果更改了行为扩展的名称，则可使用它来替换"BamEndpointBehaviorExtension"。  

   > [!NOTE]
   >  行为名称为"bamEndpointBehavior"，并且可以更改以适合您的环境。  

   > [!NOTE]
   >  避免使用明文用户名/密码组合，指定时`ConnectionString`。 执行此操作可能会危及你的数据库服务器。  

   > [!NOTE]
   >  必须指定`PollingIntervalSec`大于或等于 5 （秒）。 如果指定较低的值或忽略`PollingIntervalSec`元素中，将引发错误且不会配置拦截。  

4. 添加`behaviorConfiguration`到终结点，您将跟踪并提供新行为的名称属性：  

   ```  
   <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
   ```  

   > [!NOTE]
   >  如果使用不同的行为名称，提供该名称。  

    您可以将行为配置应用到多个终结点。  

5. 保存修改的 App.config 文件并重新启动你的应用程序。
