---
title: 创建 BizTalk Server 业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6223ab8d8aa3c8d1c20559a88257dd0dccaa22e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008972"
---
# <a name="create-a-biztalk-server-orchestration"></a>创建 BizTalk Server 业务流程
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 部署时创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程，以接收 JSON 采购订单消息、将其转换成 XML 发票，然后向外发送 JSON 发票。  
  
## <a name="define-message-and-message-types"></a>定义消息和消息类型  
 此解决方案结合使用两个基本消息 – 采购订单和发票。 我们已经使用 JSON 架构向导从 JSON 消息生成采购订单的架构。 为本教程提供的示例已具有发票消息的架构。 我们使用这些架构在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中创建消息类型。  
  
1.  将业务流程添加到 BizTalk 项目中，然后打开业务流程视图。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
4.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`PurchaseOrder`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BTSJSON。PO*，其中*BTSJSON*是 BizTalk 项目的名称。|  
  
5.  重复上一步骤，为发票消息创建一个新消息类型。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`InvoiceMsg`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BTSJSON。发票*。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 在此步骤中，您将添加消息形状和端口，创建一个业务流程。  
  
### <a name="add-message-shapes"></a>添加消息形状  
 从解决方案资源管理器打开业务流程文件，然后添加以下消息形状。  
  
-   添加接收图形，请将其名称设置为**ReceivePO**，和消息类型设置为**PurchaseOrder**。  
  
-   添加发送图形，请将其名称设置为**SendInvoice**，和消息类型设置为**InvoiceMsg**。  
  
-   添加构造消息形状，并设置**消息构造**属性构造消息形状上与**InvoiceMsg**。  
  
-   在“构造消息”形状内添加“转换”形状。 双击转换形状并在**转换配置**对话框中，选择**现有映射**选项，然后再选中**BTSJSON。POToInvoice**映射。 此映射是作为示例的一部分提供的。 在对话框中，设置**源**到**PurchaseOrder**并设置**目标**到**InvoiceMsg**。 单击 **“确定”**。  
  
### <a name="add-ports"></a>添加端口  
 向业务流程添加两个端口 – 一个用于接收消息，一个用于发送消息。 针对端口使用以下属性。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*ReceiveJSONPO*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|ResponseOut|-将设置**标识符**到*SendJSONInvoice*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
 按照下面的屏幕快照所示连接端口和消息形状，然后将更改保存至项目。  
  
 ![业务流程来处理 JSON 消息](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)