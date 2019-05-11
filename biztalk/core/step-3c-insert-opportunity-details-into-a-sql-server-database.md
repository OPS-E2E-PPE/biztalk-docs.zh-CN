---
title: 步骤 3c:将机会详细信息插入到 SQL Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c49c7b182d3a6fda593ea34f20238328f47ce5a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392598"
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a>步骤 3c:将机会详细信息插入到 SQL Server 数据库
现在，我们已构建业务流程，以向 Salesforce 发送查询并接收响应。 在本部分中，我们将更新该业务流程，以将响应插入到 salesforce **OrderDetails**在本地 SQL Server 数据库中，表**订单**。 若要实现此目的，我们将执行以下广泛的步骤：  
  
- 创建**OrderDetails**表中**订单**的本地 SQL Server 数据库中的数据库。  
  
- 使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上生成的 Insert 操作架构**OrderDetails**表。  
  
- 创建映射到插入的消息将 Salesforce 响应消息转换**OrderDetails** SQL Server 中的表。  
  
- 更新业务流程，以便通过转换到将响应消息插入**OrderDetails**表。  
  
## <a name="create-sql-server-database-and-table"></a>创建 SQL Server 数据库和表  
  
#### <a name="to-create-the-database-and-table"></a>若要创建数据库和表  
  
1.  打开 SQL Server Management Studio 并以管理员身份连接。  
  
2.  右键单击**数据库**节点，然后单击**新数据库**。 指定数据库名称，例如`Orders`并指定其他详细信息，以创建新的数据库。  
  
3.  打开查询编辑器，并运行以下查询以创建**OrderDetails**表中**订单**数据库：  
  
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
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a>为对 OrderDetails 表的插入操作创建架构  
 安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供了[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，它可以用于中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目以生成 Insert 操作的架构上**OrderDetails**表。 本部分提供创建消息架构时要遵循的步骤。  
  
#### <a name="to-create-the-schema-for-insert-operation"></a>若要创建用于插入操作的架构  
  
1. 右键单击**BtsSalesforceIntegration**项目，指向**添加**，然后单击**添加生成的项**。 在中**添加生成的项**对话框中，单击**使用适配器服务**，然后单击**添加**。  
  
2. 在中[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]，从绑定下拉列表中选择，单击**sqlBinding**，然后单击**配置**。  
  
3. 在**配置适配器**对话框中的**安全**选项卡上，对于**客户端凭据类型**，选择**Windows**若要使用 Windows若要连接到 SQL Server 数据库的身份验证。  
  
4. 在中**配置适配器**对话框中的**URI 属性**选项卡上，对于**Initial Catalog**指定数据库名称 (Orders) 连接到。 有关**Server**指定安装了 SQL Server 要连接到的计算机名称。 SQL Server 数据库是否为同一台计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目中，你可以放置一个句点 (**。**)。 单击“确定” 。  
  
5. 在中[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]单击**Connect**。 建立连接后，选择作为协定类型**客户端 （出站操作）**。 下**选择一个类别**框中，展开**表**，单击**OrderDetails**表，然后在右窗格中单击**插入**，然后单击**添加**。  
  
6. 指定**文件名前缀**如果你想要生成的架构标识符的前缀。 对于本教程中，让我们指定作为前缀**InsertOrders** ，然后单击**确定**。  
  
    多个架构添加到项目中。 我们将用于将消息插入到架构**OrderDetails**表是**InsertOrdersTableOperation.dbo.OrderDetails.xsd**。  
  
## <a name="map-salesforce-response-and-insert-schemas"></a>映射 Salesforce 响应架构和插入架构  
 现在，我们有两个架构 (来自 Salesforce 并将插入到响应**OrderDetails**)，我们必须映射为插入架构，从 Salesforce 响应架构**OrderDetails**以便可以在 SQL Server 数据库表中插入从 Salesforce 的响应消息。  
  
#### <a name="to-map-the-schemas"></a>若要将架构映射  
  
1.  右键单击**BtsSalesforceIntegration**项目，指向**添加**，单击**新项**，然后单击**映射**。 映射名称指定为`QueryResult_Orders.btm`，然后单击**添加**。  
  
2.  在映射图面上，对于源架构中，选择**QueryResult** ，对于目标架构中，选择**InsertOrdersTableOperation.dbo.OrderDetails.xsd** ，然后在其中， **插入**节点。  
  
3.  将两个架构的映射，如以下屏幕截图中所示：  
  
     ![将映射到插入架构的 Salesforce 响应](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")  
  
     请注意，地图**循环**functoid 之间**记录**并**OrderDetails**链接。 这可确保所有一个或多个出现的节点下**记录**映射到的节点下出现类似次数**OrderDetails**。  
  
4.  将更改保存到该映射。  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a>更新业务流程，以将消息插入到 SQL Server  
 在本部分中，我们将使用业务流程中的映射 Salesforce 响应消息转换为 SQL Server 表中插入订单详细信息的消息。 我们还将添加一个端口，以将该消息发送到 SQL Server。  
  
#### <a name="to-update-the-orchestration"></a>若要更新业务流程  
  
1. 创建插入架构的消息变量。 从业务流程视图中，右键单击**消息**节点，并单击**新消息**。 设置消息名称， **InsertOrders**消息类型作为**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**。  
  
2. 添加构造消息形状后的**ReceiveQueryResult**形状。 设置该形状的名称`ConstructOrders`并设置**构造的消息**属性设置为**InsertOrders**。  
  
3. 内**ConstructOrders**形状中，添加**转换**形状。 双击要打开转换配置对话框中的转换形状。 在对话框中，选择**现有的映射**选项，然后再从下拉列表中选择**BtsSalesforceIntegration.QueryResult_Orders**。 设置**源**到**QueryResultMsg**，**目标**到**InsertOrders**，然后单击**确定**。  
  
4. 之后**ConstructOrders**形状中，添加发送形状。 该形状命名`SendOrders`并将作为消息类型设置**InsertOrders**。  
  
5. 添加用于将订单详细信息插入到 Salesforce 的端口。 在端口配置向导中，选择以下选项：  
  
   - 将端口名称指定为`SendToSQL`。  
  
   - 选择选项以创建新的端口类型。  
  
   - 设置**通信模式**到*单向*。  
  
   - 设置**端口通信方向**到*我始终在发送消息此端口上*并设置**端口绑定**到*以后指定*。  
  
     连接**请求**到端口的操作**SendOrders**发送形状以完成业务流程。 下面的屏幕截图描绘了已完成的业务流程的端到端。  
  
     ![Salesforce 集成的完整业务流程](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")  
  
     向项目添加强名称密钥文件并将更改保存到项目。  
  
   使用本主题中的步骤，我们已经完成业务流程，以接收来自 Salesforce 的机会通知，查询 Salesforce 的机会，有关更多详细信息，然后将查询响应插入到 SQL Server 数据库。 在随后的主题，我们将构建一些其他关键组件的解决方案，用于使用 Salesforce 和 BizTalk Server 内处理 Salesforce 响应进行身份验证。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)