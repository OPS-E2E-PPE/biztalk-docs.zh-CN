---
title: 文件适配器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2260c29394227c9bcd905f0b87b062a35ee27e1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345577"
---
# <a name="file-adapter-biztalk-server-sample"></a>文件适配器 （BizTalk Server 示例）
文件适配器示例用 Microsoft Visual C#.NET 能够使用 Microsoft BizTalk Server。 它提供了代码生成动态或静态适配器。  但是，以下过程仅简要介绍静态适配器。 静态适配器是使用一组静态的架构和任何自定义用户界面的适配器。 动态适配器具有自定义用户界面和可能动态架构集合。 静态和动态适配器使用添加适配器向导以将其架构添加到 BizTalk 项目。  

> [!NOTE]
>  文件适配器示例中不附带有 BizTalk Server 的本机 FILE 适配器相同。 因此当使用此示例选择的传输类型选择"静态"而不是文件。  

 自定义用户界面并可能具有动态架构集合的动态适配器需要适配器管理方面中的其他代码。 若要更好地了解使用动态架构集合，请参阅[动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 示例适配器从文件文件夹中复制文件、 将提交给 BizTalk 作为消息或接收的消息从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和将放入一个文件夹。 它提供了代码生成动态或静态适配器;但是，以下过程仅简要介绍静态适配器。 静态适配器是使用一组静态的架构和任何自定义用户界面的适配器。 动态适配器具有自定义用户界面和可能动态架构集合。 静态和动态适配器使用添加适配器向导以将其架构添加到 BizTalk 项目。  

 示例文件适配器可用作模板在其上创建其他自定义适配器。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>**\AdaptersDevelopment\File Adapter**  

> [!NOTE]
>  默认位置\<*示例路径*\>是 *%programfiles%* \Microsoft BizTalk Server\SDK\Samples 时运行 32 位的计算机上安装 BizTalk ServerWindows 版本。 默认位置\<*示例路径*\>是 *%programfiles （x86） %* \Microsoft BizTalk Server\SDK\Samples 时运行 64 的计算机上安装 BizTalk Server位版本的 Windows。 若要确定与关联的值 *%programfiles%* 或 *%programfiles （x86） %* 环境变量类型**echo %programfiles%** 或**echo %Programfiles （x86） %** 在命令提示符，然后按 ENTER 键。 如果在 64 位操作系统上运行此示例，您需要更改中的任何.reg 文件中的所有引用 **%programfiles%** 到 **%programfiles （x86） %** 之前正在运行的.reg 文件。  

 下表显示在此示例中的文件，并说明了其用途。  

|\File adapter 文件|Description|  
|--------------------------|-----------------|  
|\BizTalk project 文件|包含适配器管理项目，用于测试示例适配器。|  
|\Design time 文件|包含设计时和管理项目 (AdapterManagement.csproj)。|  
|\Runtime 文件|包含运行时文件复制接收和传输项目 (DotNetFile.csproj)。|  
|DynamicAdapterManagement.reg|注册示例动态适配器。|  
|Instance.xml|若要通过文件适配器的示例文件。|  
|StaticAdapterManagement.reg|注册示例静态适配器。|  

|\BizTalk Project\Adapter harness 文件|Description|  
|----------------------------------------------|-----------------|  
|AdapterHarness.odx、 AdapterHarness.sln、 AdapterHarnessProject.btproj|提供了项目、 解决方案和相关的 BizTalk 项目文件。|  
|mySchema.xsd|提供所需的业务流程从适配器的接收部分的 Instance.xml 的架构，以及由业务流程传递给适配器的发送部分的 Instance.xml 的架构。|  

|\Design Time\Adapter 管理文件|Description|  
|---------------------------------------------|-----------------|  
|AdapterManagement.cs, AdapterManagement.csproj, AdapterManagement.sln|项目、 解决方案和适配器设计时的相关的文件。|  
|AssemblyInfo.cs|包含此示例的程序集信息。|  
|CategorySchema2.xml|不使用示例适配器。|  
|CategorySchema.xml|包含静态适配器的服务组织树。|  
|DotNetFileResource.resx|包含的资源。|  
|ReceiveHandler.xsd, ReceiveLocation.xsd|包含接收端处理程序和终结点自定义属性架构|  
|service1.wsdl|包含适配器的操作定义。|  
|TransmitHandler.xsd, TransmitLocation.xsd|包含传输端处理程序和终结点自定义属性架构|  

|                                                                                                                                                             \Runtime 文件                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DotNetFile.csproj, DotNetFile.sln,<br /><br /> AssemblyInfo.cs、<br /><br /> DotNetFileExceptions.cs, DotNetFileProperties.cs, DotNetFileReceiver.cs, DotNetFileReceiverEndPoint.cs, DotNetFileTransmitter.cs,<br /><br /> DotNetFileTransmitterEndpoint.cs,<br /><br /> DotNetFileAsyncTransmitterBatch.cs,<br /><br /> BatchMessage.cs | 运行时文件复制的文件发送和接收适配器。 可以修改和保存自定义组件的新名称下的这些文件。<br /><br /> DotNetFile.csproj 和 DotNetFile.sln 是项目和解决方案文件。<br /><br /> AssemblyInfo.cs 包含本示例的程序集信息。<br /><br /> DotNetFileReceiver.cs 从接收位置读取文件并将其提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> DotNetFileExceptions.cs,implements 代码以在消息处理过程中处理异常<br /><br /> DotNetFileProperties.cs 包含接收和发送操作的通用属性<br /><br /> BatchMessage.cs 实现批处理消息传送。<br /><br /> 类 DotNetFileReceiverEndPoint.cs，相应对接收位置/URI。  它负责轮询给定的文件夹以查看新消息<br /><br /> DotNetFileTransmitter.cs 是用于 DotNetFile 发送适配器的单一实例类。 所有消息，转到此适配器类型的各个发送端口都都将通过此类<br /><br /> DotNetFileTransmitterEndpoint.cs,handles 传输消息。 |

|\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 files|Description|  
|--------------------------------------------------------------------|-----------------|  
|Adapter.cs、 AdapterException.cs、 AsyncTransmitter.cs、 batch.cs、 ConfigProperties.cs、 ControlledTermination.cs、 IManageEndpoints.cs、 Receiver.cs、 ReceiverEndpoint.cs|提供构成基本适配器类。 可以使用这些来创建你自己的适配器。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 使用作为模板在其上创建其他自定义适配器的示例文件适配器。  

## <a name="building-this-sample"></a>生成本示例  

> [!IMPORTANT]
>  如果 BizTalk 安装的是 64 位或修改安装位置，OutboundAssemblyPath、 InboundAssemblyPath、 AdapterMgmtAssemblyPath 需要相应地更改。  

 使用以下过程生成并初始化文件适配器示例。  

#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a>若要创建强名称密钥为 DotNetFileAdapter 项目和基本适配器项目  

1.  启动**Visual Studio 命令提示符**。  

    > [!NOTE]
    >  以管理员身份运行命令提示符。  

2.  将当前目录更改为\<*示例路径*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2**目录。  

3.  在命令提示符处，键入**sn – k BaseAdapter.snk** ，然后按 ENTER。 如果以前运行过其他示例，可能已经存在此.snk 文件。 如果是这样，您可以直接转到步骤 4 和跳过此步骤。  

4.  将当前目录更改为\<*示例路径*\>\\**AdaptersDevelopment\File Adapter\Runtime**目录。  

5.  在命令提示符处，键入**sn – k DotNetFileAdapter.snk** ，然后按 ENTER。  

6.  在命令提示符处，键入**退出**，然后按 ENTER 以关闭命令提示符窗口。  

#### <a name="to-build-the-receiver-run-time-project"></a>若要生成接收器运行时项目  

1.  单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  

2.  导航到\<*示例路径*\>**"\AdaptersDevelopment\File Adapter\Runtime"** 目录中，然后再双击**DotNetFile.sln**.  

3.  若要重新生成适配器接收器运行时项目，在解决方案资源管理器，右键单击**DotNetFile**，然后单击**重新生成**。  

4.  从**文件**菜单上，单击**退出**以关闭 Visual Studio。  

#### <a name="to-build-the-adapter-design-time-project"></a>若要生成适配器设计时项目  

1.  在 Windows 资源管理器，导航到\<*示例路径*\>**"\AdaptersDevelopment\File Adapter\Design Time\Adapter Management"** 目录，然后再双击**AdapterManagement.sln**。  

2.  在解决方案资源管理器中右键单击**AdapterManagement**，然后单击**重新生成**。  

3.  从**文件**菜单上，单击**退出**以关闭 Visual Studio。  

#### <a name="to-register-the-sample-static-adapter"></a>若要注册示例静态适配器  

1. 在 Windows 资源管理器，导航到\<*示例路径*\>**"\AdaptersDevelopment\File 适配器"** 目录。  

2. 若要将示例适配器添加到注册表中，双击**StaticAdapterManagement.reg**。  

   > [!NOTE]
   >  StaticAdapterManagement.reg 包含硬编码路径为 C:\Program Files\Microsoft BizTalk Server\\。 如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 %ProgramFiles%\Microsoft BizTalk Server\ 目录下，如果从 BizTalk Server 2009 或 BizTalk Server 2006 R2 升级到 BizTalk Server 安装或正在运行的计算机上安装 BizTalk Server64 位版本的 Windows，必须修改文件 StaticAdapterManagement.reg 使用相应的路径。 默认情况下，BizTalk Server 安装到 %programfiles(x86) %\Microsoft 运行 Windows 的 64 位版本的计算机上的 BizTalk Server\ 目录。 更新与"揑 InboundAssemblyPath"、"揙 OutboundAssemblyPath"和"AdapterMgmtAssemblyPath"值，使其指向正确的位置的指定文件相关联的路径。  
   > 
   > [!IMPORTANT]
   >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**StaticAdapterManagement.reg**注册表文件。  

3. 在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**。  

4. 若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  

#### <a name="to-install-the-sample-static-adapter"></a>若要安装示例静态适配器  

1. 单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  

2. 在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，并单击以展开**平台设置**.  

3. 右键单击**适配器**，单击**新建**，然后单击**适配器**。  

4. 在中**添加适配器**对话框框中，执行以下操作。  


   |  使用此选项   |                      执行的操作                       |
   |-------------|-------------------------------------------------------|
   |  **名称**   |                   类型**静态**。                    |
   | **适配器** | 选择**Static DotNetFile**从下拉列表。 |
   | **注释** |               类型**示例适配器**。                |


5. 单击“确定” 。  

    该静态适配器现在将显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。  

#### <a name="to-stop-and-restart-the-host-instance"></a>若要停止并重新启动主机实例  

1. 单击**启动**，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  

2. 在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，单击此项可展开**平台设置**然后单击**主机实例**。 在右窗格中选择 BizTalkServerApplication。  

3. 在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），然后依次**重新启动**。  

### <a name="running-this-sample"></a>运行本示例  

##### <a name="to-run-the-file-adapter-sample"></a>若要运行文件适配器示例  

1. 单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  

2. 在 BizTalk Server 安装驱动器上创建以下文件夹：  

   -   *\<drive\>*:**\Temp**  

   -   *\<drive\>*:**\Temp\Send**  

   -   *\<drive\>*:**\Temp\Receive**  

3. 若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  

4. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

5. 右键单击**BizTalk Server 管理**节点，然后选择**连接到现有组**。  

6. 在中**连接到现有 BizTalk Server 配置数据库**对话框框中，执行以下操作。  

   > [!NOTE]
   >  BizTalk 管理数据库也称为 BizTalk 配置数据库。  

   |    使用此选项    |                                                                                    执行的操作                                                                                     |
   |----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **SQL Server** |                                                                              类型 **。** （句点）。                                                                               |
   |  **“数据库”**  | 选择配置向导创建的 BizTalk 管理数据库的名称。 使用配置向导的默认数据库名称是**BizTalkMgmtDb**。 |


7. 单击“确定” 。  

8. 展开**BizTalk 组 [*服务器名称*]** 中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**应用程序**节点，展开**BizTalk Application 1**节点。  

9. 右键单击**发送端口**节点，并单击**新建**，选择**静态单向发送端口**，然后单击**确定**。  

10. 在中**发送端口属性**对话框中，选择**常规**，并执行以下操作。  


    |      使用此选项      |                                                                                                                                                                                   执行的操作                                                                                                                                                                                   |
    |--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |      **名称**      |                                                                                                                                                                             类型**AdapterSend**。                                                                                                                                                                              |
    | **传输类型** | 选择**静态**从下拉列表单击**配置**。<br /><br /> -在**Directory**框中，键入 ***\<驱动器\>*:\Temp\Send**。<br />-在**文件模式**框中，选择**CreateNew**。<br />-在**文件名**框中，键入 **%MessageID%.xml**。<br />-单击**确定**。<br />- **URI**字段应该显示 ***\<驱动器\>*:\Temp\Send\\%MessageID%.xml**。 |
    | **发送管道**  |                                                                                                                                   选择**PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**，然后单击**确定**。                                                                                                                                    |


11. 下**BizTalk Application 1**节点单击**接收端口**，然后选择**新建 / 单向接收端口**。  

12. 中**创建新接收端口**对话框中，在**指定的接收端口类型**框中，选择**单向接收端口**从下拉列表，，然后单击**确定**。  

13. 在中**接收端口属性**对话框中**名称**框中，键入**AdapterReceive**，然后单击**确定**。  

14. 下**BizTalk Application 1**右键单击节点**接收位置**，然后选择**新建 / 单向接收位置**。  

15. 在中**选择接收端口**对话框中，选择**AdapterReceive**然后单击**确定**。  

16. 在中**接收位置属性**对话框框中，执行以下操作。  


    |       使用此选项       |                                                                                                                                                                                               执行的操作                                                                                                                                                                                                |
    |----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |       **名称**       |                                                                                                                                                                                     类型**AdapterReceiveLocation**                                                                                                                                                                                     |
    |  **传输类型**  |                                                                                                                                                  选择**静态**从下拉列表和命中**配置**以访问其余属性。                                                                                                                                                  |
    |       **URI**        | -单击省略号按钮 (**...**).<br />-在**数量的文件中批处理**框中，键入**20**。<br />-在**Directory**框中，键入 ***\<驱动器\>*:\Temp\Receive**。<br />-确保**文件掩码**属性设置为 **\*.xml**。<br />-在**轮询间隔**框中，键入**5**，然后单击**确定**。<br />-确保**URI**标签包含 ***\<驱动器\>*:\Temp\Receive\\\*.xml**。 |
    | **接收处理程序**  |                                                                                                                                                                      选择**BizTalkServerApplication**从下拉列表。                                                                                                                                                                       |
    | **接收管道** |                                                                                                                                                                             选择**XMLReceive**从下拉列表。                                                                                                                                                                              |


17. 单击“确定” 。  

     请继续执行*构建、 部署和绑定示例适配器*。  

### <a name="building-deploying-and-binding-the-sample-adapter"></a>生成、 部署和绑定示例适配器  
 在适配器投入使用前，必须生成项目、 绑定业务流程与端口并登记适配器。  

##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a>若要创建静态适配器的强名称密钥  

1.  启动**Visual Studio 命令提示符**。  

2.  在命令提示符下，将当前目录更改为\<*示例路径*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter 工具**目录。  

3.  在命令提示符处，键入**sn – k AdapterHarness.snk**，然后按 enter。  

4.  单击“确定” 。  

##### <a name="to-build-the-adapter-harness-project"></a>若要生成适配器管理项目  

-   在解决方案资源管理器中右键单击**AdapterHarnessProject**，然后单击**重新生成**。  

##### <a name="to-deploy-the-adapter-harness-project"></a>若要部署适配器管理项目  

1.  在解决方案资源管理器，该项目已重新生成时，右键单击**AdapterHarnessProject**，然后单击**部署**。  

2.  在 BizTalk Server 管理控制台中，选择的项目已部署，然后依次**刷新**。  

##### <a name="to-bind-the-orchestration-with-the-ports"></a>若要将端口与业务流程绑定  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在相应[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，展开**业务流程**节点。  

2. 右键单击**AdapterHarness.AdapterHarnessType**，然后单击**绑定**。  

3. 在中**端口绑定属性-AdapterHarness.AdapterHarnessType-绑定配置**对话框框中，执行以下操作。  


   |          使用此选项          |                     执行的操作                     |
   |----------------------------|----------------------------------------------------|
   | **AdapterFileReceivePort** | 选择**AdapterReceive**从下拉列表。 |
   |  **AdapterFileSendPort**   |  选择**AdapterSend**从下拉列表。   |


4. 在左窗格中，单击**主机**。  

5. 在中**主机**框中，选择**BizTalkServerApplication**从下拉列表中，然后单击**确定**。  

   请继续执行*管理示例适配器*。  

### <a name="administering-the-sample-adapter"></a>管理示例适配器  
 完成示例适配器在 BizTalk 管理控制台中的管理任务。  

##### <a name="to-administer-the-file-adapter-sample"></a>若要管理文件适配器示例  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在左窗格中，依次单击展开**应用程序**，单击此项可展开**BizTalk Application 1**，然后单击**接收位置**。  

3. 请确保**AdapterReceive**状态**已启用**。  

    如果状态不是**已启用**，右键单击**AdapterReceive**在右窗格中，然后单击**启用**。  

4. 在左窗格中，单击**业务流程**并确保**AdapterHarness.AdapterHarnessType**是**已登记**。 右键单击**AdapterHarness.AdapterHarnessType**，然后单击**登记**(如果 AdapterHarness.AdapterHarnessType 已经登记，**登记**菜单选项不可用）。  

5. 右键单击**AdapterHarness.AdapterHarnessType** ，然后选择**启动**。 此业务流程的状态应更改为**运行**。  

   请继续执行*测试示例适配器*。  

### <a name="testing-the-sample-adapter"></a>测试示例适配器  
 部署示例适配器后，必须停止并重新启动主机实例。 将其放入生产之前测试示例适配器至关重要。  

##### <a name="to-stop-and-restart-the-host-instance"></a>若要停止并重新启动主机实例  

1.  在中**BizTalk Server 管理**控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组**，单击此项可展开**平台设置**然后单击**主机实例**。 在右窗格中选择 BizTalkServerApplication。  

2.  右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。  

     主机实例的状态将变为**已停止**。  

3.  右键单击该主机实例，然后依次**启动**。  

     主机实例的状态将变为**运行**。  

##### <a name="to-test-the-sample-static-adapter-runtime"></a>若要测试示例静态适配器运行时  

1.  在 Windows 资源管理器，导航到\<*示例路径*\>**\AdaptersDevelopment\File 适配器**目录，并复制到剪贴板 InstanceXML.xml 文件。  

2.  导航到*\<驱动器\>*:**\Temp\Receive** Instance.xml 文件并粘贴到该文件夹。  

     如果传输和接收适配器正在工作，该文件应移*\<驱动器\>*:**\Temp\Receive**文件夹*\<驱动器\>* :**\Temp\Send**文件夹。  

##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a>若要测试示例静态适配器的示例添加适配器向导功能  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**AdapterHarnessProject**，依次指向**添加**，然后单击**添加生成的项**。  

2. 在中**添加生成的项目-AdapterHarnessProject**对话框中，单击**添加适配器元数据**，然后单击**打开**。  

    将显示已注册适配器列表。  

3. 选择**Static DotNetFile**，然后单击**下一步**。  

    将显示由适配器公开的服务组织。  

4. 展开**服务组织**，**卫生保健**，然后单击**管理**。  

    请注意，**资格**以不同方式显示来自其他节点。 **资格**是可以选择一个服务节点。 其他节点是不会介绍任何特定服务的组织节点。  

5. 选择**资格**节点，并单击**完成**。  

    BizTalk 将.odx 文件和一个.xsd 文件导入项目。  

    现在可以使用架构、 Porttype、 操作和 Messagetype 从适配器的 BizTalk 项目计划中导入。  

## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 接口：IBaseMessage、 IPropertyBag、 IBTTransportProxy  

 类 （来自基本适配器）：AsyncTransmitterEndpoint, AsyncTransmitter, BatchMessage, ControlledTermination, ReceiverEndpoint, DotNetFileCommonProperties, BatchOperationType  

### <a name="comments"></a>注释  
 示例适配器后，可以修改示例适配器创建自定义的静态或动态适配器的详细信息，请参阅[适配器设计时配置](../core/adapter-design-time-configuration.md)。  

## <a name="see-also"></a>请参阅  
 [适配器示例-用法](../core/adapter-samples-usage.md)   
 [注册适配器](../core/registering-an-adapter.md)