---
title: 如何配置 MSMQ 接收位置 |Microsoft Docs
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
ms.openlocfilehash: 1c6fcccda5b338df469baf740a118bded4b160f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341726"
---
# <a name="how-to-configure-an-msmq-receive-location"></a>如何配置 MSMQ 接收位置
您可以设置 MSMQ BizTalk Server 管理控制台中的接收位置适配器变量。 如果属性未设置接收位置中，使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，必须已添加接收端口。 有关详细信息请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
> [!IMPORTANT]
>  如果主机实例与 MSMQ 发送端口或接收位置，验证该计算机上运行 MSMQ 服务。 如果该服务未运行，则 MSMQ 接收端口将关闭，不久后启动，并发送到 MSMQ 消息发送端口将被挂起。  
>   
>  在群集方案中，不仅群集的 MSMQ 实例需要处于运行状态，但每个群集计算机上的本地 MSMQ 服务应在运行，以及。  
  
## <a name="to-configure-variables-for-an-msmq-receive-location"></a>若要配置 msmq 接收位置的变量  
 请执行以下步骤为 MSMQ 接收位置配置变量：  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要在其中创建接收位置的应用程序。  
  
2.  在 BizTalk Server 管理控制台中，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在中**接收端口属性**对话框中，在左窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**以创建新的接收位置。  
  
4.  在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**MSMQ**从下拉列表中，然后单击**配置**。  
  
5.  在中**MSMQ 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|日期类型|默认值|  
    |--------------|----------------|---------------|-------------------|  
    |**密码**|设置要使用远程队列的密码。|String|空白|  
    |**用户名**|确定要使用，与密码结合使用的远程队列的访问权限的用户名称。 您不能使用远程计算机的本地用户的用户名。|String|空白|  
    |**批大小**|配置批大小。 MSMQ 适配器将消息提交给 MessageBox 数据库中的批处理。 默认批大小为 20，并最小批大小为 1。 **注意：** 如果**事务性**接收位置属性设置为**True**; 每个消息批次提交到 MessageBox 数据库的 Microsoft 分布式事务处理协调器上下文(MSDTC) 事务。 为消息批处理创建的 MSDTC 事务保持打开状态，直到保存到 MessageBox 在批处理中每个消息并将其放在适当的订阅服务器队列中。 因此 MSDTC 事务的持续时间增加作为**批大小**参数增加。 由于同时拥有大量的 MSDTC 事务打开可以对总体性能带来负面影响**批大小**参数不应设置为非常大的值时启用事务支持。|smallint|20|  
    |**在失败**|指定适配器应如何响应错误。 将此属性设置为以下值之一：<br /><br /> -   **停止。** 如果出现错误条件，则停止接收消息，通过此接收位置。<br />-   **Suspend(non-resumable)。** 挂起消息并将标记为不可恢复。<br />-   **Suspend(resumable)。** 挂起消息并将标记为可恢复。 **重要提示：** 如果 **，则返回 True**选项**按序处理**属性，**停止**选项**失败**属性，并**False**选项**事务性**属性应用于在同一时间，则不会挂起或保留在源队列传递失败的任何消息。 在此方案中，会发生消息丢失。 若要防止数据丢失，使用时**按序处理**功能，**停止**选项**失败**应该仅应用属性，如果 **，则返回 True**选项**事务性**应用属性。 然后，如果消息送达失败时，原始消息将保留在源 MSMQ 队列。 如果**按序处理**属性设置为值**False**则**失败**属性将不会生效，并且如果消息送达失败时发生消息将状态为挂起**已挂起 （可恢复）**。|String|Suspend(resumable)|  
    |**按序的处理**|将此属性设置为 **，则返回 True**或**False**。 这指示是否按顺序处理消息。 将属性设置为 **，则返回 True**将容纳按序送达的消息传递中具有的 BizTalk 消息传送或业务流程发送端口一起使用时**按序送达**选项设置为**True**。 有关详细信息请参阅[的消息按序送达](../core/ordered-delivery-of-messages.md)。<br /><br /> 此属性设置为 **，则返回 True**还通过将适配器单线程化处理大消息时可以优化资源使用情况。 有关详细信息，请参阅[发送和接收大型消息使用 MSMQ 适配器](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)。|Boolean|False|  
    |**Queue**|键入有效的队列路径。 具体取决于您指定的队列路径，系统将执行相应的验证。 **注意：** URI 发送端口或接收位置不能超过 256 个字符。 **注意：** MSMQ 接收适配器使用轮询机制来监视每隔 0.5 秒的新消息的指定的 MSMQ 队列。 此 0.5 秒间隔是固定的时间间隔。|String|空白|  
    |**事务性**|将此属性设置为 **，则返回 True**或**False**。 **注意：** 该适配器支持 Message Queuing 4.0 或更高版本的远程队列进行事务性读取。 在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。 <br /><br /> 有关详细信息，请参阅[配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)并[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|Boolean|False|  
  
    > [!NOTE]
    >  **用户名**并**密码**仅适用于 Windows 帐户用于访问远程队列。  
  
6.  单击“确定” 。  
  
7.  在中**接收位置属性**对话框框中，输入适当的值以完成接收位置的配置，然后单击**确定**以保存设置。 有关“接收位置属性”  对话框的信息，请参阅 [如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)