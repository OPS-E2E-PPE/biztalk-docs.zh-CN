---
title: 配置消息的 HTTP 设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d15ebb5ff5be6678c4dc2aee3f9333f36c75c89f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233085"
---
# <a name="configuring-http-settings-for-messages"></a>配置消息的 HTTP 设置
作为与消息相关的 HTTP 设置的一部分，您可以指定接收 AS2 消息的 Web 服务器所要求的属性。  
  
> [!IMPORTANT]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-message-related-http-settings"></a>配置与消息相关的 HTTP 设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**本地主机设置**部分中，单击**消息的 HTTP 设置**。  
  
3.  选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与生成的 SSL 证书所针对的服务器名称不匹配，将仍 SSL 连接。  
  
4.  单击**HTTP 预期 100 继续**将预期 HTTP 标头设置为 100-继续，请指定不在初始 HTTP 请求，但等待服务器请求内容包括已发布的数据。  
  
5.  单击**保持 HTTP 连接处于活动状态**请求，请求和响应周期完成后，HTTP 连接将保持活动状态。  
  
6.  单击**展开 HTTP 标头**展开到一行的 HTTP 内容类型标头。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)