---
title: "事务适配器 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfad3a99d313a8007962cf56f403243c72f6a377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transactional-adapter-biztalk-server-sample"></a>事务适配器 （BizTalk Server 示例）
事务性适配器示例演示如何在处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息期间，根据数据库创建并使用显式 Microsoft 分布式事务处理协调器 (MSDTC) 事务。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包含一个接收适配器，该适配器以用户指定的间隔运行 SQL 语句，使用 MSDTC 事务从 SQL Server 数据库中获取数据。 然后，以同一事务上下文中的消息的形式将数据提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库。  
  
 相应的发送适配器使用来自事务上下文中 BizTalk 消息的输入运行用户指定的 SQL 存储过程。 它使用来自该消息中的特定数据，找到并删除同一事务中 MessageBox 数据库中对应的消息。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 此示例在其解决方案中有两个项目。 第一个是在运行前使用的管理项目 (Admin)，以允许用户配置使用此适配器的接收位置和发送端口。 第二个是在发送和接收适配器正在执行时运行的运行时项目 (Runtime)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*> \Samples\AdaptersDevelopment\TransactionalAdapter。 管理配置项目位于 \Admin 文件夹中，而运行时项目位于 \Runtime 文件夹中。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|Admin 项目文件名|Admin 项目文件说明|  
|----------------------------|------------------------------------|  
|TransactionalAdmin.csproj|用于进行运行时预配置的适配器管理项目文件|  
|TransactionalReceiveHandler.xsd|接收处理程序属性的 XSD|  
|TransactionalReceiveLocation.xsd|接收位置属性的 XSD|  
|TransactionalTransmitLocation.xsd|传输位置属性的 XSD|  
|TransactionalTransmitHandler.xsd|传输处理程序属性的 XSD|  
|TransactionalAdapterManagement.cs|适配器配置管理。 包含 GetConfigSchema，BizTalk 适配器框架调用 GetConfigSchema 以返回它所支持的每种（四种）可能配置类型的 XSD 配置架构。|  
  
|Runtime 项目文件名|Runtime 项目文件说明|  
|------------------------------|--------------------------------------|  
|Transactional.csproj|适配器运行时项目文件|  
|TransactionalAsyncBatch.cs|适配器发送部分的异步实现|  
|TransactionalDeleteBatch.cs|删除一批消息和投票，以提交或中止事务|  
|TransactionalProperties.cs|提取和设置配置属性|  
|TransactionalReceiver.cs|创建和管理接收终结点|  
|TransactionalReceiverEndpoint.cs|每个接收位置的实际监听或轮询|  
|TransactionalTransmitter.cs|从消息引擎接受要传输的一批消息|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 本示例可以作为你使用显式事务创建自定义发送和接收适配器的框架。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
> [!IMPORTANT]
>  如果是在 64 位计算机上安装 BizTalk 或安装位置已修改，则需要相应修改 OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath。  
  
#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a>创建事务适配器示例强名称密钥  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  在命令提示符下，键入以下命令，然后按 Enter：  
  
    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  
  
3.  在命令提示符下，键入以下命令，然后按 Enter：  
  
    ```  
    sn –k TransactionalAdapter.snk  
    ```  
  
4.  在命令提示符处，键入**退出**，然后按 enter 以关闭命令提示符窗口。  
  
#### <a name="build-the-transactional-adapter-solution"></a>生成事务适配器解决方案  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
2.  浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter，双击**TransactionalAdapter.sln**以打开此解决方案中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
3.  若要生成这两个事务适配器项目 （管理员和运行时） 在解决方案资源管理器中，右键单击**解决方案 TransactionalAdapter**，然后单击**重新生成**。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="register-the-transactional-adapter"></a>注册该事务的适配器  
  
1.  在 Windows 资源管理器中，导航至 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin。  
  
2.  若要将事务适配器数据添加到注册表中，双击**TransactionalAdmin.reg**。  
  
    > [!NOTE]
    >  **TransactionalAdmin.reg**包括硬编码路径 C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] \\。 如果你的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的安装位置不是默认位置或者是从以前版本升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装，则必须使用相应的路径修改 TransactionalAdmin.reg 文件。 更新与揑“InboundAssemblyPath”、揙“OutboundAssemblyPath”和揂“AdapterMgmtAssemblyPath”值相关联的路径，以指向指定文件的正确位置。  
  
    > [!IMPORTANT]
    >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为在 HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ **TransactionalAdmin.reg**注册表文件。  
  
3.  在**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表中，然后单击**确定**。  
  
4.  若要关闭 Windows 资源管理器，请单击**文件**，然后单击**关闭**。  
  
#### <a name="add-the-transactional-adapter-to-biztalk-server"></a>将事务性适配器添加到 BizTalk Server  
  
1.  单击**启动**菜单上，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk Server 管理**树中，展开**BizTalk 组**树，，然后展开**平台设置**树。  
  
3.  右键单击**适配器**，单击**新建**，然后单击**适配器**。  
  
4.  在**适配器属性**对话框框中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Name|类型**TransactionalAdapter**。|  
    |适配器|选择**Txn**从下拉列表。 此项将作为运行结果显示**TransactionalAdmin.reg**以前文件。|  
    |Description|类型**示例事务适配器**。|  
  
5.  单击“确定” **。** 现在该适配器显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。  
  
#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a>创建使用该适配器的接收端口和位置  
  
