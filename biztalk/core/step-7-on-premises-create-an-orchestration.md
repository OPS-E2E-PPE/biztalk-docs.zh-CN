---
title: "步骤 7 （在本地）： 创建业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c0b6d0e-cf00-4eee-9b89-28210bad46f4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b92a641252a76f4668cdf4c96c8df442c43d4719
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-on-premises-create-an-orchestration"></a>步骤 7 （在本地）： 创建业务流程
根据业务方案之后,[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的销售订单消息从 Service Bus 队列，它需要检查消息中订购数量是否大于 100。 如果数量大于 100，将消息插入**SalesOrder**表。 否则会将消息发送到共享文件位置。 Northwind 通过创建一个业务流程来实现此业务逻辑。 本主题提供如何创建该业务流程的分步指南。  
  
### <a name="to-add-an-orchestration-to-the-includebtsbiztalkservernoversionincludesbtsbiztalkservernoversion-mdmd-project"></a>向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中添加业务流程的步骤  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你已创建，右键单击项目，指向**添加**，然后单击**新项**。  
  
2.  在**新项**对话框中，选择**BizTalk 业务流程**，输入映射名称为`OrderProcessing.odx`，然后单击**添加**。  
  
## <a name="create-messages-for-the-orchestration"></a>为业务流程创建消息  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在你必须为业务流程创建消息，然后将其链接到之前生成的架构。 你需要创建以下三个消息：  
  
|消息名称|对应的架构|  
|------------------|---------------------------|  
|Message1_SO_Inbound|此消息是的一个实例**ECommerceSalesOrder.xsd**架构。|  
|Message2_SO_Inbound|此消息是一份**Message1_SO_Inbound**。 作为最佳实践，你必须创建该消息的副本，然后修改新的消息，使原始消息保持不变。 有关详细信息，请参阅[BizTalk Server 消息](http://msdn.microsoft.com/library/aa560436)。|  
|Message1_SO_Outbound|此消息是的一个实例**TableOperations.dbo.SalesOrder (Insert)**架构。|  
  
#### <a name="to-create-the-messages"></a>创建消息的步骤  
  
1.  打开**业务流程视图**BizTalk 项目，如果尚未打开的窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |属性名称|执行操作|  
    |-------------------|--------------------|  
    |Identifier|输入`Message1_SO_Inbound`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*OrderProcessingDemo.ECommerceSalesOrder*，其中*OrderProcessingDemo*是你的 BizTalk 的名称项目。 *ECommerceSalesOrder*是从服务总线队列接收的销售订单消息的架构。|  
  
5.  重复上述步骤，使用以下详细信息创建消息：  
  
    |消息名||  
    |------------------|-|  
    |Message2_SO_Inbound|-将设置**标识符**到`Message2_SO_Inbound`<br />-将设置**消息类型**到*OrderProcessingDemo.ECommerceSalesOrder*|  
    |Message1_SO_Outbound|-将设置**标识符**到`Message1_SO_Outound`<br />-将设置**消息类型**到*OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*|  
  
## <a name="add-shapes-to-the-orchestration"></a>向业务流程添加形状  
 业务流程形状定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序流。 在本部分中，将向业务流程添加所需形状。  
  
#### <a name="to-add-shapes-to-the-orchestration"></a>若要将形状添加到业务流程  
  
1.  开始时，必须添加**接收**形状。 此形状将接收来自 Service Bus 队列的传入销售订单消息。 在接收形状上设置以下属性。  
  
    1.  设置**激活**到**True**。  
  
    2.  设置**消息**到**Message1_SO_Inbound**。  
  
    3.  设置**名称**到**ReceiveOrder**。  
  
2.  如前所述，你必须为接收到业务流程中的原始销售订单消息创建一个副本。  
  
    1.  拖放**构造消息**下调整**ReceiveOrder**形状。 因为你可以使用此形状来构造一条消息的类型 Message2_SO_Inbound，设置**消息构造**属性**Message2_SO_Inbound**。  
  
    2.  添加**消息分配**中调整**构造消息**形状。 双击该形状以打开表达式编辑器，然后添加以下代码：  
  
        ```  
        Message2_SO_Inbound = Message1_SO_Inbound; //copy the message  
        Message2_SO_Inbound(*) = Message1_SO_Inbound(*); //copy the context properties on the message  
        ```  
  
         单击 **“确定”**。  
  
3.  根据本业务方案，必须根据已订购货品的数量将该消息发送到不同目标。 因此，你必须现在从传入的销售订单消息中提取出数量值。  
  
    1.  **数量**入站消息 (ECommerceSalesOrder.xsd) 中的元素包含的值的有序的数量。 你必须升级该属性，以便将此元素用在业务流程中的表达式中。 若要升级的属性，打开**ECommerceSalesOrder.xsd**架构中，右键单击**数量**，指向**Promote**，然后单击**快速提升**.  
  
    2.  创建用于存储数量值的变量。 若要创建一个变量，从**业务流程视图**，右键单击**变量**，然后单击**新变量**。 为变量设置以下属性：  
  
        |属性名称|值|  
        |-------------------|-----------|  
        |Identifier|输入`quantityOrdered`|  
        |类型|选择**Int32**。|  
  
    3.  你现在必须将分配中的值**数量**元素**quantityOrdered**变量。 拖放**表达式编辑器**后**构造消息**形状。 打开该编辑器，然后输入以下表达式：  
  
        ```  
        quantityOrdered = Message2_SO_Inbound.Quantity;  
        ```  
  
         单击 **“确定”**。  
  
4.  提取出订购数量后，现在你需要创建一个判定块，以便在该判定块上布置消息流将采取的两个单独路线。 通过添加业务流程中创建的决策块**确定**形状。  
  
    1.  拖放式**确定**后调整**表达式编辑器**形状。  
  
    2.  选择**Rule_1**形状并在**属性**窗口中，指定下列各项：  
  
        |属性名称|值|  
        |-------------------|-----------|  
        |Identifier|输入`Yes`。 **注意：**其他路由是默认情况下名为**Else**。|  
        |表达式|输入`quantityOrdered > 100`。|  
  
         现在你有两条路线可用。 如果中的值**quantityOrdered**变量大于 100，消息将**是**路由。 否则，它采用**Else**路由。 现在你必须定义要在每个路线中执行的操作。  
  
5.  根据本业务方案，如果订购数量大于 100，则必须将消息插入到 SalesOrder 表中。 因此，在**是**路由，必须转换 ECommerceSalesOrder.xsd 架构与 TableOperations.SalesOrder.Insert 架构。 主题中创建插入架构[步骤 5 （在本地）： 生成插入消息 inito SalesOrder 表的架构](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)。 转换该架构后，必须将消息发送到 SQL Server 数据库表以外的消息中。  
  
    1.  在**是**路由、 拖动和删除**构造消息**形状。 设置**消息构造**属性到形状**Message1_SO_Outbound**。  
  
    2.  在**构造消息**形状添加**转换**形状。 双击要打开的形状**转换配置**对话框。 请执行以下操作：  
  
        1.  选择**现有映射**选项。  
  
        2.  从**完全限定的映射名称**下拉列表中，选择**OrderProcessingDemo.SalesOrder_SQL**。  
  
        3.  有关**源**，选择**Message2_SO_Inbound**。  
  
        4.  有关**目标**，选择**Message1_SO_Outound**。  
  
    3.  后**构造消息**形状、 拖动和删除**发送**的形状，然后设置**消息**属性到形状`Message1_SO_Outbound`。  
  
6.  根据本业务方案，如果订购数量小于 100，则必须将消息发送到共享文件位置。 因此，在**Else**必须添加发送形状的路由。  
  
    1.  在**Else**路由、 拖动和删除**发送**形状，并设置**消息**属性到形状`Message2_SO_Inbound`。  
  
        > [!NOTE]
        >  你将“消息”设置为 Message2_SO_Inbound，是因为从 Service Bus 队列收到的同一消息将发送到此文件位置，而不做任何处理。 Message2_SO_Inbound 表示由 Service Bus 队列接收的消息。  
  
## <a name="add-ports-to-the-orchestration"></a>向业务流程添加端口  
 端口表示有关业务流程的消息的输入和输出媒介。 消息由业务流程使用接收端口处理，然后使用发送端口送出。 在本业务方案中，将从一种媒介（Service Bus 队列）接收消息，然后基于消息处理将其发送到两个不同的位置（SQL Server 数据库或文件共享位置）。 因此，必须创建一个接收端口和两个发送端口作为业务流程的一部分。  
  
#### <a name="to-add-ports"></a>添加端口的步骤  
  
1.  拖放式**端口**形状变为**端口图面**窗格**业务流程设计器**以启动**端口配置向导**。 上**欢迎**页上，单击**下一步**。  
  
2.  在**端口属性**页上，将该端口用作`ReceiveSO`，然后单击**下一步**。  
  
3.  在**选择端口类型**页上，选择**创建新的端口类型**选项中，选择**单向**通信模式，保留有关访问限制，默认值，然后单击**下一步**。  
  
4.  在**端口绑定**页上，选择的端口方向**我将始终接收此端口上的消息**，保留为默认值端口候机，然后单击**下一步**.  
  
5.  在最后一页上，单击**完成**。  
  
6.  重复上述步骤以创建两个发送端口。 在创建端口的同时指定以下值。  
  
    |端口名称|属性|  
    |---------------|----------------|  
    |SendToSQL|-将设置**名称**到**SendToSQL**<br />-选择**创建新的端口类型**<br />集通信模式与**单向**<br />-将端口方向设置为**我将始终发送消息上此端口**|  
    |SendToFile|-将设置**名称**到**SendToFile**<br />-选择**创建新的端口类型**<br />集通信模式与**单向**<br />-将端口方向设置为**我将始终发送消息上此端口**|  
  
## <a name="connect-ports-and-message-shapes"></a>连接端口和消息形状  
 现在，你必须连接端口和消息形状以完成业务流程。 接收此消息时，业务流程将启动**ReceiveOrder**形状和业务流程退出由两个发送形状发送消息。 你必须使用此标准来连接端口与消息形状  
  
#### <a name="to-connect-ports-with-message-shapes"></a>连接端口与消息形状的步骤  
  
1.  连接**ReceiveSO**接收到的端口**ReceiveOrder**形状。  
  
2.  连接下的发送形状**是**将路由到**SendToSQL**发送端口。 这表示如果消息进入此路由 (**quantityOrdered** > 100)，它将发送到**SalesOrder** SQL Server 数据库中的表。  
  
3.  连接下的发送形状**Else**将路由到**SendToFile**发送端口。 这表示如果消息进入此路由 (**quantityOrdered** < = 100)，它将发送到指定的文件位置。  
  
     业务流程必须类似于以下内容：  
  
     ![业务流程](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)