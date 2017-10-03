---
title: "进程之间的消息的身份验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c54fb463353ed6551dcbf5764fae05e63fdb778
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="authentication-of-messages-between-processes"></a>进程之间的消息的身份验证
下图显示了 BizTalk Server 中可用于在不同 BizTalk 主机之间验证消息的安全功能。  
  
 ![对消息进行身份验证的安全功能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")  
BizTalk Server 用于在进程之间验证消息的安全功能。  
  
 BizTalk Server 收到某个消息，对它进行解密和验证，然后使用有效的参与方 ID (PID) 和证书确定该消息的发件人后，MessageBox 数据库可以验证与该消息匹配的订阅，接着将消息发送到另一个主机进一步进行处理。  
  
 在消息从一个进程传递到另一个进程时，通常需要将消息原始发件人的标识传递到处理授权、参与方解析以及与发件人相关的业务逻辑的下游进程。 但是，若要在未采取某种安全措施或信任机制的情况下在所有主机中传递此信息，将极大地增加对检验所有用户对象和代码（如业务流程、适配器、管道组件和 functoid）是否可信的需求。  
  
 为了区分用户对象和代码的信任级别的方法，BizTalk Server 提供“受信任验证”作为主机的一个属性。 如果 MessageBox 数据库收到未设置为受信任验证的主机发来的消息，则 MessageBox 数据库将使用来宾 ID 覆盖 PID，并使用运行该主机实例的服务帐户覆盖 SSID。 当主机被标记为受信任验证时，BizTalk 允许该主机在排队进入 MessageBox 数据库的消息上指定任何发件人 SID (SSID) 和参与方 ID (PID)。  
  
 通过指定哪些主机可信哪些主机不可信，可以定义衡量用户对象和代码可信或不可信的安全边界。 即，部署到已设置为“受信任验证”主机中的用户对象和代码需要比部署到未设置为“受信任验证”主机中的用户对象和代码更加可靠。 有关如何配置身份验证信任的主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
 在 MessageBox 数据库接收消息时，BizTalk Server 将采取以下步骤强制对将该消息发送到 MessageBox 数据库的主机实例进行受信任验证：  
  
1.  MessageBox 数据库首先检查 SSID 是否是受信任主机的主机实例服务帐户的 SSID，确定发送消息的主机是否已设置为受信任验证。  
  
2.  如果向 MessageBox 数据库发送消息的主机已设置为受信任验证，则 MessageBox 数据库会将 SSID 和 PID 原样留在消息上下文中，除非消息上下文中的 SID 和 PID 为空。 如果 SSID 为空，则 MessageBox 数据库会使用调用进程的 SID（也称为主机 SID (HSID)）填充它。 如果 PID 为空，MessageBox 数据库会将其设为来宾 ID。  
  
3.  如果向 MessageBox 数据库发送消息的主机未设置为受信任验证，则 SSID 将被 HSID 取代，PID 将被设为“来宾”，而不论这些字段是否已有值。  
  
> [!IMPORTANT]
>  如果要让下游进程知道消息原始发件人的 SSID 和 PID，必须将传递消息的所有主机都设为受信任验证。 此外，如果在某个业务流程中接收的消息随即用于构建出站消息，则在入站消息中接收的 SSID 和 PID 必须作为一个属性显式添加到出站消息，才能继续传递这些标识。  
  
> [!IMPORTANT]
>  如果将运行管道的主机配置为受信任验证，则 BizTalk Server 会认为该管道是受信任环境。 因此，请一定要检验受信任验证主机上运行的 BizTalk 管道中包含的所有自定义组件是否也是受信任的。  
  
> [!NOTE]
>  不能将一个服务帐户同时用于受信任验证主机和不受信任验证主机。  
  
## <a name="see-also"></a>另请参阅  
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [授权一条消息的接收方](../core/authorizing-the-receiver-of-a-message.md)