---
title: 配置确认 (Mdn) (AS2) |Microsoft Docs
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
ms.openlocfilehash: 81d1eb8c500ac746606da82509fb74e4d9afeb6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391385"
---
# <a name="configuring-acknowledgements-mdns-as2"></a>配置确认 (Mdn) (AS2)
在合作伙伴协议中，可以指定如何接收 AS2 消息的参与方生成 MDN 响应并将其发回。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **未收到 MDN 时重新发送 AS2 消息**复选框以及关联的属性  
>   -   **替代发送端口设置**复选框以及关联的属性  
> 
>   仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-acknowledgements"></a>配置确认  
  
1. 创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡上，单击**确认 (Mdn)**。  
  
3. 选择**到 MessageBox 中处理入站的 MDN 以进行路由/传递**路由通过 A2 解码器将 MDN 作为直通消息，然后到 MessageBox 中的复选框。 选中此属性后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]促进`IsAS2MdnResponseMessage`属性供路由使用。  
  
4. 如果您选中**使用的验证和 MSDN 的协议设置而非消息标头**属性中的**验证**页上，选择**请求 MDN**如果复选框贸易合作伙伴必须生成 MDN 以响应 AS2 消息。  
  
    如果**请求 MDN**复选框处于选中状态，还可以设置以下属性：  
  
   1. 选择**请求经过签名的 MDN**复选框和从**签名算法**下拉列表中选择贸易合作伙伴必须用来对 MDN 签名的 MIC 算法。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 支持 MD5、 SHA1、 和 SHA2 (SHA256 （默认）、 SHA384 和 SHA512)。
    
      > [!NOTE]
      > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]及更高版本**，则会自动包括 SHA2 支持。 对于以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本中，请参阅[KB 3123748](https://support.microsoft.com/kb/3123748)。
  
   2. 选择**请求异步 MDN**复选框，然后在**回执送达选项 (URL)** 文字框中，输入接收方应接收 MDN 的 URL。  
  
       如果**请求异步 MDN**复选框处于选中状态，还可以设置以下属性：  
  
      1. 选择**MDN 未收到时重新发送 AS2 消息**复选框以启用 AS2 消息的重新传输。 输入一个值**最小 AS2 消息重新发送间隔**，**数的 AS2 消息重新发送尝试次数**并**停止尝试的 AS2 消息重新发送后**字段，用于指定重试时间间隔，最大尝试次数以及何时停止重新发送消息。  
  
         > [!NOTE]
         >  必须选择**打开报告**上的复选框**常规属性**页**常规**之前选择的选项卡**重新发送 AS2 消息如果 MDN 不收到**。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用跟踪为 AS2 报告以确定何时重新发送 AS2 消息存储的信息。  
  
      2. 如果**MDN 未收到时重新发送 AS2 消息**选中复选框，选中**替代发送端口设置**若要指定**最小 HTTP 重试间隔**和**HTTP 重试尝试次数**。 输入一个值**停止尝试 HTTP 重试后**字段来指定最长时间使用 HTTP 适配器进行重试尝试。  
  
   3. 如果所选**请求异步 MDN**复选框并且指定的 URL**回执送达选项 (URL)** 属性，**处置-到通知**文本框中，默认情况下设置为相同的 URL。 如果未选中**请求异步 MDN**复选框，您必须输入的值**处置-到通知**。 此字段的值不使用在 AS2 处理。  
  
5. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)