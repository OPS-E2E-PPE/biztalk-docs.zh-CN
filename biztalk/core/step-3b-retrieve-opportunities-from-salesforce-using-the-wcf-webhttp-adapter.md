---
title: 步骤 3b： 使用 Wcf-webhttp 适配器从 Salesforce 检索机会详细信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 115c908f-777b-4c51-85ea-71d639b01775
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66337277e2a84edbe8802b739988bcee030bc054
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008110"
---
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a>步骤 3b： 使用 Wcf-webhttp 适配器从 Salesforce 检索机会详细信息
在本部分中，我们将改进业务流程，以处理传入的机会通知，从通知中提取机会名称，并使用该名称创建请求查询，以发送到 Salesforce。 此请求检索与机会关联的产品的特定详细信息。 来自 Salesforce 的查询响应将接收回 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 为此，我们将执行以下步骤：  
  
-   创建用于向 Salesforce 发送查询消息的架构和消息变量。  
  
-   创建映射，以使用机会通知中的值创建查询，来检索与机会关联的产品详细信息。  
  
-   创建用于从 Salesforce 接收查询响应的架构。  
  
-   为请求和响应架构创建消息变量。  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a>创建用于向 Salesforce 发送查询消息的架构和消息变量  
 若要使用通过机会通知提供的信息从 Salesforce 检索产品详细信息，我们需要向 Salesforce 发送查询。 查询将作为一条 XML 消息发送到 Salesforce。 因此，在下面的过程中，我们将创建请求消息架构。 在随后的过程中，我们会将机会通知架构与此架构相映射，以构造用于检索机会的产品详细信息的查询。  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a>创建用于发送查询请求的架构  
  
1. 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目添加新架构。 将其命名为 `QueryRequest.xsd`。  
  
2. 重命名的根节点`QueryRequest`。 添加 QueryRequest 记录下的子字段元素并将其命名`Query`。  
  
3. 将提升**查询**使其可供在业务流程内使用的架构中的元素。 在后面的步骤中，我们将使用此已升级的元素分配查询字符串。  
  
    右键单击**查询**元素，指向**Promote**，然后单击**快速升级**。 这会导致创建**PropertySchema.xsd**具有架构**查询**元素。 请记下 PropertySchema 的命名空间。 在以后的步骤中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置物理端口时，你将需要此信息。  
  
4. 保存所有更改。  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a>将机会通知架构映射到查询架构  
 若要检索与机会关联的产品详细信息，我们需要向 Salesforce 发送如下查询：  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 在前面的过程中，我们已创建了查询消息架构。 在此过程中，我们将机会通知架构映射到查询请求架构，并使用 functoid 构造此查询。 此查询将传递到的值作为**查询**中的元素**QueryRequest.xsd**架构。  
  
#### <a name="to-map-the-opportunity-notification"></a>映射机会通知  
  
1. 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目添加映射。 该映射`Notification_QueryRequest.btm`。  
  
2. 将源架构设置为**NotificationService_soap_sforce_com_2005_09_outbound.xsd**。 将目标架构设置为**QueryRequest**.xsd。  
  
