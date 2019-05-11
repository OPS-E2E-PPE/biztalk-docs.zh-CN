---
title: 创建 BizTalk Server 业务流程 |Microsoft Docs
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
ms.openlocfilehash: 5ae4a8b8f2c70143d1b9969bdcd7537911a99cc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390155"
---
# <a name="create-a-biztalk-server-orchestration"></a>创建 BizTalk Server 业务流程
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程，在部署时，接收 JSON 采购订单消息、 将其转换为 XML 发票，然后发送 JSON 发票。  
  
## <a name="define-message-and-message-types"></a>定义消息和消息类型  
 此解决方案结合使用两个基本消息 – 采购订单和发票。 我们已从使用 JSON 架构向导的 JSON 消息生成采购订单的架构。 提供有关本教程中已具有发票消息的架构的示例。 我们使用这些架构来创建中的消息类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
1.  将业务流程添加到 BizTalk 项目并打开业务流程视图。  
  
2.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
3.  右键单击新创建的消息，然后依次**属性窗口**。  
  
4.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `PurchaseOrder`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BTSJSON。采购订单*，其中*BTSJSON*是 BizTalk 项目的名称。|  
  
5.  重复上述步骤创建新的发票消息的消息类型。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `InvoiceMsg`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*BTSJSON。发票*。|  
  
## <a name="set-up-the-orchestration"></a>设置业务流程  
 在此步骤中，添加消息形状和端口，创建一个业务流程。  
  
### <a name="add-message-shapes"></a>添加消息形状  
 从解决方案资源管理器中打开业务流程文件并添加以下消息形状。  
  
-   添加接收形状，将其名称设置为**ReceivePO**，和消息类型设置为**PurchaseOrder**。  
  
-   添加发送形状，将其名称设置为**SendInvoice**，和消息类型设置为**InvoiceMsg**。  
  
-   添加构造消息形状，并设置**构造的消息**向构造消息形状的属性**InvoiceMsg**。  
  
-   添加转换形状中构造消息形状。 双击转换形状并在**转换配置**对话框中，选择**现有映射**选项，并选择**BTSJSON。POToInvoice**映射。 此映射作为示例的一部分提供。 在对话框中，将**源**到**PurchaseOrder**并设置**目标**到**InvoiceMsg**。 单击“确定” 。  
  
### <a name="add-ports"></a>添加端口  
 将两个端口添加到业务流程 – 一个用于接收消息，一个用于发送消息。 使用以下属性的端口。  
  
|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*ReceiveJSONPO*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|ResponseOut|-设置**标识符**到*SendJSONInvoice*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*|  
  
 下面的屏幕截图中所示连接端口和消息形状，并将更改保存到项目。  
  
 ![处理 JSON 消息的业务流程](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)