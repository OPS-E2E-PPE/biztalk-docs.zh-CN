---
title: "文件适配器 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2392f7a74b12ddd0c030922b166bb9a701ae88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-biztalk-server-sample"></a>文件适配器 （BizTalk Server 示例）
在 Microsoft Visual C#.NET 地与 Microsoft 合作编写文件适配器示例[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。 它提供了建立动态或静态适配器的代码。  不过，以下过程仅简要介绍静态适配器。 静态适配器是具有静态架构集合且没有自定义用户接口的适配器。 动态适配器具有自定义用户接口，并可能具有动态架构集合。 静态适配器和动态适配器均使用添加适配器向导向 BizTalk 项目中添加其架构。  
  
> [!NOTE]
>  文件适配器示例与 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 随附的本机 FILE 适配器不同。 因此，在使用本示例时如果要选择传输类型，请选择“静态”，而不是 FILE。  
  
 具有自定义用户接口并可能具有动态架构集合的动态适配器在适配器管理方面需要编写额外的代码。 若要更好地了解使用架构动态组，请参阅[动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例适配器从一个文件夹中复制文件，然后将其作为消息提交给 BizTalk，或者从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 获取消息，然后将其放到文件夹。 它提供了建立动态或静态适配器的代码；不过，以下过程仅简要介绍静态适配器。 静态适配器是具有静态架构集合且没有自定义用户接口的适配器。 动态适配器具有自定义用户接口，并可能具有动态架构集合。 静态适配器和动态适配器均使用添加适配器向导向 BizTalk 项目中添加其架构。  
  
 可以将该示例文件适配器用作创建其他自定义适配器的模板。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*>**\AdaptersDevelopment\File 适配器**  
  
> [!NOTE]
>  默认位置\<*示例路径*> 是*%programfiles%*\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples 时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]运行 32 位版本的计算机上安装Windows。 默认位置\<*示例路径*> 是*%programfiles （x86） %*\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples 时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]运行 64 位计算机上安装Windows 版本。 若要确定与关联的值*%programfiles%*或*%programfiles （x86） %*环境变量类型**echo %programfiles%**或**echo %Programfiles （x86） %**在命令提示符并按 enter 键。 如果在 64 位操作系统上运行此示例，你将需要更改任何从的.reg 文件中的所有引用**%programfiles%**到**%programfiles （x86） %**之前运行的.reg 文件。  
  
 下表显示了本示例中的文件并说明了其用途。  
  
|\File Adapter 文件|Description|  
|--------------------------|-----------------|  
|\BizTalk Project 文件|包含适配器管理项目，用于测试示例适配器。|  
|\Design Time 文件|包含设计时项目和管理项目 (AdapterManagement.csproj)。|  
|\Runtime 文件|包含运行时文件复制接收和传输项目 (DotNetFile.csproj)。|  
|DynamicAdapterManagement.reg|注册示例动态适配器。|  
|Instance.xml|通过文件适配器传递的示例文件。|  
|StaticAdapterManagement.reg|注册示例静态适配器。|  
  
|\BizTalk Project\Adapter Harness 文件|Description|  
|----------------------------------------------|-----------------|  
|AdapterHarness.odx、AdapterHarness.sln、AdapterHarnessProject.btproj|为 BizTalk 项目提供项目文件、解决方案文件和相关文件。|  
|mySchema.xsd|提供管理业务流程预期从适配器的接收部分获得的 Instance.xml 的架构以及由该业务流程传递给适配器的发送部分的 Instance.xml 的架构。|  
  
|\Design Time\Adapter Management 文件|Description|  
|---------------------------------------------|-----------------|  
|AdapterManagement.cs、AdapterManagement.csproj、AdapterManagement.sln|适配器设计时所需的项目、解决方案和相关文件。|  
|AssemblyInfo.cs|包含本示例的程序集信息。|  
|CategorySchema2.xml|本示例适配器不使用此文件。|  
|CategorySchema.xml|包含静态适配器的服务组织树。|  
|DotNetFileResource.resx|包含资源。|  
|ReceiveHandler.xsd、ReceiveLocation.xsd|包含接收端处理程序和终结点自定义属性架构|  
|service1.wsdl|包含适配器的操作定义。|  
|TransmitHandler.xsd、TransmitLocation.xsd|包含传输端处理程序和终结点自定义属性架构|  
  
