---
title: 步骤 4：测试解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56869aa22ab54efe78838403ae060154b98a001a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392474"
---
# <a name="step-4-test-the-solution"></a>步骤 4：测试解决方案
删除与文件关联的文件夹中的虚拟请求消息测试解决方案本主题中接收端口。 如中所述，你放置虚拟请求消息仅仅是为了调用**Wcf-webhttp**发送端口。 可以创建虚拟请求消息，如下所示：  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  从 BizTalk Server 管理控制台中，启动**BizTalk Application 1**。 这会启动我们在前面的步骤中创建的所有端口。  
  
2.  打开 Windows 资源管理器，并导航到与文件关联的位置接收位置。 在此位置，将复制虚拟请求消息。  
  
3.  在该文件消失后，检查与处理来自 REST 接口的响应消息的文件发送端口关联的位置。 它应包含一个 XML 响应消息。 打开要查看航班为从的都延迟的详细信息的 XML 消息。  
  
## <a name="see-also"></a>请参阅  
 [教程 5:调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)