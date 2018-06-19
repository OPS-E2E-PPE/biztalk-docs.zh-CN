---
title: 如何配置 MQSeries 适配器接收位置和发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, receive ports
- receive ports, MQSeries adapters
- MQSeries adapters, send ports
- configuring [MQSeries adapters], send ports
- configuring [MQSeries adapters], receive ports
- send ports, MQSeries adapters
- configuring [MQSeries adapters], receive locations
- MQSeries adapters, receive locations
- receive locations, MQSeries adapters
ms.assetid: 552aacde-9ec0-4459-b369-073676b6f926
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c31a15615d74a2ca1471559aa25772725821889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250509"
---
# <a name="how-to-configure-mqseries-adapter-receive-locations-and-send-ports"></a>如何配置 MQSeries 适配器接收位置和发送端口
对接收位置和发送端口均可配置 MQSeries 适配器。  
  
## <a name="to-configure-receive-locations-and-send-ports"></a>配置接收位置和发送端口  
 **创建接收端口和接收位置：**  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你要在其中创建接收位置的应用程序。  
  
2.  右键单击**接收端口**节点，单击**新建，** 和指向**单向接收端口**。  
  
3.  输入中的相应值**端口属性**对话框。 璝惠**端口属性**对话框中，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**接收端口**节点你创建，然后单击**属性**。  
  
5.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后单击**新建**右窗格中。  
  
6.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**MQSeries**从下拉列表列表，，然后单击**配置**。  
  
7.  在**MQSeries 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**批大小**|确定消息批的最大大小 (KB)。 **注意：** 如果**事务支持**接收位置的属性设置为**是**; 每个消息批提交到 MessageBox 数据库的 Microsoft 上下文分布式的事务处理协调器 (MSDTC) 事务。 为消息批创建的 MSDTC 事务将始终处于打开状态，直到该批中的所有消息都已保存到 MessageBox 数据库并已放置到相应的订户队列中为止。 因此此 MSDTC 事务的持续时间增加作为**最大批处理大小**增加参数。 因为同时具有大量的 MSDTC 事务打开可以对总体性能带来负面影响**最大批处理大小**参数不应设置为非常大的值如果启用事务支持。|  
    |**有序的处理**|将 MQSeries 设置为从 MQSeries 队列接收消息时保持消息的顺序。 **注意：** 为了保持顺序特定队列的消息，只有一个 BizTalk 主机实例可能会从队列接收消息该 MQSeries。 <br /><br /> **默认值：** False|  
    |**队列**|使用中的信息填充**队列定义**对话框。 **注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**事务性**|此适配器将在 BizTalk Server 和 MQSeries 服务器之间开始 Microsoft 分布式事务处理协调器 (DTC) 事务。 当设置为**否**，就不能保证的消息传递。<br /><br /> **默认值：** False|  
  
8.  在**MQSeries 传输属性**对话框中，单击**确定**来填充**地址 (URI)** 框中**接收位置属性**对话框。  
  
9. 在**接收位置属性**对话框框中，输入适当的值来完成接收位置的配置，然后单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
 **若要创建发送端口：**  
  
1.  在 BizTalk Server 管理控制台中，创建一个新的静态发送端口。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)有关详细信息。 配置所有发送端口选项并指定**MQSeries**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮旁边**类型**。  
  
3.  在**MQSeries 传输属性**对话框框中，执行以下操作：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**碎片大小**|设置在适配器和 MQSAgent 之间发送消息时消息块的大小（KB）|  
    |**SSO 关联应用程序**|设置单一登录 (SSO) 关联应用程序。 用于的用户 ID 和密码 SSO **MQMD_UserIdentifier**，和**MQIIH_Authenticator** (或**MQCIH_Authenticator**) 属性分别。<br /><br /> **默认值：** 空白|  
    |**数据转换**|将消息转换为用于 Windows Server 的 MQSeries 的 ANSI 代码页。<br /><br /> 选择**是**来执行从 Unicode 此转换为 ANSI。<br /><br /> **默认值：** 否|  
    |**排序**|将 MQSeries 设置为向 MQSeries 队列发送消息时保持消息的顺序。<br /><br /> 选择**是**维护消息顺序。 **注意：** 必须设置**传递通知**到业务流程中的属性**传输**发送端口。 <br /><br /> **默认值：** 否|  
    |**队列定义**|使用中的信息填充**队列定义**对话框中或直接在该字段。 **注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**允许的分段**|如果单个消息超出了 MQSeries 队列的最大消息长度，则使用 MQSeries 队列管理器分段功能。 如果你选择**是**，MQSeries 将分段的消息放入队列。<br /><br /> **默认值：** 否|  
    |**事务支持**|适配器在 BizTalk Server 和 MQSeries 服务器之间执行 DTC 事务。 当设置为**否**，就不能保证的消息传递。<br /><br /> **默认值：** 是**注意：** 没有配置发送端口和不同**事务支持**设置将消息发送到同一个 MQSeries 队列。 **注意：** 除了测试方案中，此属性应始终设置为默认值的**是**。 此属性设置为值为**否**在生产环境可能会导致意外的问题。|  
  
     下图显示了这些属性的可能配置：  
  
     ![MQSeries 传输属性对话框中](../core/media/bts-dev-mqsendtransportprops.gif "BTS_Dev_MQSendTransportProps")  
  
4.  单击省略号 (**...**) 的右侧的按钮**队列定义**框可定义队列。 你可以使用**导出**对话框中，您可能必须与接收位置，以立即创建队列，或将导出定义队列的脚本时相同。  
  
5.  单击**确定**在每个对话框框中，以将其关闭并保存设置。  
  
 **若要登记发送端口，启动发送端口，并启用接收位置：**  
  
1.  右键单击发送端口，然后单击**Enlist**登记发送端口。  
  
2.  右键单击发送端口，然后单击**启动**启动发送端口。  
  
3.  右键单击接收位置，然后单击**启用**以便接收位置。  
  
4.  检查事件日志以确定是否存在 BizTalk Server 错误。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)