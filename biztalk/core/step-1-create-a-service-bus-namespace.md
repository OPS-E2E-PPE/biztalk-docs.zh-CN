---
title: "步骤 1： 创建服务总线 Namespace |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-a-service-bus-namespace"></a>步骤 1： 创建服务总线 Namespace
在此步骤中，你将创建[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]命名空间。 你将使用此命名空间托管用于从 Salesforce 接收机会通知的中继终结点。 在创建此解决方案的过程的后面部分，将使用此中继终结点将通知消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统中。  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a>创建 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间  
  
1.  登录到[http://manage.windowsazure.com](http://manage.windowsazure.com)使用你的 Microsoft 帐户。  
  
2.  在页面底部，单击**新建**，**应用程序服务**， **Service Bus 中继**，，然后**快速创建**。  
  
3.  输入作为命名空间`BtsSalesforce`选择离你当前的地理位置区域。 单击**创建中继**。  
  
    > [!CAUTION]
    >  这必须是全球唯一的命名空间。 因此，你必须使用本教程中提及的命名空间以外的命名空间。  
  
    > [!NOTE]
    >  请注意，中继并不作为操作的一部分创建，只有命名空间才是如此。 我们将配置的接收位置时，将中继终结点创建本教程中稍后**SB 消息**适配器。  
  
4.  创建命名空间后，将状态设置为**Active**。 活动状态后，你可以选择的命名空间并单击**访问密钥**要获取有关如何连接到的详细信息的页的底部**BtsSalesforce**命名空间，包括的值**默认用户**和**默认密钥**。 在本教程的后面部分，你将需要这些详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [教程 6： 将与 Salesforce 集成 BizTalk Server 2013](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)