|\Runtime 文件|Description|  
|---------------------|-----------------|  
|DotNetFile.csproj、DotNetFile.sln、<br /><br /> AssemblyInfo.cs、<br /><br /> DotNetFileExceptions.cs、DotNetFileProperties.cs、DotNetFileReceiver.cs、DotNetFileReceiverEndPoint.cs、DotNetFileTransmitter.cs<br /><br /> DotNetFileTransmitterEndpoint.cs<br /><br /> DotNetFileAsyncTransmitterBatch.cs、<br /><br /> BatchMessage.cs|运行时文件复制发送和接收适配器的文件。 对于自定义组件，可以修改这些文件并以新名称保存它们。<br /><br /> DotNetFile.csproj 和 DotNetFile.sln 是项目和解决方案文件。<br /><br /> AssemblyInfo.cs 包含本示例的程序集信息。<br /><br /> DotNetFileReceiver.cs 读取来自接收位置的文件并将其提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> DotNetFileExceptions.cs 实现了对消息处理过程中发生的异常进行处理的代码<br /><br /> DotNetFileProperties.cs 包含接收和发送操作的通用属性<br /><br /> BatchMessage.cs 实现批处理消息传送。<br /><br /> DotNetFileReceiverEndPoint.cs 是与接收位置/URI 相对应的类。  它负责轮询给定文件夹以查看是否有新消息<br /><br /> DotNetFileTransmitter.cs 是用于 DotNetFile 发送适配器的单独类。 通过此类将所有消息发往此适配器类型的各个发送端口<br /><br /> DotNetFileTransmitterEndpoint.cs 处理消息的传输工作。|  
  
|\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 文件|Description|  
|--------------------------------------------------------------------|-----------------|  
|Adapter.cs、AdapterException.cs、AsyncTransmitter.cs、batch.cs、ConfigProperties.cs、ControlledTermination.cs、IManageEndpoints.cs、Receiver.cs、ReceiverEndpoint.cs|提供构成基本适配器的类。 你可以使用它们来创建你自己的适配器。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 示例文件适配器用作要在其中创建自定义的其他适配器的模板。  
  
## <a name="building-this-sample"></a>生成本示例  
  
> [!IMPORTANT]
>  如果是在 64 位计算机上安装 BizTalk 或安装位置已修改，则需要相应修改 OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath。  
  
 使用以下过程可以生成并初始化文件适配器示例。  
  
#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a>为 DotNetFileAdapter 项目和基本适配器项目创建强名称密钥  
  
1.  启动**Visual Studio 命令提示**。  
  
    > [!NOTE]
    >  以管理员身份运行命令提示符。  
  
2.  将当前目录更改为\<*示例路径*>**\AdaptersDevelopment\BaseAdapter\v1.0.2**目录。  
  
3.  在命令提示符处，键入**sn-k BaseAdapter.snk**然后按 ENTER。 如果以前运行过其他示例，则此 .snk 文件可能已经存在。 如果确实如此，则可以跳过此步骤直接转到步骤 4。  
  
4.  将当前目录更改为\<*示例路径*>\\**AdaptersDevelopment\File Adapter\Runtime**目录。  
  
5.  在命令提示符处，键入**sn-k DotNetFileAdapter.snk**然后按 ENTER。  
  
6.  在命令提示符处，键入**退出**然后按 ENTER 以关闭命令提示符窗口。  
  
#### <a name="to-build-the-receiver-run-time-project"></a>生成接收器运行时项目  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
2.  导航到\<*示例路径*>**"\AdaptersDevelopment\File Adapter\Runtime"**目录中，，然后双击**DotNetFile.sln**.  
  
3.  若要重新生成适配器接收方运行时项目，在解决方案资源管理器，右键单击**DotNetFile**，然后单击**重新生成**。  
  
