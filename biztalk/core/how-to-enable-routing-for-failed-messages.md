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
ms.openlocfilehash: c00e49afa528bc0008d73272dca561d461660367
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008486"
---
# <a name="how-to-enable-routing-for-failed-messages"></a>如何为失败消息启用路由功能
失败消息路由是发送端口和接收端口的属性，可通过在端口的属性页上指示“为失败消息启用路由功能”来启用。  
  
> [!NOTE]
>  配置在接收端口上时，适用于与该接收端口有关的所有接收位置。  
  
> [!NOTE]
>  配置在发送端口上时，既适用于主传输，也适用于备份传输。  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a>为接收端口配置失败消息路由（此配置适用于单向接收端口和请求-响应接收端口）  
  
1. 打开 BizTalk Server 管理控制台。  
  
2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。  
  
3. 单击**接收端口**文件夹。  
  
4. 在右侧窗格中，双击要配置的接收端口的名称。  
  
5. 在接收端口属性页上，在左窗格中，选择**常规**类别。  
  
6. 在右窗格中，选择**失败消息启用路由功能**复选框，然后依次**应用**。  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a>为发送端口配置失败消息路由（此配置仅适用于静态单向发送端口和静态要求-响应发送端口）  
  
1. 打开 BizTalk Server 管理控制台。  
  
2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。  
  
3. 单击**发送端口**文件夹。  
  
4. 在右侧窗格中，双击要配置的发送端口的名称。  
  
5. 在发送端口的属性页上，在左窗格中，选择**传输高级选项**类别。  
  
6. 在右窗格中，在**传输选项**组框中，选择**失败消息启用路由功能**复选框，然后依次**应用**。  
  
## <a name="see-also"></a>请参阅  
 [错误处理](../core/error-handling.md)