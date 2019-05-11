---
title: 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fefe11eb38575a7225b6cc88c3977df6bab685b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398213"
---
# <a name="receive-locations"></a>接收位置
创建接收位置涉及到指定的地址的入站的消息到达时以及在该地址接收对消息进行处理的消息传送管道。 只有管理员才能创建和启用接收位置。  
  
 管理员使用 BizTalk 管理控制台来创建接收位置、 接收位置绑定到业务流程，启用接收位置、 禁用接收位置，和设置全局属性的接收位置。  
  
 管理员 （使用 BizTalk 管理控制台） 遵循以下步骤创建接收位置：  
  
1.  创建接收位置。  
  
2.  将接收位置与主机相关联。  
  
3.  将接收位置绑定到业务流程。  
  
4.  启用接收位置。  
  
5.  接收位置接收消息。  
  
> [!NOTE]
>  更改接收位置所做的如何使用 Windows Management Instrumentation (WMI) 会影响接收位置在 BizTalk 管理控制台中显示。 例如，如果管理员使用 WMI 来创建新接收位置，则该接收位置将显示在 BizTalk 管理控制台中。 同样，如果管理员删除某一接收位置，将从 BizTalk 管理控制台中消失的接收位置。  
> 
> [!IMPORTANT]
>  每个接收位置必须具有唯一的名称。 两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
> 
> [!IMPORTANT]
>  我们建议您设置加强的访问控制列表 (ACL) 中的接收位置的放置位置。 例如，您必须设置加强的目录的 Acl 文件接收位置从其中提取消息，以便只有经过授权的用户可以在此位置中存放消息。  
  
## <a name="receive-location-types"></a>接收位置类型  
 有两种类型的接收位置  
  
-   单向。 用于存放消息并且不等待同步回复的应用程序。  
  
-   请求-响应。 与需要对一条消息的响应的应用程序一起使用。  
  
## <a name="receive-location-properties"></a>接收位置属性  
 接收位置具有全局和特定于适配器的属性。 管理员使用 BizTalk 管理控制台中，设置全局属性的所有接收位置与特定适配器相关联。  
  
 按序发生更改，以接收位置属性。 如果解决方案开发人员修改属性值某一特定接收位置、 新的属性值重写的全局属性值的接收位置在 BizTalk 管理控制台中设置管理员。  
  
## <a name="see-also"></a>请参阅  
 [管理接收位置](../core/managing-receive-locations.md)   
 [项目](../core/artifacts.md)