4.  从**文件**菜单上，单击**退出**关闭 Visual Studio。  
  
#### <a name="to-build-the-adapter-design-time-project"></a>生成适配器设计时项目  
  
1.  在 Windows 资源管理器，导航到\<*示例路径*>**"\AdaptersDevelopment\File Adapter\Design Time\Adapter 管理"**目录中，，然后双击**AdapterManagement.sln**。  
  
2.  在解决方案资源管理器，右键单击**AdapterManagement**，然后单击**重新生成**。  
  
3.  从**文件**菜单上，单击**退出**关闭 Visual Studio。  
  
#### <a name="to-register-the-sample-static-adapter"></a>注册示例静态适配器  
  
1.  在 Windows 资源管理器，导航到\<*示例路径*>**"\AdaptersDevelopment\File 适配器"**目录。  
  
2.  若要将示例适配器添加到注册表中，双击**StaticAdapterManagement.reg**。  
  
    > [!NOTE]
    >  StaticAdapterManagement.reg 包括硬编码路径 C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] \\。 如果未将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装到 %ProgramFiles%\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\ 目录中，或是从 BizTalk Server 2009 或 BizTalk Server 2006 R2 升级 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装，亦或将 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装在运行 64 位版本 Windows 的计算机上，则必须使用相应的路径修改 StaticAdapterManagement.reg 文件。 默认情况下，在运行 64 位版本 Windows 的计算机上，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装在 %ProgramFiles(x86)%\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\ 目录中。 更新与“InboundAssemblyPath”、“OutboundAssemblyPath”和“AdapterMgmtAssemblyPath”值相关联的路径，使之指向指定文件的正确位置。  
  
    > [!IMPORTANT]
    >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为在 HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ **StaticAdapterManagement.reg**注册表文件。  
  
3.  在**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表中，然后单击**确定**。  
  
4.  若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  
  
#### <a name="to-install-the-sample-static-adapter"></a>若要安装示例静态适配器  
  
1.  单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击以展开**BizTalk 组**，并单击以展开**平台设置**.  
  
3.  右键单击**适配器**，单击**新建**，然后单击**适配器**。  
  
4.  在**添加适配器**对话框框中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**静态**。|  
    |**适配器**|选择**静态 DotNetFile**从下拉列表。|  
    |**注释**|类型**示例适配器**。|  
  
5.  单击 **“确定”**。  
  
     该静态适配器此时即会显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。  
  
#### <a name="to-stop-and-restart-the-host-instance"></a>若要停止并重新启动主机实例  
  
1.  单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击以展开**BizTalk 组**，单击以展开**平台设置**单击**主机实例**。 在右窗格中选择“BizTalkServerApplication”。  
  
3.  在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），并依次**重新启动**。  
  
### <a name="running-this-sample"></a>运行本示例  
  
