---
title: 如何配置身份验证选项接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012ec38ef3d9acf53c7293c668b17cd85c6c738d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248805"
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a>如何为接收端口配置验证选项
本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置消息验证选项。 此选项在配置了参与方解析验证后生效。 相应的选项包括：  
  
-   **无身份验证。** 如果选中此选项，接收端口将以直通方式传送消息而不检查消息凭据。  
  
-   **如果身份验证失败，则丢弃消息。** 如果选中此选项，则接收端口将使用参与方解析检查消息凭据，并在验证失败时放弃消息。  
  
-   **如果身份验证失败，则保留消息。** 如果选中此选项，则接收端口将使用参与方解析检查消息凭据，并在验证失败时在挂起的队列中保留消息。  
  
 有关创建和配置方的说明，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。 有关方解析身份验证的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)和[入站消息身份验证](../core/inbound-message-authentication.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a>为接收端口配置验证选项  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置验证的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**接收端口**，右键单击接收端口，然后单击**属性**。  
  
4.  在**身份验证**部分中，选择选项，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收端口](../core/managing-receive-ports.md)