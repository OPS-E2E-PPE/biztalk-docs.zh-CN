---
title: "配置常规本地主机设置 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5e5c076e6b245e4a662f8132d027e927df6142
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-local-host-settings-as2"></a>配置常规本地主机设置（AS2）
作为本地主机常规设置的一部分，可以指定 AS2 消息的内容类型以及是否将文件名保留为 AS2 消息标头的一部分。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-the-general-settings"></a>配置常规设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**常规**。  
  
3.  选择**发送消息之前检查证书吊销列表**复选框，以确定是否已在证书吊销列表中，包含要用于对传出消息进行签名的证书，该值指示它已被吊销，或是否超过到期日期。 如果是这样，BizTalk 服务器不会加密消息，但它时将挂起。 如果清除此属性，BizTalk Server 将不会执行此项检查。  
  
    > [!NOTE]
    >  存在与检索和搜索证书吊销列表有关的延迟时间。  
  
4.  有关**默认内容类型**，选择当事方必须使用传出的 AS2 消息的默认内容类型。 如果`ContentType`属性设置的消息正文部分，设置将用于生成传出的消息; 否则为上下文中的值**默认内容类型**使用属性。  
  
5.  选择**MIME 标头中的传输文件名**复选框以将文件名作为出站 AS2 消息的 MIME 标头的一部分发送。 若要指定的文件名称，选择**指定文件名**或**使系统生成文件名**。  
  
    > [!NOTE]
    >  选择**使系统生成文件名**将生成新的 GUID 值作为发送 AS2 消息中每个附件的文件名称。  
  
6.  如果你选择**指定文件名**，输入中的字符串值或上下文属性**指定文件名**字段。 你还可以启用**挂起消息，如果找不到上下文属性 （例如 %属性 %）**挂起消息，如果所选的上下文属性不存在的出站消息。  
  
    > [!NOTE]
    >  若要指定上下文属性，请将 %字符的属性名称。 例如， `%FILE.ReceivedFileName%`。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)