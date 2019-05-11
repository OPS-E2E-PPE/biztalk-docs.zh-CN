---
title: 配置 Mdn 的 HTTP 设置 |Microsoft Docs
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
ms.openlocfilehash: 40496efd556d30f87f33d647ab97edb123453c5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355421"
---
# <a name="configuring-http-settings-for-mdns"></a>配置 Mdn 的 HTTP 设置
作为 MDN 相关 HTTP 设置的一部分，可以指定用来接收 Mdn 的 Web 服务器所需的属性。  
  
> [!IMPORTANT]
>  如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
>   
>  仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-mdn-related-http-settings"></a>若要配置与 MDN 相关 HTTP 设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**本地主机设置**部分中，单击**Mdn 的 HTTP 设置**。  
  
3.  选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与为其生成 SSL 证书的服务器名称不匹配，将仍 SSL 连接。  
  
4.  单击**HTTP 预期 100 继续**将 HTTP Expect 标头设置为 100-continue，这将指定不在初始 HTTP 请求中，但等待服务器请求内容包含已发布的数据。  
  
5.  单击**保持 HTTP 连接保持活动状态**请求的 HTTP 连接保持活动状态后请求和响应周期已结束。  
  
6.  单击**展开 HTTP 标头**以将 HTTP 内容类型标头展开为单个行。  
  
7.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)