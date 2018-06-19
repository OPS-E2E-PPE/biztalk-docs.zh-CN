---
title: 配置确认 (Mdn) (AS2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2df8c92d37d5f6bc8fbf8d6d77fb698e6178036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234101"
---
# <a name="configuring-acknowledgements-mdns-as2"></a>配置确认 (MDN) (AS2)
在合作伙伴协议中，您可以指定接收 AS2 消息的参与方生成 MDN 响应并将其发回的方式。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **重新发送 AS2 消息如果未收到 MDN**复选框和关联的属性  
> -   **重写发送端口设置**复选框和关联的属性  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-acknowledgements"></a>配置确认  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，单击**确认 (Mdn)**。  
  
3.  选择**路由/传递到 MessageBox 处理入站的 MDN**复选框，以作为传递消息，然后再连接 MessageBox 路由通过 A2 解码器 MDN。 当选择此属性时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会提升用于路由的 `IsAS2MdnResponseMessage` 属性。  
  
4.  如果你选中**使用用于验证和 MSDN 的协议设置，而不是消息标头**中的属性**验证**页上，选择**请求 MDN**如果复选框贸易合作伙伴必须生成 MDN 来响应 AS2 消息。  
  
     如果**请求 MDN**选择复选框后，你还可以设置以下属性：  
  
    1.  选择**请求经过签名的 MDN**复选框并从**签名算法**下拉列表选择贸易合作伙伴必须使用进行签名的 MDN 的 MIC 算法。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]支持 MD5、 SHA1、 和 SHA2 (SHA256 （默认值）、 SHA384 和 SHA512)。
    
        > [!NOTE] 
        > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]和更高版本**，SHA2 支持将自动包含。 有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本，请参阅[KB 3123748](https://support.microsoft.com/kb/3123748)。
  
    2.  选择**请求异步 MDN**复选框，然后在**回执送达选项 (URL)** 文本框中，输入接收方应发送到 MDN 的 URL。  
  
         如果**请求异步 MDN**选择复选框后，你还可以设置以下属性：  
  
        1.  选择**重新发送 AS2 消息如果未收到 MDN**复选框以使重新传输的 AS2 消息。 输入一个值**最小 AS2 消息重新发送间隔**，**数的 AS2 消息重新发送尝试**和**停止尝试的 AS2 消息后将重新发送**字段来指定重试间隔、 最大尝试次数和何时停止重新发送消息。  
  
            > [!NOTE]
            >  必须选择**打开 ON Reporting**上的复选框**常规属性**页**常规**之前选择的选项卡**重新发送 AS2 消息如果 MDN 不收到**。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用跟踪为 AS2 reporting 以确定何时重新发送 AS2 消息存储的信息。  
  
        2.  如果**重新发送 AS2 消息如果未收到 MDN**选中复选框，则检查**替代发送端口设置**指定**最小 HTTP 重试间隔**和**HTTP 重试尝试次数**。 输入一个值**后重试停止尝试 HTTP**字段来指定最长时间使用 HTTP 适配器重试。  
  
    3.  如果你选择**请求异步 MDN**复选框并且指定的 URL**回执送达选项 (URL)** 属性，**处置-到通知**文本框中，默认情况下设置为相同的 URL。 如果你未选择**请求异步 MDN**复选框，你必须输入一个值**处置-到通知**。 此字段中的值不会在 AS2 处理中使用。  
  
5.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)