---
title: MQSeries 适配器安全 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08d5228dab8463c2ad5dc7f9d9347899d4c41a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263197"
---
# <a name="security-with-the-mqseries-adapter"></a>安全与 MQSeries 适配器

MQSeries 适配器安全性首先是要确保 BizTalk 和 MQSeries 服务器的安全。 有关保护 BizTalk Server 的信息，请参阅[安全和保护数据](secure-and-protect-your-biztalk-messages.md)。 有关 MQSeries 服务器安全性的信息，请参阅 IBM MQSeries 服务器文档。  
  
> [!NOTE]
>  在 BizTalk Server 与 MQSeries 服务器之间发送和接收消息时，该适配器将自动使用数据包隐私性。  

## <a name="adapter-security"></a>适配器安全  
 安全地使用适配器本身需要注意以下四个方面：  
  
-   选择 MQSAgent 的应用程序标识和成员  
  
-   使用适配器控制 BizTalk Server 帐户  
  
-   确保队列创建脚本安全  
  
-   使适合使用**SSO Affiliate 应用程序**属性  
  
 在配置过程中为应用程序标识指定的帐户不应为管理员帐户。 相反，该帐户应具有所需的最小权限-读取和写入访问权限 MQSeries 队列。  
  
 确保只将使用该适配器的 BizTalk Server 帐户分配给 MQSAgent 角色。  
  
 使用在队列定义过程中创建的导出脚本时，应将脚本置于安全区域中。 只有使用这些脚本的管理员才具有访问权限。  
  
 如果你的应用程序使用 MQCIH 和 MQIIH 标头属性放置在出站消息中的用户凭据，使用**SSO Affiliate 应用程序**属性**传输属性**页。 有关此属性的详细信息，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器的结构](../core/structure-of-the-mqseries-adapter.md)   
 [什么是 MQSeries 适配器？](../core/what-is-the-mqseries-adapter.md)