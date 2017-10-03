---
title: "配置参数发送和接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters
- send adapters
- configuration parameters [adapters]
- receive adapters
ms.assetid: f24ca8ae-feaf-4e5f-b434-76bc3c1c8ccf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c33e49e82f9ebbf8856dd447989d7557558c0e4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-parameters-for-send-and-receive-adapters"></a>配置参数发送和接收适配器
本部分提供的配置参数发送和接收最小较低层协议 (MLLP) 适配器。 这些参数分为两个类： 阻止字符和网络连接参数。  
  
 你设置块字符设置使用 MLLP 传输类型的发送端口的 MLLP 传输属性中。  
  
 你可以设置的网络连接参数 MLLP 传输属性中为发送端口或接收位置使用 MLLP 传输类型。 为此，请打开 BizTalk Server 管理控制台，导航到发送端口或接收位置文件夹 （如果适用）、 右键单击特定发送端口或接收位置，单击**属性**，然后单击**配置**。  
  
## <a name="block-characters"></a>块字符  
 这些参数是特殊字符，必须将接收或通过 MLLP 适配器发送的 HL7 消息括起来。 这些字符形成块采用以下格式： \<SB >*DDD*\<EB >\<CR >，其中*DDD*消息数据，代表\<SB> 是开始块字符， \<EB > 是结束块字符，和\<CR > 回车符，将返回。  
  
|参数|改用|  
|---------------|---------|  
|**\<CR > 回车符**|用于回车符 （第二个字节的包装后的最终字节） 的字节值 （以十六进制格式）。 可选。|  
|**\<EB > 结束块字符**|用于结束字节 （消息预告片包装） 的字节值。 ASCII \<FS >，例如， \<1 c >。|  
|**\<SB > 开始块字符**|用于 （消息标头包装） 中的开始字节的字节值。 ASCII \<VT >，例如， \<0b >。|  
  
## <a name="deliverymode"></a>DeliveryMode  
 是否在序列中，或 （按顺序，按顺序） 的顺序不正确传递实例文件，你可以使用控件的传递模式参数。 每个接收位置具有例如序列文件自己传递。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|按序送达|**MLLP 接收**:<br /><br /> 设置**按序送达**属性**TRUE**，以指定应按照指定的顺序处理消息。 “按序送达”对于合作伙伴业务流程指定的必须作为保护进行处理的消息十分重要。<br /><br /> 如果你设置**按序送达**属性**FALSE** （默认值），该端口不会强制有序的传递。|  
  
## <a name="network-connection-parameters"></a>网络连接参数  
 使用这些参数来建立的连接通过网络，包括注释、 连接名称、 主机名、 端口 ID、 接收超时，和发送超时时。  
  
|参数|改用|  
|---------------|---------|  
|**注释**|连接的说明。 可选。|  
|**连接名称**|监视连接名称。 建议的名称是唯一的。 此连接的性能计数器实例的名称中包含的名称。|  
|**主机**|**MLLP 接收**:<br /><br /> 可选。 指定用于侦听传入连接的本地接口。 通过在所有本地接口上的默认侦听。<br /><br /> **MLLP 发送**:<br /><br /> 指定的 NetBIOS 名称或你想要连接的业务线 (LOB) 计算机的 IP 地址。|  
|**持续性连接**|**MLLP 接收**:<br /><br /> 设置**持续性连接**属性**FALSE** （默认值），连接空闲超时期限后关闭连接。 设置**持续性连接**属性**True**，以使连接保持打开。<br /><br /> 下表显示的可能值的结果**持续性连接**和**接收超时**值。<br /><br /> **FALSE**<br /><br /> - >0<br /><br /> 的收到一条消息或超时时间到期后，将关闭连接。<br /><br /> **FALSE**<br /><br /> - 0<br /><br /> -将导致错误条件:"接收超时值不应持久连接 FALSE 的情况下的零。"<br /><br /> **TRUE**<br /><br /> - 0<br /><br /> -在连接永远不会中断。<br /><br /> **TRUE**<br /><br /> - <>0<br /><br /> -将导致错误条件:"接收超时值应为持久连接 TRUE 的情况下的零"。<br /><br /> **MLLP 发送**:<br /><br /> 设置**持续性连接**属性**FALSE**以关闭连接的超时期限内收到响应或超时时间到期。 设置**持续性连接**属性**True** （默认值），以使连接保持打开。<br /><br /> 下表显示的可能值的结果**持续性连接**和**接收超时**值。<br /><br /> **FALSE**<br /><br /> -O 或 > 0<br /><br /> 的收到的响应或超时时间到期后，将关闭连接。<br /><br /> **TRUE**<br /><br /> -0 或 <> 0<br /><br /> -在连接永远不会中断。 **发送超时**值不会影响连接状态。<br /><br /> 下表显示了不同发送端口的连接状态类型时持续性连接的设置和请求作出响应更改。<br /><br /> 静态单向<br /><br /> -TRUE<br /><br /> -无<br /><br /> -保持打开状态<br /><br /> 静态单向<br /><br /> -TRUE<br /><br /> -是<br /><br /> -保持打开状态<br /><br /> 静态单向<br /><br /> -FALSE<br /><br /> -无<br /><br /> 关闭<br /><br /> 静态单向<br /><br /> -FALSE<br /><br /> -是<br /><br /> 关闭<br /><br /> 静态请求作出响应<br /><br /> -TRUE<br /><br /> -无<br /><br /> -保持打开状态<br /><br /> 静态请求作出响应<br /><br /> -TRUE<br /><br /> -是<br /><br /> -保持打开状态<br /><br /> 静态请求作出响应<br /><br /> -FALSE<br /><br /> -无<br /><br /> 关闭<br /><br /> 静态请求作出响应<br /><br /> -FALSE<br /><br /> -是<br /><br /> 关闭|  
|**端口**|**MLLP 接收**:<br /><br /> 要侦听的本地端口 ID。<br /><br /> **MLLP 发送**:<br /><br /> 你想要连接的远程端口 ID。|  
|**发送超时时**|**MLLP 发送**:<br /><br /> 发送适配器发送一条消息时所等待的最长时间之后发送的套接字将超时。到期时，BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将重试消息。<br /><br /> 此外，如果同步操作发送端口中，从 LOB 接收确认 (ACK) 的最长时间。|  
|**接收超时**|**MLLP 接收**:<br /><br /> 接收适配器接收一条消息时所等待的最长时间后接收套接字将超时。到期时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将关闭连接。<br /><br /> 此外，如果同步操作的接收位置中，将确认发送到 LOB 的最长时间。|  
|**要求启用的响应**|**MLLP 发送**:<br /><br /> 是/否。 允许同一个 TCP 连接上接收确认。|  
|**提交收到 ACK 位置 URI**|**MLLP 发送**:<br /><br /> 确认接收同一个 TCP 连接接收位置的 URI 将传递到 MessageBox 数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)