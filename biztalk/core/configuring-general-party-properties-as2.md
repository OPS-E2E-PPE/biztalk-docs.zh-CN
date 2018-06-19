---
title: 配置常规参与方属性 (AS2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9a4dbd0-8849-403a-af82-58ee0b10f85a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d947baa1a3f9ea867f1b3a85a8b60129d31ee3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007047"
---
# <a name="configuring-general-party-properties-as2"></a>配置常规参与方属性（AS2）
参与方或贸易合作伙伴表示业务关系中的一个参与组织。 参与方属性包含下列信息：  
  
-   常规信息（如参与方名称）  
  
-   与该参与方关联的发送端口  
  
-   与该参与方关联的证书  
  
 有关方或贸易合作伙伴的详细信息，请参阅[贸易合作伙伴](../core/trading-partners-and-business-profiles.md)。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-party-properties"></a>配置参与方属性  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。  
  
2.  上**常规**页**参与方属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|输入参与方名称。|  
    |**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**|选中此复选框以指定该参与方代表托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的同一个贸易合作伙伴。 **重要说明：** 两方 Tpm 使用全新的管道的解决方案附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须选择至少一个方此复选框。 **注意：** 如果清除此复选框，将创建此参与方的协议时禁用某些属性。|  
    |**其他属性 – 名称/值**|输入一个名称/值对以存储有关参与方的任何信息。 可以根据需要添加任意数量的名称/值对。 **注意：** 名称-值对不用于 BizTalk server 任何处理; 此数据是仅供信息。|  
    |**删除**|单击此项可删除所选的名称/值对。|  
  
3.  上**发送端口**页**参与方属性**对话框框中，执行以下操作：  
  
    > [!NOTE]
    >  在 BizTalk Server 中，在协议级别完成发送端口关联。 **发送端口**作为一部分的参与方属性是只是为了向后兼容，会出现页面。 每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。 但是，反之则不然。 不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。 有关如何将发送端口与协议关联的详细信息，请参阅此处。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**发送端口的名称**|从下拉列表中选择要绑定到此参与方的发送端口。|  
    |**发送端口的 URI**|显示发送端口地址。|  
    |**删除**|单击此项可删除所选从该参与方发送端口。|  
    |**属性**|单击此项可显示**发送端口属性**所选的发送端口的对话框。|  
  
    > [!NOTE]
    >  通过将订阅消息的发送端口和与参与方关联的发送端口匹配，BizTalk Server 可确定接收该消息的参与方。 BizTalk Server 还可以使用上下文属性来完成此操作。 有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
4.  上**证书**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**浏览**|单击此项可显示**选择证书**对话框中，其中从本地计算机或其他人证书存储，将应用到消息传输到方选择签名证书。|  
    |**公用名**|显示所选证书的说明。|  
    |**指纹**|显示用于参与方解析和签名验证的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。|  
    |**删除证书**|单击此项可删除所显示证书。|  
  
    > [!NOTE]
    >  为参与方指定的证书用于验证来自参与方的 AS2 消息或 MDN 的签名。 用于验证参与方签名的证书必须与用于验证其他参与方签名的证书不同。 AS2 消息的证书的详细信息，请参阅[AS2 安全](../core/as2-security.md)。 您可能需要安装和定义用于出站签名、入站签名验证、出站加密和入站解密的证书。  
  
5.  单击**应用**接受属性，或单击**确定**完成的配置设置。 以上任一操作均将验证设置。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 属性](../core/configuring-as2-properties.md)