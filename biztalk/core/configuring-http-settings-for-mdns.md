---
title: 配置 Mdn 的 HTTP 设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74ba2eaf11e8beed3e28d10beb9f95b2f0f6194
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233333"
---
# <a name="configuring-http-settings-for-mdns"></a>配置 MDN 的 HTTP 设置
作为 MDN 相关 HTTP 设置的一部分，您可以指定接收 MDN 的 Web 服务器所需的属性。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-mdn-related-http-settings"></a>若要配置的相关 MDN 的 HTTP 设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**Mdn 的 HTTP 设置**。  
  
3.  选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与生成的 SSL 证书所针对的服务器名称不匹配，将仍 SSL 连接。  
  
4.  单击**HTTP 预期 100 继续**将预期 HTTP 标头设置为 100-继续，请指定不在初始 HTTP 请求，但等待服务器请求内容包括已发布的数据。  
  
5.  单击**保持 HTTP 连接处于活动状态**请求，请求和响应周期完成后，HTTP 连接将保持活动状态。  
  
6.  单击**展开 HTTP 标头**展开到一行的 HTTP 内容类型标头。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)