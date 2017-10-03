---
title: "接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9866edd5dfa6f953c4e847f191891bd7e6bc25ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-locations"></a>接收位置
创建接收位置涉及指定入站消息到达的地址以及用于处理在该地址接收的消息的消息传送管道。 只有管理员才能创建和启用接收位置。  
  
 管理员使用 BizTalk 管理控制台来创建接收位置，将接收位置绑定到业务流程，启用接收位置，禁用接收位置，以及为接收位置设置全局属性。  
  
 若要创建接收位置，管理员（使用该 BizTalk 管理控制台）可以按照这些步骤进行操作：  
  
1.  创建接收位置。  
  
2.  将接收位置与某个主机相关联。  
  
3.  将接收位置绑定到业务流程。  
  
4.  允许接收位置。  
  
5.  接收位置接收消息。  
  
> [!NOTE]
>  使用 Windows Management Instrumentation (WMI) 对接收位置所做的更改会影响接收位置在 BizTalk 管理控制台中显示的方式。 例如，如果管理员使用 WMI 来创建新接收位置，则该接收位置将显示在 BizTalk 管理控制台中。 同样，如果管理员删除某一接收位置，则该接收位置将从 BizTalk 管理控制台中消失。  
  
> [!IMPORTANT]
>  每个接收位置都必须具有唯一名称。 两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
> [!IMPORTANT]
>  建议您在存放位置中为接收位置设置加强的访问控制列表 (ACL)。 例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。  
  
## <a name="receive-location-types"></a>接收位置类型  
 接收位置具有以下两种类型：  
  
-   单向。 用于存放消息并且不等待同步回复的应用程序。  
  
-   请求-响应。 用于需要消息响应的应用程序。  
  
## <a name="receive-location-properties"></a>接收位置属性  
 接收位置具有全局属性和特定于适配器的属性。 使用 BizTalk 管理控制台中，管理员设置的特定适配器关联的接收位置的所有全局属性。  
  
 对接收位置属性的更改将按序发生。 如果解决方案开发人员修改的属性值，对特定接收位置，新属性值将重写的全局属性值，接收管理员设置了 BizTalk 管理控制台中的位置。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收位置](../core/managing-receive-locations.md)   
 [项目](../core/artifacts.md)