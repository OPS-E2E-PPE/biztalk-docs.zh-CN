---
title: 配置常规本地主机设置 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b990a44c9599ff725bdd19f7bfdd8286ec11487d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391113"
---
# <a name="configuring-general-local-host-settings-as2"></a>配置常规本地主机设置 (AS2)
作为本地主机常规设置的一部分，可以指定是否作为 AS2 消息标头的一部分保留的文件的名称和 AS2 消息的内容类型。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
>   
>  仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-the-general-settings"></a>若要配置常规设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**本地主机设置**部分中，单击**常规**。  
  
3.  选择**发送消息之前检查证书吊销列表**复选框，以确定是否已在证书吊销列表中，包含要在签名传出消息中使用的证书，该值指示它已被吊销，或是否超过到期日期。 如果是这样，BizTalk Server 不会加密消息，但将挂起消息。 如果清除此属性，则 BizTalk Server 将不执行此检查。  
  
    > [!NOTE]
    >  检索和搜索证书吊销列表所涉及的是延迟。  
  
4.  有关**默认内容类型**，选择参与方必须用于传出 AS2 消息的默认内容类型。 如果`ContentType`属性设置的上下文中为消息正文部分，设置是用于生成传出消息; 否则为此设置的值**默认内容类型**使用属性。  
  
5.  选择**MIME 标头中的传输文件名**复选框以将文件名作为出站 AS2 消息的 MIME 标头的一部分发送。 若要指定的文件的名称，选择**指定的文件名**或**让系统生成文件名**。  
  
    > [!NOTE]
    >  选择**让系统生成文件名**将作为 AS2 消息中发送每个附件的文件名生成新的 GUID 值。  
  
6.  如果所选**指定的文件名**，输入中的字符串值或上下文属性**指定文件名**字段。 您还可以启用**挂起消息上下文属性 （例如 %property%)找不到**以挂起消息，如果所选的上下文属性不存在对出站消息。  
  
    > [!NOTE]
    >  若要指定的上下文属性，请将 %字符的属性名称。 例如，`%FILE.ReceivedFileName%`。  
  
7.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)