---
title: "配置接收方邮件跟踪 (NRR) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a9c62e69f9f39bf445f0b3028a4e6707f48d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-receiver-message-tracking-nrr"></a>配置接收方消息跟踪（NRR）
作为本页设置的一部分，您可以指定是否将入站消息及其确认 (MDN) 存储在不可否认数据库中。 有关详细信息，请参阅[AS2 处理在 BizTalk Server](../core/as2-processing-in-biztalk-server.md)。  
  
 若要将消息存储在不可否认数据库中，您必须启用 NRR（接收的不可否认性）作为 AS2 协议属性的一部分。 NRR 可确保发送方已验证消息收件人的签名回执。 从理论上讲，NRR 是消息发件人证明消息以未改变的状态到达目的地的不可否认的证据。 仅在数字签名了原始消息和回执时，才能建立 NRR。  
  
> [!IMPORTANT]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a>配置入站 AS2 消息和出站 MDN 的消息跟踪  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**接收方消息跟踪 (NRR)**。  
  
    > [!NOTE]
    >  要保障接收的不可否认性，必须对消息进行验证和确保消息的完整性。 实现此目的的推荐方法是对消息使用数字签名。 因此，如果你选择任何要在不可否认性数据库中存储消息的属性，你应该对消息进行签名通过选择**应对消息进行签名**属性**验证**页。  
  
3.  选择**为入站的已编码 AS2 消息启用 NRR**将出站的已编码的 AS2 消息存储在不可否认性数据库。  
  
4.  选择**为入站的已解码 AS2 消息启用 NRR**将出站的已解码的 AS2 消息存储在不可否认性数据库。  
  
5.  选择**为出站的 MDN 启用 NRR**将入站的 MDN 存储在不可否认性数据库。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)