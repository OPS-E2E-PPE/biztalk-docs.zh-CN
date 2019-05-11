---
title: 动态发送端口处理程序是可配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21f4985b3e22bd2095e66c240d6c614e1a88c45c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389271"
---
# <a name="dynamic-send-port-handler-is-configurable"></a>动态发送端口处理程序是可配置
创建动态发送端口时，适配器发送处理程序是可以为配置*每个*安装适配器。 请考虑下列方案：  
  
 **应用场景**  
  
 应用程序中有两个 ESB 行程。 Itinerary1 使用动态发送端口将数据发送到文件共享。 Itinerary2 使用动态发送端口发送电子邮件。 在过去，动态发送端口在适配器的默认主机中执行。 Itinerary1 针对低容量-大消息大小的情况。 Itinerary2 针对高容量-小消息大小的情况。 由于只有一个默认主机的适配器，所有消息均都路由使用同一台主机，从而降低性能。  
  
 **更改**  
  
 若要提高性能的动态发送端口，将适配器发送处理程序配置为使用任何主机。 在该 ESB 方案中，Itinerary1 使用 HostA 向文件共享发送数据。 Itinerary2 使用 HostB 端口发送电子邮件。  
  
## <a name="select-a-send-handler"></a>选择发送处理程序  
 创建动态单向发送端口或动态要求响应发送端口时，是可以为每个已安装的适配器配置发送处理程序。 步骤：  
  
1. 在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含发送端口的应用程序。  
  
2. 右键单击**发送端口**，单击**新建**，然后单击**动态单向发送端口**或者**动态要求响应发送端口**。  
  
3. 在中**属性**，单击**配置**。  
  
    使用默认发送处理程序列出的适配器。 单击向下箭头以选择其他主机。  
  
4. 单击**确定**保存设置。  
  
5. 取消登记并重新登记新的动态发送端口。  
  
6. 重新启动原始主机实例。  
  
7. 重新启动新的主机实例。  
  
   其他发送端口配置选项包括：  
  
- [如何配置传输高级选项的发送端口](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
- [如何为发送端口配置备份传输选项](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
- [如何配置发送端口的出站映射](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
- [如何为发送端口配置筛选器](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
- [如何为发送端口分配证书](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
- [如何为发送端口配置跟踪](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
  不同的主机可以细微调整。 以下链接讨论了性能优化：  
  
  [一般 BizTalk Server 优化](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
  [管理 BizTalk Server 性能设置](http://go.microsoft.com/fwlink/p/?LinkId=267704)