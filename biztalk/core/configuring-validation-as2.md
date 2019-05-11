---
title: 配置验证 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ee93a214730303b4ce510d0da8d4d08e2073990
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390583"
---
# <a name="configuring-validation-as2"></a>配置验证 (AS2)
在合作伙伴协议中，必须指定验证设置来验证入站的 AS2 消息。  
  
> [!NOTE]
>  没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，以下属性中的相同页上禁用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
>   
>  -   **使用的验证和 MDN 的协议设置而非消息标头**  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-validation-properties"></a>若要配置验证属性  
  
1. 创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡上，单击**验证**。  
  
3. 选择**使用的验证和 MDN 的协议设置而非消息标头**复选框，如果你想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证数字签名、 压缩和加密的传入消息，根据中的设置协议。 如果清除该复选框，则将根据消息 AS2 标头而不是协议属性来确定此处理过程中的属性来验证消息。 有关 AS2 标头的列表，请参阅[AS2 消息](../core/as2-messages.md)。  
  
4. 选择**应对消息进行签名**复选框以确保对入站的消息进行签名。  
  
5. 选择**应对消息进行压缩**复选框以确保对入站的消息进行压缩。  
  
6. 选择**应对消息进行加密**复选框以确保对入站的消息进行加密。 选择中的加密算法**加密算法**下拉列表。 

   **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]及更高版本**，则会自动包括 AES 支持。 选项包括 DES3、 RC2，AES128 （默认）、 AES192 和 AES256。
    
   对于以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本，选项为 DES3 和 RC2。
  
   > [!NOTE]
   >  只有设置相应属性时，如果 AS2 接收管道验证数字签名、 消息，进行解压缩或解密消息。 如果**使用的验证和 MDN 的协议设置而非消息标头**选择属性，该消息具有签名、 压缩和加密的协议上选择的不同的传输属性属性，则 AS2 解码器将挂起消息并发布错误。  
  
7. 选择**检查证书吊销列表**复选框，以确定要用于验证传入消息的证书是否已包含在该值指示是否已被吊销，证书吊销列表或是否已超过到期日期。 如果是这样，BizTalk Server 不会解密该消息，但将挂起消息。 如果清除此属性，则 BizTalk Server 将不执行此检查。  
  
   > [!NOTE]
   >  检索和搜索证书吊销列表所涉及的是延迟。  
  
8. 选择**检查重复消息**复选框，以确定传入消息是否为重复的以前收到的消息。  
  
    如果您选中**检查重复消息**属性，则设置**天**属性以指示以前接收的消息时检查要使用的跨度复制，检查**挂起重复消息**属性以指示应挂起重复消息。  
  
   > [!NOTE]
   >  **AS2-从**并**AS2-到**字段用于确定消息是否重复。 如果消息包含为这些字段与先前接收的消息相同的值，它将标记为重复这是即使其他标头或负载不同。  
  
9. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)