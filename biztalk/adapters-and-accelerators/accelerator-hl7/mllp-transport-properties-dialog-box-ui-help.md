---
title: MLLP 传输属性对话框的 UI 帮助 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.mllp.transportproperties
ms.assetid: 2a41aaeb-a91d-4d89-ac8a-1cfe48ab4cd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9856b7fbbac5dd9d6a4f809e369e586d95a31b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="mllp-transport-properties-dialog-box-ui-help"></a>MLLP 传输属性对话框的 UI 帮助
你使用**MLLP 传输属性**对话框中配置的参数以发送和接收最小较低层协议 (MLLP) 适配器。 你可以设置的网络连接参数 MLLP 传输属性中为发送端口或接收位置使用 MLLP 传输类型。  
  
 有关 MLLP 属性的详细信息，请参阅[发送和接收的适配器的配置参数](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)。  
  
## <a name="uielement-list"></a>UIElement 列表  
 在**MLLP 传输属性**对话框框中，执行以下操作：  
  
#### <a name="block-characters"></a>块字符  
 块字符参数都必须将括 HL7 消息接收或通过 MLLP 适配器发送的特殊字符。 这些字符形成块采用以下格式： \<SB\>*DDD*\<EB\>\<CR\>，其中*DDD*代表消息数据， \<SB\>是开始块字符， \<EB\>是结束块字符，和\<CR\>回车符，将返回。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**\<CR\>回车符**|用于回车符 （第二个字节的包装后的最终字节） 的字节值 （以十六进制格式）。 可选。|  
|**\<EB\>结束块字符**|用于结束字节 （消息预告片包装） 的字节值。 ASCII \<FS\>，例如， \<1 c\>。|  
|**\<SB\>开始块字符**|用于 （消息标头包装） 中的开始字节的字节值。 ASCII \<VT\>，例如， \<0b\>。|  
  
#### <a name="deliverymode"></a>DeliveryMode  
 是否在序列中，或 （按顺序，按顺序） 的顺序不正确传递实例文件，你可以使用控件的传递模式参数。 每个接收位置具有例如序列文件自己传递。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|按序送达|**MLLP 接收**:<br /><br /> 如果你设置**按序送达**属性**FALSE** （默认值），实例文件将不会发送序列中。 将第一次传递推送到队列在较大的实例文件后的较小实例文件。 设置**按序送达**属性**TRUE**、 顺序提供实例文件。|  
  
#### <a name="network-connection-parameters"></a>网络连接参数  
 使用网络连接参数来建立的连接通过网络，包括注释、 连接名称、 主机名、 端口 ID、 接收超时，和发送超时时。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**注释**|连接的说明。 可选。|  
|**连接名称**|监视连接名称。 建议的名称是唯一的。 此连接的性能计数器实例的名称中包含的名称。|  
|**主机**|**MLLP 接收**:<br /><br /> 可选。 指定用于侦听传入连接的本地接口。 通过在所有本地接口上的默认侦听。<br /><br /> **MLLP 发送**:<br /><br /> 指定的 NetBIOS 名称或你想要连接的业务线 (LOB) 计算机的 IP 地址。|  
|**持续性连接**|**MLLP 接收**:<br /><br /> 设置**持续性连接**属性**FALSE** （默认值），连接空闲超时期限后关闭连接。 设置**持续性连接**属性**True**，以使连接保持打开。<br /><br /> **MLLP 发送**:<br /><br /> 设置**持续性连接**属性**FALSE**以关闭连接的超时期限内收到响应或超时时间到期。 设置**持续性连接**属性**True** （默认值），以使连接保持打开。<br /><br /> 请参阅[持续性连接和接收超时值](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#persistentConnectionAndReceiveTimeout)，和[端口类型和连接状态](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#portTypeConnectionStatus)有关详细信息。|  
|**端口**|**MLLP 接收**:<br /><br /> 要侦听的本地端口 ID。<br /><br /> **MLLP 发送**:<br /><br /> 你想要连接的远程端口 ID。|  
|**发送超时时**|**MLLP 发送**:<br /><br /> 发送适配器发送一条消息时所等待的最长时间之后发送的套接字将超时。到期时，BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将重试消息。<br /><br /> 此外，如果同步操作发送端口中，从 LOB 接收确认 (ACK) 的最长时间。|  
|**接收超时**|**MLLP 接收**:<br /><br /> 接收适配器接收一条消息时所等待的最长时间后接收套接字将超时。到期时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将关闭连接。<br /><br /> 此外，如果同步操作的接收位置中，将确认发送到 LOB 的最长时间。|  
|**要求启用的响应**|**MLLP 发送**:<br /><br /> 是/否。 允许同一个 TCP 连接上接收确认。|  
|**提交收到 ACK 位置 URI**|**MLLP 发送**:<br /><br /> 确认接收同一个 TCP 连接接收位置的 URI 将传递到 MessageBox 数据库。|  
  
#####  <a name="persistentConnectionAndReceiveTimeout"></a>持续性连接和接收超时值  
 有关**MLLP 接收**下, 表显示的可能值的结果**持续性连接**和**接收超时**值。  
  
|**持续性连接**|**接收超时**|结果|  
|-------------------------------|-------------------------|------------|  
|**FALSE**|>0|收到一条消息或超时时间到期后，将关闭连接。|  
|**FALSE**|0|导致错误条件:"接收超时值不应持久连接 FALSE 的情况下的零。"|  
|**TRUE**|0|连接永远不会断开。|  
|**TRUE**|<>0|导致错误条件:"接收超时值应为持久连接 TRUE 的情况下的零"。|  
  
 有关**MLLP 发送**下, 表显示的可能值的结果**持续性连接**和**接收超时**值。  
  
|**持续性连接**|**发送超时时**|结果|  
|-------------------------------|----------------------|------------|  
|**FALSE**|0 或 > 0|收到的响应或超时时间到期后，将关闭连接。|  
|**TRUE**|0 或 <> 0|连接永远不会断开。 **发送超时**值不会影响连接状态。|  
  
#####  <a name="portTypeConnectionStatus"></a>端口类型和连接状态  
 下表显示了不同发送端口的连接状态类型时持续性连接的设置和请求作出响应更改。  
  
|发送端口类型|持续型连接|请求作出响应|连接状态|  
|--------------------|---------------------------|----------------------|-----------------------|  
|静态单向|TRUE|是|仍然处于打开状态|  
|静态单向|TRUE|是|仍然处于打开状态|  
|静态单向|FALSE|是|已关闭|  
|静态单向|FALSE|是|已关闭|  
|静态请求作出响应|FALSE|是|仍然处于打开状态|  
|静态请求作出响应|TRUE|是|仍然处于打开状态|  
|静态请求作出响应|FALSE|是|已关闭|  
|静态请求作出响应|FALSE|是|已关闭|  
  
## <a name="see-also"></a>另请参阅  
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [设置用于接收 ACK 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)