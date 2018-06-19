---
title: 配置发件人消息跟踪 (NRR) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1785a5502bc1adb9cc8b9aa7f85b6a4473d21c5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233573"
---
# <a name="configuring-sender-message-tracking-nrr"></a>配置发送方消息跟踪（NRR）
作为此页上的一部分设置，您可以指定是否将出站消息及其确认 (MDN) 存储到不可否认数据库中。 有关详细信息，请参阅[AS2 处理在 BizTalk Server](../core/as2-processing-in-biztalk-server.md)。  
  
 若要将消息存储在不可否认数据库中，您必须启用 NRR（接收的不可否认性）作为 AS2 协议属性的一部分。 NRR 可确保发送方已验证消息收件人的签名回执。 从理论上讲，NRR 是消息发件人证明消息以未改变的状态到达目的地的不可否认的证据。 仅在数字签名了原始消息和回执时，才能建立 NRR。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a>若要配置的出站 AS2 消息的消息跟踪和入站的 MDN  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**发件人消息跟踪 (NRR)**。  
  
    > [!NOTE]
    >  要保障接收的不可否认性，必须对消息进行验证和确保消息的完整性。 实现此目的的推荐方法是对消息使用数字签名。 因此，如果你选择任何要在不可否认性数据库中存储消息的属性，你应该对消息进行签名通过选择**应对消息进行签名**属性**验证**页。  
  
3.  选择**为出站的已编码 AS2 消息启用 NRR**将出站的已编码的 AS2 消息存储在不可否认性数据库。  
  
4.  选择**为出站的已解码 AS2 消息启用 NRR**将出站的已解码的 AS2 消息存储在不可否认性数据库。  
  
5.  选择**为入站的 MDN 启用 NRR**将入站的 MDN 存储在不可否认性数据库。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)