---
title: MQSeries 适配器安全性 |Microsoft Docs
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
ms.openlocfilehash: 2cf8d0b960f09ef3ba955da9996aa858595688f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323658"
---
# <a name="security-with-the-mqseries-adapter"></a>使用 MQSeries 适配器的安全

MQSeries 适配器安全性始于保护你的 BizTalk 和 MQSeries 服务器。 有关保护 BizTalk Server 的信息，请参阅[安全和保护你的数据](secure-and-protect-your-biztalk-messages.md)。 有关 MQSeries 服务器安全性的信息，请参阅 IBM MQSeries 服务器文档。  
  
> [!NOTE]
>  适配器会自动使用数据包隐私性发送和接收 BizTalk Server 和 MQSeries 服务器之间的消息。  

## <a name="adapter-security"></a>适配器安全性  
 安全地使用适配器本身需要注意以下四个方面：  
  
- 选择应用程序标识和 MQSAgent 的成员  
  
- 控制使用的适配器的 BizTalk Server 帐户  
  
- 保护队列创建脚本  
  
- 进行适当利用**SSO 关联应用程序**属性  
  
  在配置期间分配给应用程序标识的帐户不应是管理员帐户。 相反，该帐户应具有所需的最小权限 — 读取和写入访问权限向 MQSeries 队列。  
  
  请确保分配仅使用 MQSAgent 角色到适配器的 BizTalk Server 帐户。  
  
  当使用导出队列定义过程中创建的脚本时，应将脚本置于安全区域。 只有使用脚本的管理员才具有访问权限。  
  
  如果你的应用程序使用 MQCIH 和 MQIIH 标头属性将用户凭据置于出站消息中，使用**SSO 关联应用程序**上的属性**传输属性**页。 有关此属性的详细信息，请参阅[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器的结构](../core/structure-of-the-mqseries-adapter.md)   
 [MQSeries 适配器概述](../core/what-is-the-mqseries-adapter.md)