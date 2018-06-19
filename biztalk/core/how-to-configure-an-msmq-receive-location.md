---
title: 如何配置 MSMQ 接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- receive locations, MSMQ adapters
- configuring [MSMQ adapters], receive locations
ms.assetid: ba25cf43-18f1-4c19-84fb-74c7b82b95a9
caps.latest.revision: 43
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 795b72318054525485a64c9dd704b81ddf6cb6b9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008246"
---
# <a name="how-to-configure-an-msmq-receive-location"></a>如何配置 MSMQ 接收位置
您可以在 BizTalk Server 管理控制台中设置 MSMQ 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
> [!IMPORTANT]
>  如果主机实例与 MSMQ 发送端口或接收位置相关联，则请验证该 MSMQ 服务正在该计算机上运行。 如果该服务未运行，则 MSMQ 接收端口在启动后将随即关闭，并将发送到 MSMQ 发送端口的消息挂起。  
>   
>  在群集方案中，不仅需要运行群集 MSMQ 实例，还应在每个群集计算机上运行本地 MSMQ 服务。  
  
## <a name="to-configure-variables-for-an-msmq-receive-location"></a>配置 MSMQ 接收位置的变量  
 请按照下列步骤为 MSMQ 接收位置配置变量：  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要创建中的接收位置的应用程序。  
  
2.  在 BizTalk Server 管理控制台中，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**MSMQ**从下拉列表中，然后单击**配置**。  
  
5.  在**MSMQ 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|日期类型|默认值|  
    |--------------|----------------|---------------|-------------------|  
    |**密码**|设置用于远程队列的密码。|字符串|空白|  
    |**用户名**|确定与密码结合使用以访问远程队列的用户名。 不能使用远程计算机的本地用户作为该用户名。|字符串|空白|  
    |**批大小**|配置批大小。 MSMQ 适配器将消息分批提交给 MessageBox 数据库。 默认的批大小为 20，最小批大小为 1。 **注意：** 如果**事务**接收位置的属性设置为**True**; 每个消息批提交到 MessageBox 数据库的 Microsoft 分布式上下文事务处理协调器 (MSDTC) 事务。 为消息批创建的 MSDTC 事务将始终处于打开状态，直到该批中的所有消息都已保存到 MessageBox 数据库并已放置到相应的订户队列中为止。 因此此 MSDTC 事务的持续时间增加作为**批大小**增加参数。 因为同时具有大量的 MSDTC 事务打开可以对总体性能带来负面影响**批大小**参数不应设置为非常大的值如果启用事务支持。|int|20|  
    |**失败**|指定适配器响应错误的方式。 将此属性设置为以下值之一：<br /><br /> -   **停止。** 如果发生错误，则停止通过此接收位置接收消息。<br />-   **Suspend(non-resumable)。** 挂起消息并将其标记为不可恢复。<br />-   **Suspend(resumable)。** 挂起消息并将其标记为可恢复。 **重要说明：** 如果**True**选项**排序处理**属性，**停止**选项**上失败**属性，与**False**选项**事务**属性应用于同一时间，则不会挂起或留在源队列传递失败的任何消息。 在此方案中，会发生消息丢失。 若要防止数据丢失，当使用**排序处理**功能，**停止**选项**上失败**应该只应用属性，如果**True**选项**事务**应用属性。 然后，在消息送达失败时，原始消息将会保留在源 MSMQ 队列中。 如果**排序处理**属性设置为值为**False**则**上失败**属性将不会影响，如果消息传递失败仍然出现该消息将状态为挂起**已挂起 （恢复）**。|字符串|已挂起(可恢复)|  
    |**有序的处理**|将此属性设置为**True**或**False**。 这表示是否按顺序处理消息。 将属性设置为**True**将容纳有序的消息传递时与具有 BizTalk 消息传递或业务流程发送端口结合使用**按序送达**选项设置为**True**。 有关详细信息请参阅[有序的消息的传递](../core/ordered-delivery-of-messages.md)。<br /><br /> 此属性设置为**True**还通过进行单线程的适配器处理大消息时可以优化资源使用情况。 有关详细信息，请参阅[发送和接收使用 MSMQ 适配器的大型消息](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)。|Boolean|False|  
    |**队列**|键入有效的队列路径。 根据指定的队列路径，系统将执行相应的验证。 **注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。 **注意：** MSMQ 接收适配器使用轮询机制来监视每个 0.5 秒的新消息的指定的 MSMQ 队列。 此 0.5 秒间隔为固定间隔。|字符串|空白|  
    |**事务性**|将此属性设置为**True**或**False**。 **注意：** 的适配器支持的与消息队列 4.0 或更高版本的远程队列事务性读取。 在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。 <br /><br /> 有关详细信息，请参阅[配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)和[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|Boolean|False|  
  
    > [!NOTE]
    >  **用户名**和**密码**仅适用于 Windows 帐户用于访问远程队列。  
  
6.  单击 **“确定”**。  
  
7.  在**接收位置属性**对话框框中，输入适当的值来完成接收位置的配置，然后单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)