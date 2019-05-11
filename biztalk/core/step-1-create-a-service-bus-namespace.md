---
title: 第 1 步：创建服务总线 Namespace |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8986f729d48fd25066bd166749d6bfb2b7ed3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392819"
---
# <a name="step-1-create-a-service-bus-namespace"></a>第 1 步：创建服务总线 Namespace
在此步骤中，您将创建[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]命名空间。 将使用此命名空间来托管用于从 Salesforce 接收机会通知的中继终结点。 更高版本的过程中创建此解决方案，您将使用此中继终结点来接收通知消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a>若要创建[!INCLUDE[sb](../includes/sb-md.md)]命名空间  
  
1.  登录到[ http://manage.windowsazure.com ](http://manage.windowsazure.com)使用你的 Microsoft 帐户。  
  
2.  在页面底部，单击**新建**，**应用服务**，**服务总线中继**，然后**快速创建**。  
  
3.  输入的命名空间`BtsSalesforce`并选择离你当前的地理位置最近的区域。 单击**创建中继**。  
  
    > [!CAUTION]
    >  此命名空间必须是全局唯一。 因此，必须使用一个在本教程中所述之外的命名空间。  
  
    > [!NOTE]
    >  请注意，中继不作为操作的一部分创建，只有命名空间。 我们配置的接收位置时，稍后在本教程中创建的中继终结点**SB 消息**适配器。  
  
4.  创建命名空间后，将状态设置为**Active**。 一旦激活状态，可以选择的命名空间，单击**访问密钥**底部的页后，可以获取有关如何连接到详细信息**BtsSalesforce**命名空间，其中包括的值**默认用户**并**默认密钥**。 本教程的后面，将需要这些详细信息。  
  
## <a name="see-also"></a>请参阅  
 [教程 6:将 BizTalk Server 2013 与 Salesforce 集成](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)