---
title: 配置端口以接收 EDI 消息，确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c043e648-b7f5-40aa-b7b5-0172fbea7b31
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16d3add143cdac1926b89cf137b5ccfcebe77be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234205"
---
# <a name="configuring-a-port-to-receive-edi-messages-and-acknowledgments"></a>配置接收 EDI 消息和确认的端口
若要接收的 EDI 交换，你可以创建单向接收端口或请求-响应 （双向） 接收端口，以便接收该交换。  
  
-   创建单向接收端口，如果你还将创建一个单向发送端口发送 EDI 确认 （如果启用）。 您还需要清除**路由 ACK 发送管道请求-响应接收端口**协议属性。  
  
-   创建请求响应接收端口和要返回通过关联的 EDI 确认 （如果启用） 发送管道的位置。 你还必须选择**路由 ACK 发送管道请求-响应接收端口**协议属性。  
  
## <a name="creating-a-one-way-receive-port"></a>创建单向接收端口  
 使用以下配置创建的接收端口和位置：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**接收端口属性： 常规**|端口类型|单向|  
|**接收端口属性： 常规**|身份验证|设置为**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**进行身份验证对收到的消息发送方。<br /><br /> 设置为**无身份验证**禁用发送对收到的消息一方的身份验证。<br /><br /> 如果设置为**丢弃的消息，如果身份验证失败**，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将会挂起消息，如果其发件人的身份验证失败。<br /><br /> 如果设置为**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**，消息必须解析为协议。 不允许使用后备协议属性。 如果对于传入消息而言未确定任何协议，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将消息视为验证已失败，并将挂起消息。|  
|**接收位置属性： 常规**|传输类型|可以是任何传输类型。|  
|**接收位置属性： 常规**|接收处理程序|BizTalkServerApplication|  
|**接收位置属性： 常规**|接收管道|EdiReceive|  
|**文件传输属性： 身份验证**|在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）|如果需要验证，则加以设置。|  
|**文件传输属性： 批处理**|批中的消息数|如果批处理的交换，设置。|  
|**文件传输属性： 批处理**|最大批大小(字节)|如果批处理的交换，设置。|  
  
## <a name="creating-a-request-response-receive-port"></a>创建请求-响应接收端口  
 使用以下配置创建的接收端口和位置：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**接收端口属性： 常规**|端口类型|请求响应|  
|**接收端口属性： 常规**|身份验证|设置为**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**进行身份验证对收到的消息发送方。<br /><br /> 设置为**无身份验证**禁用发送对收到的消息一方的身份验证。<br /><br /> **注意：** 如果设置为**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**，消息必须解析为协议。|  
|**接收位置属性： 常规**|传输类型|可以是众多传输类型中的任何一个，FILE 除外，在下拉列表中不提供此类型。<br /><br /> **注意：** 如果创建一个使用 EDIReceive 管道并且具有 HTTP 传输类型的接收位置，可能出现安全问题。 EdiReceive 管道将不生成 HTTP“200 OK”确认。 如果返回没有 EDI 确认，连接将保持打开，直到超时期限已过。|  
|**接收位置属性： 常规**|接收处理程序|BizTalkServerApplication|  
|**接收位置属性： 常规**|接收管道|EdiReceive|  
|**接收位置属性： 常规**|发送管道|EdiSend|  
|**文件传输属性： 身份验证**|在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）|如果需要验证，则加以设置。|  
|**文件传输属性： 批处理**|批中的消息数|如果批处理的交换，设置。|  
|**文件传输属性： 批处理**|最大批大小(字节)|如果批处理的交换，设置。|  
  
## <a name="setting-agreement-properties"></a>设置协议属性  
 创建接收端口和位置后，需要设置接收管道工作所需的协议属性。 各种页中设置这些属性**协议属性**对话框。 有关的 EDI 反汇编程序必须具有到 EdiReceive 中的 EDI 交换接收的进程的属性列表管道，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
## <a name="see-also"></a>另请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)   
 [EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)   
 [如何创建接收端口](../core/how-to-create-a-receive-port.md)