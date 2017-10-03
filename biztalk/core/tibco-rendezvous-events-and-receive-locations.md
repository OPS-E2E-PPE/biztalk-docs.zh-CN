---
title: "TIBCO 集合事件和接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a>TIBCO 集合事件和接收位置
任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。 这一概念*事件*是代的其他 TIBCO 会合程序的消息。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  创建接收位置。  
  
2.  将接收位置与主机相关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置已启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置都必须具有唯一名称。 同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。  
  
> [!IMPORTANT]
>  建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。 例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)