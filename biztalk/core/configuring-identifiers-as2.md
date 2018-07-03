---
title: 配置标识符 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f4ec3f66a2cdbacf99650620551b7762bcd56df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978358"
---
# <a name="configuring-identifiers-as2"></a>配置标识符（AS2）
在合作伙伴协议中，您必须指定发送方和接收方。 这些值还可用于入站或出站消息的协议解析。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **AS2To**下**其他协议解析程序**部分。  
> 
>   仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-identifier-properties"></a>配置标识符属性  
  
1. 创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡上，单击**标识符**。  
  
3. 在中**AS2-从**页上，指定发送 AS2 消息的贸易合作伙伴的名称。  
  
4. 在中**AS2-到**页上，指定接收 AS2 消息的贸易合作伙伴的名称。  
  
5. 下**其他协议解析程序**部分中，对于**AS2To**属性，输入接收消息的合作伙伴的其他别名。  
  
   > [!NOTE]
   >  此属性是可选的。 此属性可用于向后兼容。 为 BizTalk Server 中，在以前版本的参与方的名称从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移参与方定义当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含作为此属性的值。 这可确保发生协议解析和现有的应用程序与合作伙伴定义可以用于 BizTalk Server。  
  
6. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)