1.  展开**BizTalk 组 [服务器名称]**中的节点[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**应用程序**节点，展开**BizTalk 应用程序 1**节点。  
  
2.  右键单击**接收端口**，然后单击**新建**，选择**单向接收端口。**  
  
3.  有关**名称**，输入**TxnReceivePort1**，然后单击**确定**。  
  
4.  右键单击**接收位置**节点，单击**新建**，然后选择**单向接收位置**。  
  
5.  在**选择接收端口**对话框中，选择**TxnReceivePort1**，然后单击**确定**。  
  
6.  在**接收位置属性**对话框中，在**常规**选项卡上，输入**TxnReceiveLocation1**为**名称**。 确保**接收端口**标签显示**TxnReceivePort1**。  
  
7.  在**类型**下拉列表框中，在**传输**帧中，选择**TransactionalAdapter。**  
  
8.  在**接收 * * * 管道**框中，确保**PassThruReceive**选择。 将其他属性保留为默认设置。  
  
9. 单击**配置**按钮旁边**类型**下拉框。 这会显示特定于此适配器的对话框。 指定下列各项，正如你看到的适当情况下，然后单击**确定**。  
  
    |属性|设置|  
    |--------------|-------------|  
    |连接字符串|用于连接 Northwind 数据库并进行身份验证的 SQL 数据库连接字符串。 我们随后运行的 SQL 脚本将使用此数据库。|  
    |命令文本|针对 Northwind 数据库执行的 SQL 语句，目的是获取要输入到 BizTalk 消息中的数据。|  
    |Cookie|包括部分 URI，因此请输入唯一的值，如接收位置的名称，例如：TxnReceiveLocation1。|  
    |轮询间隔单位|轮询数据的时间单位。 设置为秒。|  
    |轮询间隔|数据的轮询的时间度量单位。 设置为 15 秒。|  
  
10. 单击**确定**以关闭配置对话框中，然后**确定**以关闭**接收位置属性**对话框中，以返回到[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a>创建使用此适配器的发送端口和发送处理程序  
  
1.  与**BizTalk 应用程序 1**仍已展开的节点，右键单击**发送端口**，然后单击**新建**，然后选择**静态单向发送端口**.  
  
2.  在**名称**字段中，输入**TxnSendPort1**。  
  
3.  在**传输**框架，在**类型**下拉列表中，选择**TransactionalAdapter**`.`  
  
4.  在**发送管道**框中，确保**PassThruTransmit**选择。  
  
5.  单击**配置**按钮旁边**传输**下拉列表。在显示的对话框中指定以下正如你看到的适当情况下，然后单击**确定**。  
  
    |属性|设置|  
    |--------------|-------------|  
    |Cookie|包含一部分的 uri 中的唯一在此处输入值如接收位置的名称的实例： **TxnSendPort1**。|  
    |连接字符串|用于连接 Northwind 数据库并进行身份验证的 SQL 数据库连接字符串。 它将很可能是用于配置的同一**TxnReceiveLocation1**接收位置。|  
    |存储过程|若要轮询数据库-获取执行的存储的过程名称**sp_txnProc**。 将消息提供给，BizTalk 正文作为字符串参数调用存储过程@Data。 例如，用户将在此情况下更高版本的存储的过程使用的名称配置**sp_txnProc**。 该适配器在运行时将对数据库执行等效的这种调用。<br /><br /> exec sp_txnProc @Data ="BizTalk 消息的内容"|  
  
6.  在左侧的导航窗格中，单击**筛选器**。  
  
7.  在筛选器表达式编辑器中，输入以下表达式以便设置针对此发送端口的订阅，接收由 TxnReceivePort1 接收端口接收到的任何消息。  
  
     请输入这些值：**BTS。ReceivePortName = = TxnReceivePort1**  
  
    1.  `(property)`  **BTS。ReceivePortName**  
  
    2.  `(operator)`  **==**  
  
    3.  `(value)`  **TxnReceivePort1**  
  
8.  对其余的适配器属性中使用的默认值，然后选择**确定**。  
  
## <a name="run-the-sample"></a>运行示例  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，选择**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框框中，请确保**服务器类型**设置为**数据库引擎**，并输入凭据进行身份验证到数据库服务器，然后选择**连接**。  
  
3.  选择**新查询**工具栏按钮，再粘贴到新的查询窗口，以插入测试表、 测试数据和测试以下存储过程到 Northwind 数据库。 选择**执行**工具栏按钮。  
  
    ```  
    use [Northwind]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    drop table [dbo].[scratch]  
    GO  
    CREATE TABLE [dbo].[scratch] (  
         [id] [int] IDENTITY (1, 1) NOT NULL ,  
         [msg] [nvarchar] (4000) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
    drop procedure [dbo].[sp_txnProc]  
    GO  
    CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
    AS   
    INSERT scratch ( msg ) values ( @Data )  
    GO  
    GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
    GO  
    ```  
  
4.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**发送端口**节点中，选择**TxnSendPort1**发送端口，然后选择**启动**。  
  
5.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**接收位置**节点中，选择**TxnRecieveLocation1**接收位置，，然后选择**启用**。  
  
6.  在启用该接收位置后，它将在指定的时间间隔自动轮询数据库以获得数据。  
  
## <a name="classes-or-methods-used-in-the-sample"></a>类或方法的示例中使用  
* IBTTransmitterBatch 接口 (COM)
  
* IBTTransportProxy 接口 (COM)

这些方法所述[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>另请参阅  
 [适配器样本-开发](../core/adapter-samples-development.md)   
 [注册的适配器](../core/registering-an-adapter.md)