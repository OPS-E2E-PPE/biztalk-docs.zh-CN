---
title: 配置接收方消息跟踪 (NRR) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b57c9b032fb557c23e7ec11a6e6f60fd6692b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355282"
---
# <a name="configuring-receiver-message-tracking-nrr"></a>配置接收方消息跟踪 (NRR)
作为此页上设置的一部分，可以指定是否在不可否认数据库中存储入站的消息和及其确认 (Mdn)。 有关详细信息，请参阅[BizTalk Server 中的 AS2 处理](../core/as2-processing-in-biztalk-server.md)。  
  
 若要将消息存储在不可否认数据库中，您必须启用 NRR （不可否认接收的） 作为 AS2 协议属性的一部分。 NRR 可确保发送方已验证消息接收方的签名的回执。 从概念上讲，NRR 是消息发件人消息到达目标不变的确凿无疑的证据。 仅当原始消息和接收经过数字签名时，才能建立 NRR。  
  
> [!IMPORTANT]
>  没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a>若要配置入站的 AS2 消息和出站 MDN 的消息跟踪  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**本地主机设置**部分中，单击**接收方消息跟踪 (NRR)**。  
  
    > [!NOTE]
    >  若要确保不可否认性的回执，必须建立身份验证和确保消息的完整性。 推荐的方法来这样做因此是对消息使用数字签名。 因此，如果您选择任何要在不可否认数据库中存储消息的属性，你应登录消息通过选择**应对消息进行签名**上的属性**验证**页。  
  
3.  选择**已为入站编码 AS2 消息启用 NRR**的不可否认数据库中存储出站编码的 AS2 消息。  
  
4.  选择**已为入站解码 AS2 消息启用 NRR**的不可否认数据库中存储解码后的出站 AS2 消息。  
  
5.  选择**对出站 MDN 启用 NRR**来将入站的 MDN 存储在不可否认数据库中。  
  
6.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)