##### <a name="to-run-the-file-adapter-sample"></a>运行文件适配器示例  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
2.  上创建以下文件夹[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装驱动器：  
  
    -   *\<驱动器 >*:**\Temp**  
  
    -   *\<驱动器 >*:**\Temp\Send**  
  
    -   *\<驱动器 >*:**\Temp\Receive**  
  
3.  若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  
  
4.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
5.  右键单击**BizTalk Server 管理**节点，然后选择**连接到现有组**。  
  
6.  在**连接到现有的 BizTalk Server 配置数据库**对话框框中，执行以下操作。  
  
    > [!NOTE]
    >  BizTalk 管理数据库也称为 BizTalk 配置数据库。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**SQL Server**|类型**。** （句点）。|  
    |**数据库**|选择由配置向导创建的 BizTalk 管理数据库的名称。 使用配置向导的默认数据库名称是**BizTalkMgmtDb**。|  
  
7.  单击 **“确定”**。  
  
8.  展开 **BizTalk 组 [*服务器名称*] * * 中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**应用程序**节点，展开**BizTalk 应用程序 1**节点。  
  
9. 右键单击**发送端口**节点，，然后单击**新建**，选择**静态单向发送端口**，然后单击**确定**。  
  
10. 在**发送端口属性**对话框中，选择**常规**，并执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**AdapterSend**。|  
    |**传输类型**|选择**静态**从该下拉列表并单击**配置**。<br /><br /> -在**目录**框中，键入 ***\<驱动器 >*: \Temp\Send**。<br />-在**文件模式**框中，选择**创建新**。<br />-在**文件名**框中，键入**%MessageID%.xml**。<br />-单击**确定**。<br />- **URI**字段应显示 ***\<驱动器 >*: \Temp\Send\\%MessageID%.xml**。|  
    |**发送管道**|选择**PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**，然后单击**确定**。|  
  
11. 下**BizTalk 应用程序 1**节点单击**接收端口**，然后选择**新 / 单向接收端口**。  
  
12. 在**创建新接收端口**对话框中，在**指定的接收端口类型**框中，选择**单向接收端口**从下拉列表，，然后单击**确定**。  
  
13. 在**接收端口属性**对话框中，在**名称**框中，键入**AdapterReceive**，然后单击**确定**。  
  
14. 下**BizTalk 应用程序 1**右键单击节点**接收位置**，然后选择**新 / 单向接收位置**。  
  
15. 在**选择接收端口**对话框中，选择**AdapterReceive**然后单击**确定**。  
  
16. 在**接收位置属性**对话框框中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**AdapterReceiveLocation**|  
    |**传输类型**|选择**静态**从下拉列表和命中**配置**以访问这些剩余属性。|  
    |**URI**|-单击省略号按钮 (**...**).<br />-在**数量的文件在批处理**框中，键入**20**。<br />-在**目录**框中，键入 ***\<驱动器 >*: \Temp\Receive**。<br />-确保**文件掩码**属性设置为 **\*.xml**。<br />-在**轮询间隔**框中，键入**5**，然后单击**确定**。<br />-确保**URI**标签包含 ***\<驱动器 >*: \Temp\Receive\\\*.xml**。|  
    |**接收处理程序**|选择**BizTalkServerApplication**从下拉列表。|  
    |**接收管道**|选择**XMLReceive**从下拉列表。|  
  
17. 单击 **“确定”**。  
  
     继续执行*生成、 部署和绑定的示例适配器*。  
  
### <a name="building-deploying-and-binding-the-sample-adapter"></a>示例适配器的生成、部署和绑定  
 在适配器投入使用前，必须生成项目、绑定业务流程与端口以及登记适配器。  
  
##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a>为静态适配器创建强名称密钥  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  在命令提示符下，将当前目录更改为\<*示例路径*>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter 套**目录。  
  
3.  在命令提示符处，键入**sn-k AdapterHarness.snk**，然后 pressENTER。  
  
4.  单击 **“确定”**。  
  
##### <a name="to-build-the-adapter-harness-project"></a>生成适配器管理项目  
  
-   在解决方案资源管理器，右键单击**AdapterHarnessProject**，然后单击**重新生成**。  
  
##### <a name="to-deploy-the-adapter-harness-project"></a>部署适配器管理项目  
  
1.  在解决方案资源管理器已重新生成了项目，右键单击**AdapterHarnessProject**，然后单击**部署**。  
  
2.  在 BizTalk Server 管理控制台中，选择你已部署，然后单击该项目**刷新**。  
  
##### <a name="to-bind-the-orchestration-with-the-ports"></a>绑定业务流程与端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在相应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，展开**业务流程**节点。  
  
2.  右键单击**AdapterHarness.AdapterHarnessType**，然后单击**绑定**。  
  
3.  在**端口绑定属性 AdapterHarness.AdapterHarnessType-绑定配置**对话框框中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**AdapterFileReceivePort**|选择**AdapterReceive**从下拉列表。|  
    |**AdapterFileSendPort**|选择**AdapterSend**从下拉列表。|  
  
4.  在左窗格中，单击**主机**。  
  
5.  在**主机**框中，选择**BizTalkServerApplication**从下拉列表，然后单击**确定**。  
  
 继续执行*管理示例适配器*。  
  
### <a name="administering-the-sample-adapter"></a>管理示例适配器  
 可以在 BizTalk 管理控制台中完成示例适配器的管理任务。  
  
##### <a name="to-administer-the-file-adapter-sample"></a>管理文件适配器示例  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在左窗格中，单击以展开**应用程序**，单击以展开**BizTalk 应用程序 1**，然后单击**接收位置**。  
  
3.  确保**AdapterReceive**状态是**已启用**。  
  
     如果状态不是**已启用**，右键单击**AdapterReceive**在右窗格中，然后单击**启用**。  
  
4.  在左窗格中，单击**业务流程**并确保**AdapterHarness.AdapterHarnessType**是**登记的**。 右键单击**AdapterHarness.AdapterHarnessType**，然后单击**Enlist** (如果已登记 AdapterHarness.AdapterHarnessType， **Enlist**菜单选项不可用）。  
  
5.  右键单击**AdapterHarness.AdapterHarnessType**和选择**启动**。 此业务流程的状态应更改为**运行**。  
  
 继续执行*测试示例适配器*。  
  
### <a name="testing-the-sample-adapter"></a>测试示例适配器  
 在部署示例适配器后，必须停止并重新启动主机实例。 在投入生产前测试示例适配器很重要。  
  
##### <a name="to-stop-and-restart-the-host-instance"></a>若要停止并重新启动主机实例  
  
1.  在**BizTalk Server 管理**控制台，单击以展开**BizTalk Server 管理**，单击以展开**BizTalk 组**，单击以展开**平台设置**单击**主机实例**。 在右窗格中选择“BizTalkServerApplication”。  
  
2.  右键单击主机实例 （通常情况下，计算机名称），并依次**停止**。  
  
     主机实例的状态更改为**已停止**。  
  
3.  右键单击主机实例，然后单击**启动**。  
  
     主机实例的状态更改为**运行**。  
  
##### <a name="to-test-the-sample-static-adapter-runtime"></a>测试示例静态适配器运行时  
  
1.  在 Windows 资源管理器，导航到\<*示例路径*>**\AdaptersDevelopment\File 适配器**目录，并将复制到剪贴板的 InstanceXML.xml 文件。  
  
2.  导航到*\<驱动器 >*:**\Temp\Receive**并将 Instance.xml 文件粘贴到该文件夹。  
  
     如果传输和接收正在适配器，该文件应移动从*\<驱动器 >*:**\Temp\Receive**文件夹*\<驱动器 >*:**\Temp\Send**文件夹。  
  
##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a>测试示例静态适配器的示例添加适配器向导功能  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击**AdapterHarnessProject**，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项的 AdapterHarnessProject**对话框中，单击**添加适配器元数据**，然后单击**打开**。  
  
     即会显示已注册适配器的列表。  
  
3.  选择**静态 DotNetFile**，然后单击**下一步**。  
  
     即会显示由该适配器公开的服务组织。  
  
4.  展开**服务组织**，**卫生保健**，然后单击**管理**。  
  
     请注意，**资格**以不同方式显示来自其他节点。 **资格**是你可以选择一个服务节点。 其他节点为组织节点，不对任何特定服务进行说明。  
  
5.  选择**资格**节点，，然后单击**完成**。  
  
     BizTalk 即会将一个 .odx 文件和一个 .xsd 文件导入到项目中。  
  
     现在你即可在 BizTalk 项目的计划中使用从适配器导入的架构、PortType、操作和 MessageType。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>类或在此示例中使用的方法  
 接口：IBaseMessage、IPropertyBag、IBTTransportProxy  
  
 类（来自基本适配器）：AsyncTransmitterEndpoint、AsyncTransmitter、BatchMessage、ControlledTermination、ReceiverEndpoint、DotNetFileCommonProperties、BatchOperationType  
  
### <a name="comments"></a>注释  
 完成后的示例适配器，你可以修改的示例适配器创建自定义的静态或动态适配器有关详细信息，请参阅[适配器设计时配置](../core/adapter-design-time-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [适配器示例-使用情况](../core/adapter-samples-usage.md)   
 [注册的适配器](../core/registering-an-adapter.md)