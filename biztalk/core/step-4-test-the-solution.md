---
title: "步骤 4： 测试解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-solution"></a>步骤 4： 测试解决方案
在本主题中，你将在与 FILE 接收端口关联的文件夹中放置一个虚拟请求消息，以便对解决方案进行测试。 只是为了调用 dummy 请求消息中所述，放置**WCF WebHttp**发送端口。 你可以创建如下所示的虚拟请求消息：  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  从 BizTalk Server 管理控制台中，启动**BizTalk 应用程序 1**。 这将启动你在上述步骤中创建的所有端口。  
  
2.  打开 Windows 资源管理器，然后导航到与 FILE 接收位置关联的位置。 在此位置复制虚拟请求消息。  
  
3.  当文件消失时，检查与 FILE 发送端口（处理来自 REST 接口的响应消息）关联的位置。 其中应包含一个 XML 响应消息。 打开该 XML 消息可查看延误的美国航空公司航班的详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [教程 5： 调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)