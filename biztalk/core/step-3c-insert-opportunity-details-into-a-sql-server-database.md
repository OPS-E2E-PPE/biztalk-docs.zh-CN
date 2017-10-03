---
title: "步骤 3c: SQL Server 数据库中插入机会详细信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a>步骤 3c: SQL Server 数据库中插入机会详细信息
迄今，我们已构建用于将查询发送到 Salesforce 并接收响应的业务流程。 在此部分中，我们将更新该业务流程将响应来自 Salesforce 到**OrderDetails**在本地 SQL Server 数据库中，表**订单**。 为此，我们将执行以下广泛的步骤：  
  
-   创建**OrderDetails**表中**订单**本地 SQL Server 数据库中的数据库。  
  
-   使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]适用于[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上生成 Insert 操作架构**OrderDetails**表。  
  
-   创建一个映射，以便转换 Salesforce 响应消息与用于插入到消息**OrderDetails** SQL Server 中的表。  
  
-   更新业务流程用于转换插入到响应消息**OrderDetails**表。  
  
## <a name="create-sql-server-database-and-table"></a>创建 SQL Server 数据库和表  
  
#### <a name="to-create-the-database-and-table"></a>创建数据库和表  
  
1.  打开 SQL Server Management Studio 并以管理员身份连接。  
  
2.  右键单击**数据库**节点，然后单击**新数据库**。 指定数据库名称作为`Orders`并指定其他详细信息，以创建新的数据库。  
  
3.  打开查询编辑器并运行以下查询以创建**OrderDetails**表中**订单**数据库：  
  
    ```  
    USE [Orders]  
    GO  
    /****** Object:  Table [dbo].[OrderDetails]    Script Date: 07-12-2012 22:15:47 ******/  
    SET ANSI_NULLS ON  
    GO  
    SET QUOTED_IDENTIFIER ON  
    GO  
    SET ANSI_PADDING ON  
    GO  
    CREATE TABLE [dbo].[OrderDetails]([ID] [int] IDENTITY(1,1) NOT NULL,  
    [TITLE] [varchar](200) NULL,  
    [ProductName] [varchar](200) NULL,  
    [Quantity] [float] NULL,  
    [Amount] [float] NULL,  
    PRIMARY KEY CLUSTERED   
    (  
    [ID] ASC  
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
    GO  
    SET ANSI_PADDING OFF  
    GO  
    ```  
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a>创建用于对 OrderDetails 表执行 Insert 操作的架构  
 安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，它可以用于中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目以生成 Insert 操作的架构上**OrderDetails**表。 本部分提供创建消息架构时要执行的步骤。  
  
#### <a name="to-create-the-schema-for-insert-operation"></a>创建用于 Insert 操作的架构  
  
1.  右键单击**BtsSalesforceIntegration**项目，指向**添加**，然后单击**添加生成的项**。 在**添加生成的项**对话框中，单击**使用适配器服务**，然后单击**添加**。  
  
2.  在[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，从选择绑定的下拉列表中，单击**sqlBinding**，然后单击**配置**。  
  
3.  在**配置适配器**对话框中，在**安全**选项卡上，为**客户端凭据类型**，选择**Windows**为使用 Windows若要连接到 SQL Server 数据库的身份验证。  
  
4.  在**配置适配器**对话框中，在**URI 属性**选项卡上，为**初始目录**指定 (Orders) 连接到的数据库名称。 有关**服务器**指定安装了你要连接到的 SQL Server 的计算机名称。 SQL Server 数据库是否为同一台计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目中，可以只将期间 (**。**)。 单击 **“确定”**。  
  
5.  在[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]单击**连接**。 建立连接后，选择与具有协定类型**客户端 （出站操作）**。 下**选择类别**框中，展开**表**，单击**OrderDetails**表，然后在右窗格中单击**插入**，然后单击**添加**。  
  
6.  指定**文件名前缀**如果你想要前缀标识符与生成的架构。 对于本教程，让我们指定作为前缀**InsertOrders** ，然后单击**确定**。  
  
     此时，多个架构将添加到项目中。 我们将使用用于插入到消息的架构**OrderDetails**表是**InsertOrdersTableOperation.dbo.OrderDetails.xsd**。  
  
## <a name="map-salesforce-response-and-insert-schemas"></a>映射 Salesforce 响应架构和插入架构  
 现在，我们有两个架构 (来自 Salesforce 并将插入到响应**OrderDetails**)，我们必须映射到 insert 架构从 Salesforce 响应架构**OrderDetails**以便可以在 SQL Server 数据库表中插入从 Salesforce 的响应消息。  
  
#### <a name="to-map-the-schemas"></a>若要将架构映射  
  
1.  右键单击**BtsSalesforceIntegration**项目，指向**添加**，单击**新项**，然后单击**映射**。 将映射名称指定为`QueryResult_Orders.btm`，然后单击**添加**。  
  
2.  在代码图图面，对于源架构中，选择**QueryResult**和对于目标架构中，选择**InsertOrdersTableOperation.dbo.OrderDetails.xsd** ，其中，然后**插入**节点。  
  
3.  映射这两个架构，如下面的屏幕快照中所示：  
  
     ![映射到 Insert 架构的 Salesforce 响应](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")  
  
     请注意，地图使用**循环**之间 functoid**记录**和**OrderDetails**链接。 这样可确保所有一个或多个匹配项下的节点**记录**映射到类似出现下的子节点的**OrderDetails**。  
  
4.  保存对映射所做的更改。  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a>更新业务流程，以将消息插入到 SQL Server  
 在此部分中，我们将在业务流程中使用映射，将 Salesforce 响应消息转换为用于将订单详细信息插入到 SQL Server 表的消息。 我们还将添加用于将该消息发送到 SQL Server 的端口。  
  
#### <a name="to-update-the-orchestration"></a>若要更新业务流程  
  
1.  为插入架构创建消息变量。 在业务流程视图中，右键单击**消息**节点，，然后单击**新消息**。 设置消息同名**InsertOrders**和消息类型作为**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**。  
  
2.  添加后的构造消息形状**ReceiveQueryResult**形状。 设置到形状的名称`ConstructOrders`并设置**消息构造**属性**InsertOrders**。  
  
3.  在**ConstructOrders**形状，添加**转换**形状。 双击“转换”形状以打开“转换配置”对话框。 在对话框中，选择**现有映射**选项，然后再从下拉列表选中**BtsSalesforceIntegration.QueryResult_Orders**。 设置**源**到**QueryResultMsg**，**目标**到**InsertOrders**，然后单击**确定**。  
  
4.  后**ConstructOrders**形状，添加发送形状。 命名形状`SendOrders`和将消息类型设置为**InsertOrders**。  
  
5.  添加用于将订单详细信息插入到 Salesforce 的端口。 在“端口配置”向导中，选择以下选项：  
  
    -   将端口名称指定为`SendToSQL`。  
  
    -   选择用于创建新的端口类型的选项。  
  
    -   设置**通信模式**到*单向*。  
  
    -   设置**端口的通信的方向**到*我将始终发送消息上此端口*并设置**端口绑定**到*稍后指定*。  
  
     连接**请求**操作到端口**SendOrders**发送形状来完成业务流程。 以下屏幕快照描述了已完成的业务流程（端到端）。  
  
     ![Salesforce 集成的完整 orchesration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")  
  
     向项目添加强名称密钥文件，并保存对项目所做的更改。  
  
 使用本主题中的步骤，我们已经完成业务流程，以接收来自 Salesforce 的机会通知，查询 Salesforce 以获取有关机会的详细信息，然后将查询响应插入到 SQL Server 数据库中。 在随后的主题中，我们将构建此解决方案的其他一些关键组件，这些组件用于向 Salesforce 进行身份验证，并在 BizTalk Server 内处理 Salesforce 响应。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)