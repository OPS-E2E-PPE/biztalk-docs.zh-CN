---
title: "配置收件人 MDN 设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-receiver-mdn-settings"></a>配置收件人 MDN 设置
作为接收器 MDN 设置的一部分，您可以根据 AS2 消息标头来指定控制 MDN 生成的属性。  
  
> [!IMPORTANT]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-receiver-mdn-settings"></a>配置接收方 MDN 设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**收件人 MDN 设置**。  
  
3.  如果你没有检查**使用验证和 MDN 的协议设置，而不是消息标头**中的属性**验证**页上，你可以选择具有发送 MDN，方签名的 MDN，如果MDN 生成通过**处置-到通知**AS2 标头，但**处置通知选项**标头不会启用签名。 发生这种情况**处置通知选项**未设置，或设置为可选。 你可以通过单击来实现**登录请求 MDN 不预设处置通知选项标头是否已签名回执协议标头设置为可选**。  
  
4.  你可以输入中的文本**MDN 文本**字段可以在参与方发送 MDN 将其添加到 MDN 消息 （在内容说明字段中）。 此设置十分适用，并且不用考虑是否根据 AS2 标头或协议属性生成 MDN。  
  
5.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)