---
title: "消息队列的队列 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9156b6d6fa1374f532efb354e5816c054b83994
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-queuing-queues"></a>消息队列的队列
本部分将介绍如何在使用 MSMQ 适配器时指定 Microsoft 消息队列（也称为 MSMQ）。 本部分对指定路径的约定进行了说明，并介绍了格式名称在将路径翻译成队列指定格式的过程中所起的作用。  
  
## <a name="queue-path-naming-conventions"></a>队列路径命名约定  
 如果队列名称引用路径，则将使用下表中的命名约定：  
  
|**队列类型**|**路径的语法**|  
|--------------------|-------------------------|  
|公用队列|*Computername*\QueueName|  
|专用队列|*Computername*\Private$\QueueName|  
|日志队列|*Computername*\QueueName\Journal$|  
|计算机日记队列**注意：**用于仅接收队列。|*Computername*\Journal$|  
|计算机死信队列**注意：**用于仅接收队列。|*Computername*\Deadletter$|  
|计算机事务性死信队列**注意：**用于仅接收队列。|*Computername*\XactDeadletter$|  
  
> [!NOTE]
>  该队列路径必须唯一。  
  
 如果队列名称引用格式名称，则将采用字符串形式，以指示队列是公用队列还是专用队列，并在后面附加生成的队列 GUID 和其他标识符（根据需要）。 请使用下表中的命名约定：  
  
|**格式类型**|**语法对格式名**|  
|---------------------|--------------------------------|  
|公共|*通过 FormatName*： 公共 = QueueGUID|  
|直接|*通过 FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName<br /><br /> *通过 FormatName*: DIRECT = TCP:IPAddress\QueueName<br /><br /> *通过 FormatName*: DIRECT = OS:ComputerName\QueueName|  
  
 如果发送端口队列路径是分发列表，则该队列路径语法为：  
  
 DL=DistributionListGUID  
  
 如果发送或接收队列路径是 HTTP 或 HTTPS URL，则语法为：  
  
 FormatName:DIRECT = http: / /\<客户端名称 > /msmq/\<队列名称 >  
  
 FormatName:DIRECT = https: / /\<客户端名称 > /msmq/\<队列名称 >  
  
> [!NOTE]
>  “msmq”是消息队列在 Internet 信息服务 (IIS) 中创建的虚拟文件夹。  
  
> [!NOTE]
>  您只能使用 HTTP 发送消息。 如果使用 HTTP 直接格式名称打开队列，则将无法读取远程计算机上的队列中的消息。 但是，不使用 HTTP，仍可以通过使用专用或公用队列路径从远程队列接收 SOAP（格式化）消息。  
  
 如果队列名称引用管理员为队列指定的说明性文本标签，则引用此标签的队列路径的语法应为：  
  
 LABEL:MyQueue  
  
> [!NOTE]
>  标签并不总是唯一的。 因此，如果在尝试使用某队列的标签连接到该队列时存在名称冲突，则会收到错误消息。  
  
> [!NOTE]
>  标签是适配器的必需传输字段。  
  
## <a name="role-of-the-format-name"></a>格式名称的作用  
 消息队列使用格式名称来标识队列和确定访问队列的方式。 消息队列可为队列分配格式名称。  
  
 在使用路径名称语法（例如 myMachine\myQueue）指定队列时，消息队列将查找该路径以找到关联的格式名称。 然后，消息队列将使用该格式名称访问相应的队列。 在指定格式名称时，消息队列将使用您所用的格式名称。  
  
 有关格式名称的详细信息，请参阅 .NET Framework 类库帮助中的“MessageQueue.FormatName 属性”。  
  
## <a name="troubleshooting-queue-paths"></a>队列路径疑难解答  
  
-   如果提供的队列路径的语法与先前在“队列路径命名约定”中介绍的某种格式不匹配，则会出现异常。  
  
-   队列路径中的计算机名称不能使用以下字符：  
  
     \ ; , + "  
  
     如果计算机名称为数字，则会出现异常。 例如： 234\private$ \queue。  
  
-   对于计算机死信队列、计算机日志队列以及计算机事务死信队列，如果用户将某个系统队列指定为发送的目标队列，则会出现异常。  
  
-   **System.Messaging.MessageQueue.Exists**并不适用于远程队列。 有关详细信息，请参阅 .NET Framework 类库帮助中的“MessageQueue.Exists 方法”。  
  
## <a name="see-also"></a>另请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)