3. 添加**字符串连接**functoid 到映射图面。 打开**配置字符串连接 Functoid**对话框框，并指定输入的值，如下所示：  
  
   |||  
   |-|-|  
   |Input[0]|SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '|  
   |输入 [1]|将源架构中的 Name 元素连接到 functoid，以使用 Name 元素的值作为第二个输入。|  
   |输入 [2]|'**注意：** 对于最后一个输入值，指定仅右单引号 （'）。|  
  
    下面的屏幕截图描绘了的配置**字符串连接**functoid。  
  
    ![配置字符串连接 functoid](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")  
  
    当三个输入参数连接在一起时，将形成要发送到 Salesforce 的所需查询。  
  
4. 将“字符串连接”functoid 连接到目标架构中的 Query 元素，如下面的屏幕快照中所示。  
  
    ![通知将响应映射到查询架构](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")  
  
5. 保存对映射所做的更改。  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a>创建用于接收查询响应消息的架构  
 在本部分中，我们将创建用于从 Salesforce 接收查询响应消息的架构。 在本部分中，我们将手动创建查询响应架构。  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a>创建用于接收查询响应的架构  
  
1. 添加到新的架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，并命名`QueryResult.xsd`。  
  
2. Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017)对象描述了从 Salesforce 接收查询响应。 因此，我们将构建一个描述以下内容的架构：  
  
   ```  
   <?xml version="1.0" encoding="utf-16" ?>  
   - <xs:schema xmlns="http://BtsSalesforceIntegration.QueryResult" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://BtsSalesforceIntegration.QueryResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     - <xs:element name="QueryResult">  
       - <xs:complexType>  
         - <xs:sequence>  
           <xs:element name="done" type="xs:string" />  
           - <xs:sequence>  
             - <xs:element name="records">  
               - <xs:complexType>  
                 - <xs:sequence>  
                   <xs:element name="Id" type="xs:string" />  
                   <xs:element name="Amount" type="xs:string" />  
                   <xs:element name="Name" type="xs:string" />  
                   - <xs:sequence>  
                     - <xs:element name="OpportunityLineItems">  
                       - <xs:complexType>  
                         - <xs:sequence>  
                           <xs:element name="done" type="xs:string" />  
                           - <xs:sequence minOccurs="1" maxOccurs="unbounded">  
                             - <xs:element name="records">  
                               - <xs:complexType>  
                                 - <xs:sequence>  
                                   <xs:element name="Quantity" type="xs:string" />  
                                   <xs:element name="ListPrice" type="xs:string" />  
                                   - <xs:element name="PricebookEntry">  
                                     - <xs:complexType>  
                                       - <xs:sequence>  
                                         <xs:element name="UnitPrice" type="xs:string" />  
                                         <xs:element name="Name" type="xs:string" />  
                                       </xs:sequence>  
                                       <xs:attribute name="type" type="xs:string" />  
                                       <xs:attribute name="url" type="xs:string" />  
                                     </xs:complexType>  
                                   </xs:element>  
                                 </xs:sequence>  
                                 <xs:attribute name="type" type="xs:string" />  
                                 <xs:attribute name="url" type="xs:string" />  
                               </xs:complexType>  
                             </xs:element>  
                           </xs:sequence>  
                           <xs:element name="totalSize" type="xs:string" />  
                         </xs:sequence>  
                       </xs:complexType>  
                     </xs:element>  
                   </xs:sequence>  
                 </xs:sequence>  
                 <xs:attribute name="type" type="xs:string" />  
                 <xs:attribute name="url" type="xs:string" />  
               </xs:complexType>  
             </xs:element>  
           </xs:sequence>  
           <xs:element name="totalSize" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   </xs:schema>  
   ```  
  
    架构结构应如下所示：  
  
    ![从 Salesforce 查询响应架构](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")  
  
3. 保存对架构所做的更改。  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a>为 QueryRequest 和 QueryResult 架构创建消息变量  
 在创建 QueryRequest 和 QueryResult 架构后，你必须在业务流程中创建两个消息变量来表示这两种消息类型。  
  
#### <a name="to-create-message-variables"></a>创建消息变量  
  
1.  打开**NotificationService.odx**业务流程，并在业务流程视图中，添加两条新消息。 设置这些消息的名称`QueryRequestMsg`和`QueryResultMsg`。  
  
2.  设置的消息类型**QueryRequestMsg**作为**BtsSalesforceIntegration.QueryRequest**。  
  
3.  设置的消息类型**QueryResultMsg**作为**BtsSalesforceIntegration.QueryResult**。  
  
4.  保存对业务流程所做的更改。  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a>更新业务流程以将消息发送到 Salesforce 并接收响应  
 主题中[步骤 3a： 到 BizTalk Server 接收 Salesforce 机会通知](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)，我们构建了从 Salesforce 接收机会通知并发送确认的业务流程。 在此步骤中，我们将在此业务流程的基础上构建，以将查询请求发送到 Salesforce 来获得与机会相关的产品详细信息并接收响应。 我们已创建了将在此步骤中使用的架构（QueryRequest.xsd 和 QueryResult.xsd）和消息变量（QueryRequestMsg 和 QueryResultMsg）。  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a>向 Salesforce 发送查询请求和接收响应  
  
1. 添加构造消息形状后的**SendNotificationAck**形状。 设置该形状的名称`ConstructQuery`并设置**构造的消息**属性设置为**QueryRequestMsg**。  
  
2. 内**ConstructQuery**形状中，添加**转换**形状。 双击“转换”形状以打开“转换配置”对话框。 在对话框中，选择**现有的映射**选项，然后再从下拉列表中选择**BtsSalesforceIntegration.Notification_QueryRequest**。 设置**源**到**NotificaitonMessage**，**目标**到**QueryRequestMsg**，然后单击**确定**.  
  
3. 内**ConstructQuery**形状之后转换形状中，, 添加消息赋值形状。 双击“消息赋值”形状并添加以下表达式：  
  
   ```  
   QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
   ```  
  
    通过执行此操作，我们传递的值**查询**中的元素**QueryRequestMsg**架构已升级元素**查询**属性架构中。 配置 WCF-WebHttp 端口时，我们将使用此元素将查询值动态传递到请求消息。  
  
4. 之后**ConstructQuery**形状中，添加发送形状。 该形状命名`SendQueryRequest`并将作为消息类型设置**QueryRequestMsg**。  
  
5. 发送形状后添加接收形状并将其命名`ReceiveQueryResult`。 设置该形状的消息类型**QueryResultMsg**。  
  
6. 添加端口以向 Salesforce 发送查询请求，并接收作为响应的查询结果。 在“端口配置”向导中，选择以下选项：  
  
   - 将端口名称指定为`SalesforceRESTInterface`。  
  
   - 选择用于创建新的端口类型的选项。  
  
   - 设置**通信模式**到*请求-响应*。  
  
   - 设置**端口通信方向**到*我将发送请求并接收响应*并设置**端口绑定**到*指定更高版本*.  
  
     连接**请求**端口到发送形状的操作 (*SendQueryRequest*) 和**响应**该端口与接收形状的操作 (*ReceiveQueryResult*)。 下面的屏幕快照描述了业务流程的一部分，它表示向 Salesforce 发送查询请求并接收响应的流程。  
  
     ![将查询发送到 Salesforce 并接收响应](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")  
  
   在本主题中，我们更新了业务流程以向 Salesforce 发送查询请求，并接收与 Salesforce 中创建的机会有关的详细信息（如产品、数量等）。 在随后的主题中，我们将更新此解决方案，以将 Salesforce 响应输入到本地的 SQL Server 数据库。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：在 Visual Studio 中创建 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)