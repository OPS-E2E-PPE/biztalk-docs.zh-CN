---
title: "配置标识符 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac5f85187a49f3ab5248f12aceba74731ed7e915
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-identifiers-as2"></a>配置标识符（AS2）
在合作伙伴协议中，您必须指定发送方和接收方。 这些值还可用于入站或出站消息的协议解析。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **AS2To**下**其他协议冲突解决程序**部分。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-identifier-properties"></a>配置标识符属性  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，单击**标识符**。  
  
3.  在**AS2-从**页上，指定贸易合作伙伴发送 AS2 消息的名称。  
  
4.  在**AS2-到**页上，指定贸易合作伙伴接收 AS2 消息的名称。  
  
5.  下**其他协议冲突解决程序**部分中，为**AS2To**属性，输入合作伙伴接收消息的其他别名。  
  
    > [!NOTE]
    >  此属性是可选的。 此属性可用于向后兼容。 在将参与方定义从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移到 [!INCLUDE[prague](../includes/prague-md.md)] 时，将包括上一版 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中参与方的名称作为本属性的值。 这可以确保发生协议解析，并且现有的应用程序与合作伙伴定义可以与 [!INCLUDE[prague](../includes/prague-md.md)] 一起使用。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)