---
title: 如何启用的路由失败消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e524f96114e887569c10294be0e665f1aa711a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337933"
---
# <a name="how-to-enable-routing-for-failed-messages"></a>如何为失败消息启用路由功能
失败的消息路由是一个属性的发送和接收端口和情况下，该值指示"为失败消息启用路由"端口的属性页上启用。  
  
> [!NOTE]
>  接收端口上的配置适用于所有与该接收端口相关联的接收位置。  
  
> [!NOTE]
>  发送端口上的配置适用于主要和备份传输。  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a>若要配置失败的消息路由的接收端口 (这适用于单向和请求-响应接收端口)  
  
1. 打开 BizTalk Server 管理控制台。  
  
2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。  
  
3. 单击**接收端口**文件夹。  
  
4. 在右窗格中，双击你想要配置的接收端口的名称。  
  
5. 在接收端口属性页上，在左窗格中，选择**常规**类别。  
  
6. 在右窗格中，选择**失败消息启用路由功能**复选框，然后依次**应用**。  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a>若要配置失败消息路由的发送端口 （这仅适用于静态单向和静态要求响应发送端口）  
  
1. 打开 BizTalk Server 管理控制台。  
  
2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。  
  
3. 单击**发送端口**文件夹。  
  
4. 在右窗格中，双击你想要配置的发送端口的名称。  
  
5. 在发送端口的属性页上，在左窗格中，选择**传输高级选项**类别。  
  
6. 在右窗格中，在**传输选项**组框中，选择**失败消息启用路由功能**复选框，然后依次**应用**。  
  
## <a name="see-also"></a>请参阅  
 [错误处理](../core/error-handling.md)