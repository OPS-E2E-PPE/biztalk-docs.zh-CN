---
title: "配置验证 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135d048f7dede032803b5830faec4570fa1f4d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-as2"></a>配置验证（AS2）
在合作伙伴协议中，您必须指定验证设置来验证入站 AS2 消息。  
  
> [!NOTE]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将以下属性禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
>   
>  -   **使用验证和 MDN 的协议设置，而不是消息标头**  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-validation-properties"></a>配置验证属性  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，单击**验证**。  
  
3.  选择**使用验证和 MDN 的协议设置，而不是消息标头**复选框，如果你想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证数字签名、 压缩和加密的传入消息，基于中的设置协议。 如果已清空该复选框，则将会根据消息 AS2 标头中的属性来验证消息（而不是根据协议属性）以确定此过程。 AS2 标头的列表，请参阅[AS2 消息](../core/as2-messages.md)。  
  
4.  选择**应对消息进行签名**复选框以确保入站的消息进行签名。  
  
5.  选择**应对消息进行压缩**复选框以确保压缩的入站的消息。  
  
6.  选择**应对消息进行加密**复选框以确保入站的消息进行加密。 选择从的加密算法**加密算法**下拉列表。 

    **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]和更高版本**，AES 支持将自动包含。 选项包括 DES3、 RC2，AES128 （默认值）、 AES192 和 AES256。
    
    有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本，选项为 DES3 和 RC2。
  
    > [!NOTE]
    >  仅当设置了正确的属性后，AS2 接收管道才会对数字签名进行验证，对消息进行解压缩或解密。 如果**使用验证和 MDN 的协议设置，而不是消息标头**选择属性和消息具有用于签名、 压缩和加密比在协议中选择不同的传输属性属性，然后 AS2 解码器将挂起消息，并且会产生错误。  
  
7.  选择**检查证书吊销列表**复选框，以确定要用于验证传入消息的证书是否已包括在证书吊销列表，表示，它已被吊销，或者，是否到期日期已过。 如果已吊销，BizTalk Server 将不会对消息解密，但会挂起消息。 如果清除此属性，BizTalk Server 将不会执行此项检查。  
  
    > [!NOTE]
    >  存在与检索和搜索证书吊销列表有关的延迟时间。  
  
8.  选择**检查中的重复消息**复选框，以确定传入消息是否为重复的以前接收消息。  
  
     如果你选中**检查中的重复消息**属性，设置**天**属性以指示以前接收的消息时检查要使用的跨度复制，检查**挂起重复消息**属性以指示应挂起重复消息。  
  
    > [!NOTE]
    >  **AS2-从**和**AS2-到**字段用于确定消息是否为重复。 如果该消息所包含的这些字段的值与先前接收的消息的这些字段值相同，那么，即使其他标头或负载不同，该消息也会被标记为重复消息。  
  
9. 单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)