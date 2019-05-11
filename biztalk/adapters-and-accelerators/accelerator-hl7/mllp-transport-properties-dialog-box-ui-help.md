---
title: MLLP 传输属性对话框用户界面帮助 |Microsoft Docs
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
ms.openlocfilehash: 167591fe9820d4e416cdb1f931b8dbf4fc302ea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290382"
---
# <a name="mllp-transport-properties-dialog-box-ui-help"></a>MLLP 传输属性对话框用户界面帮助
您使用**MLLP 传输属性**对话框可配置参数发送和接收最少的较低层协议 (MLLP) 适配器。 您可以设置网络连接参数 MLLP 传输属性中为发送端口或接收位置使用 MLLP 传输类型。  

 MLLP 属性的详细信息，请参阅[发送和接收适配器的配置参数](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)。  

## <a name="uielement-list"></a>UIElement 列表  
 在中**MLLP 传输属性**对话框框中，执行以下操作：  

#### <a name="block-characters"></a>禁止字符  
 块字符参数是必须将接收或通过 MLLP 适配器发送的 HL7 消息的特殊字符。 这些字符会形成一个块采用以下格式：\<SB\>*DDD*\<EB\>\<CR\>，其中*DDD*消息数据，代表\<SB\>是开始块字符\<EB\>是结束块字符，并且\<CR\>回车符。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|**\<CR\>回车符**|使用回车符 （第二个字节包装后的最终字节） 的字节值 （以十六进制格式）。 可选。|  
|**\<EB\>结束块字符**|用于结束字节 （消息尾部包装器） 的字节值。 ASCII \<FS\>，例如\<1c\>。|  
|**\<SB\>开始块字符**|用于 （消息标头包装器） 中的开始字节的字节值。 ASCII \<VT\>，例如\<0b\>。|  

#### <a name="deliverymode"></a>DeliveryMode  
 是否在序列中，或未按顺序 （按顺序，不按顺序） 传递实例文件使用控件的交付模式参数。 每个接收位置具有的自己传递，例如序列文件。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|按序的送达|**MLLP 接收**:<br /><br /> 如果您设置**按序送达**属性设置为**FALSE** （默认值），实例文件将不会传递序列中。 将第一次传递推送到队列后较大的实例文件的较小的实例文件。 设置**按序送达**属性设置为**TRUE**、 来传送序列中的实例的文件。|  

#### <a name="network-connection-parameters"></a>网络连接参数  
 使用网络连接参数建立的连接通过网络，包括评论、 连接名称、 主机名、 端口 ID、 接收超时，并发送超时。  


