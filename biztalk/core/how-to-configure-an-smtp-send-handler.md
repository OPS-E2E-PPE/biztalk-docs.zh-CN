---
title: "如何配置一个 SMTP 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99dc71cf04d8a80b3a88630908a814957c83b8cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-smtp-send-handler"></a>如何配置一个 SMTP 发送处理程序
您可以在 BizTalk 管理控制台中设置 SMTP 发送处理程序属性。 如果未对各 SMTP 发送端口单独设置属性，则可以将这些发送处理程序属性用作发送端口配置值。  
  
### <a name="to-change-global-variables-for-an-smtp-send-handler"></a>更改 SMTP 发送处理程序的全局变量  
  
1.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**SMTP**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择的主机发送处理程序将与之相关联，并依次**属性**。  
  
4.  在**SMTP 传输属性**对话框中，在**属性**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**SMTP 服务器名称和 TCP 端口**|**[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> 必需的。 输入 SMTP 服务器名称和 （可选） 若要在发送消息时使用的 TCP 端口号。 例如，您可以输入：<br /><br /> -mySMTPserver<br />-mySMTPserver.internet.com:2525<br /><br /> **在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  （包括 BizTalk Server 2013)，只需输入 SMTP 服务器名称。 TCP 端口 25 进行硬编码。<br /><br /> 最大长度：256|  
    |**发件人 （电子邮件地址）**|必需的。 输入的电子邮件地址将 SMTP**从**标头。<br /><br /> 最大长度：256|  
    |**身份验证类型**|输入要使用的 SMTP 服务器的身份验证的类型。<br /><br /> 选项：<br /><br /> -   **无身份验证**<br />-   **基本身份验证**<br />-   **进程帐户 (NTLM)**<br /><br /> 默认值：进程帐户(NTLM)|  
    |**用户名**|输入要使用的 SMTP 服务器的身份验证的用户名称。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**密码**|输入要用于 SMTP 服务器的身份验证的密码。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)