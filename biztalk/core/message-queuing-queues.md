---
title: 消息队列队列 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2f5c2d4861a59ded7c19da84d0ca0e6ded9ddfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394562"
---
# <a name="message-queuing-queues"></a>消息队列队列
本部分介绍如何使用 MSMQ 适配器时指定 Microsoft 消息队列 (也称为 MSMQ) 队列。 它介绍了指定的路径的约定，并且还描述了格式中将路径翻译成队列指定名称发挥作用的角色。  
  
## <a name="queue-path-naming-conventions"></a>队列路径命名约定  
 如果队列名称引用一个路径，使用下表中的命名约定。  
  
|**队列类型**|**路径语法**|  
|--------------------|-------------------------|  
|公用队列|*Computername*\QueueName|  
|专用队列|*Computername*\Private$\QueueName|  
|日记队列|*Computername*\QueueName\Journal$|  
|计算机日志队列**注意：** 用于仅接收队列。|*Computername*\Journal$|  
|计算机死信队列**注意：** 用于仅接收队列。|*Computername*\Deadletter$|  
|计算机事务死信队列**注意：** 用于仅接收队列。|*Computername*\XactDeadletter$|  
  
> [!NOTE]
>  队列路径必须是唯一的。  
  
 如果队列名称引用格式名称，它将指示队列是否为公用或专用，根据需要和生成 GUID 对队列和其他标识符以字符串的形式。 下表中使用的命名约定。  
  
|**格式类型**|**格式名称的语法**|  
|---------------------|--------------------------------|  
|公共|*FormatName*:Public=QueueGUID|  
|直接|*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName<br /><br /> *格式名称*:DIRECT=TCP:IPAddress\QueueName<br /><br /> *格式名称*:DIRECT=OS:ComputerName\QueueName|  
  
 如果发送端口队列路径是通讯组列表，该队列路径语法是：  
  
 DL=DistributionListGUID  
  
 如果发送或接收队列路径是 HTTP 或 HTTPS URL，则语法为：  
  
 格式 = http: / /\<客户端名称\>/msmq/\<队列名称\>  
  
 格式 = https: / /\<客户端名称\>/msmq/\<队列名称\>  
  
> [!NOTE]
>  "msmq"是消息队列创建 Internet 信息服务 (IIS) 中的虚拟文件夹。  
  
> [!NOTE]
>  您只能使用 HTTP 发送消息。 如果使用 HTTP 直接格式名称打开队列，无法读取远程计算机上的队列中的消息。 但是，您仍可以通过使用专用或公用队列的路径不使用 HTTP SOAP （格式化） 消息接收从远程队列。  
  
 如果队列名称引用的描述性文本标签，为队列指定的管理员，则引用此标签的队列路径的语法是：  
  
 LABEL:MyQueue  
  
> [!NOTE]
>  标签并不总是唯一。 因此，如果存在名称冲突，当你尝试使用其标签连接到特定的队列时将收到错误。  
  
> [!NOTE]
>  标签是适配器的必需的传输字段。  
  
## <a name="role-of-the-format-name"></a>格式名称的角色  
 消息队列使用格式名称来标识队列并确定如何对其进行访问。 消息队列到队列分配格式名称。  
  
 当指定队列使用的路径名称语法时，例如 myMachine\myQueue，消息队列会查找用于查找关联的格式名称的路径。 然后，消息队列使用该格式名称来访问队列。 当指定的格式名称时，消息队列使用你使用的格式名称。  
  
 有关格式名称的详细信息，请参阅.NET Framework 类库帮助中的"MessageQueue.FormatName 属性"。  
  
## <a name="troubleshooting-queue-paths"></a>队列路径疑难解答  
  
-   如果提供的队列路径的语法与在"队列路径命名约定。"的前面部分中所述的格式之一都不匹配，会发生异常  
  
-   以下不是有效字符中的队列路径的计算机名称：  
  
     \ ; , + "  
  
     如果计算机名称是一个数字，则会发生异常。 例如：234\private$ \queue。  
  
-   计算机死信队列、 计算机日志队列以及计算机事务死信队列，如果用户指定系统队列之一发送的目标队列，会发生异常。  
  
-   **System.Messaging.MessageQueue.Exists**不适用于远程队列。 有关详细信息，请参阅.NET Framework 类库帮助中的"MessageQueue.Exists 方法"。  
  
## <a name="see-also"></a>请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)