|                使用此选项                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          执行的操作                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              **注释**               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             连接的说明。 可选。                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|           **连接名称**           |                                                                                                                                                                                                                                                                                                                                                                                                                监视连接的名称。 建议的名称保持唯一。 为此连接的性能计数器实例的名称中包含名称。                                                                                                                                                                                                                                                                                                                                                                                                                |
|                **主机**                 |                                                                                                                                                                                                                                                                                                                                         **MLLP 接收**:<br /><br /> 可选。 指定用来侦听传入的连接上的本地接口。 通过默认侦听所有本地接口。<br /><br /> **MLLP 发送**:<br /><br /> 指定 NetBIOS 名称或你想要连接的业务线 (LOB) 计算机的 IP 地址。                                                                                                                                                                                                                                                                                                                                         |
|        **持久连接**        | **MLLP 接收**:<br /><br /> 设置**持续性连接**属性设置为**FALSE** （默认值），以连接空闲超时时间后关闭连接。 设置**持续性连接**属性设置为**True**，使连接保持打开状态。<br /><br /> **MLLP 发送**:<br /><br /> 设置**持续性连接**属性设置为**FALSE**以关闭该连接，如果在超时期间内收到响应或超时时间到期。 设置**持续性连接**属性设置为**True** （默认值），使连接保持打开状态。<br /><br /> 请参阅[持续性连接和接收超时值](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#persistentConnectionAndReceiveTimeout)，并[端口类型和连接状态](../../adapters-and-accelerators/accelerator-hl7/mllp-transport-properties-dialog-box-ui-help.md#portTypeConnectionStatus)有关详细信息。 |
|                **端口**                 |                                                                                                                                                                                                                                                                                                                                                                                                                         **MLLP 接收**:<br /><br /> 若要在其上侦听的本地端口 ID。<br /><br /> **MLLP 发送**:<br /><br /> 你想要连接的远程端口 ID。                                                                                                                                                                                                                                                                                                                                                                                                                         |
|            **发送超时**             |                                                                                                                                                                                                                                                                    **MLLP 发送**:<br /><br /> 发送适配器发送一条消息时将等待的最长时间之后发送的套接字将超时。到期后，BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将重试消息。<br /><br /> 此外，对于同步操作的发送端口，用于从 LOB 接收确认 (ACK) 的最长时间。                                                                                                                                                                                                                                                                    |
|           **接收超时**           |                                                                                                                                                                                                                                                                                 **MLLP 接收**:<br /><br /> 接收适配器接收的消息时将等待的最长时间后接收套接字将超时。到期后，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将关闭连接。<br /><br /> 此外，对于同步操作的接收位置，用于将确认发送到 LOB 的最长时间。                                                                                                                                                                                                                                                                                 |
|      **要求响应已启用**       |                                                                                                                                                                                                                                                                                                                                                                                                                                                     **MLLP 发送**:<br /><br /> 是/否。 同一 TCP 连接上接收 Ack 的启用。                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **提交接收位置的 URI，用于确认** |                                                                                                                                                                                                                                                                                                                                                                                                                 **MLLP 发送**:<br /><br /> 在其下确认收到同一个 TCP 连接的接收位置的 URI 会传送给 MessageBox 数据库。                                                                                                                                                                                                                                                                                                                                                                                                                 |

#####  <a name="persistentConnectionAndReceiveTimeout"></a> 持续性连接和接收超时值  
 有关**MLLP 接收**下, 表显示了有关可能的值的结果**持续性连接**并**接收超时**值。  

|**持久连接**|**接收超时**|结果|  
|-------------------------------|-------------------------|------------|  
|**FALSE**|>0|在连接关闭后收到一条消息或超时时间到期。|  
|**FALSE**|0|导致错误条件："接收超时值不应为 FALSE 的持久连接的情况下为零。"|  
|**TRUE**|0|连接永远不会中断。|  
|**TRUE**|<>0|导致错误条件："接收超时值应为 TRUE 的持久连接的情况下的零。"|  

 有关**MLLP 发送**下, 表显示了有关可能的值的结果**持续性连接**并**接收超时**值。  

|**持久连接**|**发送超时**|结果|  
|-------------------------------|----------------------|------------|  
|**FALSE**|0 或 > 0|在连接关闭后收到的响应或超时时间到期。|  
|**TRUE**|0 或 & lt;>0|连接永远不会中断。 **发送超时**值不会影响连接状态。|  

#####  <a name="portTypeConnectionStatus"></a> 端口类型和连接状态  
 下表显示不同的发送端口的连接状态类型，当持久性连接的设置和要求响应更改。  

|发送端口类型|持久连接|要求响应|连接状态|  
|--------------------|---------------------------|----------------------|-----------------------|  
|静态单向|TRUE|否|保持打开状态|  
|静态单向|TRUE|是|保持打开状态|  
|静态单向|FALSE|否|已关闭|  
|静态单向|FALSE|是|已关闭|  
|静态要求响应|FALSE|是|保持打开状态|  
|静态要求响应|TRUE|是|保持打开状态|  
|静态要求响应|FALSE|否|已关闭|  
|静态要求响应|FALSE|是|已关闭|  

## <a name="see-also"></a>请参阅  
 [处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [设置用于接收 ACK 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)