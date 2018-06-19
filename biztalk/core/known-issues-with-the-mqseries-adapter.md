---
title: 已知问题 MQSeries 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe3093416a10b6b66867dcb2e3629de8f25e5aca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262197"
---
# <a name="known-issues-with-the-mqseries-adapter"></a>MQSeries 适配器已知问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="know-issues"></a>了解问题  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a>尝试发送或接收消息时，发生访问被拒绝错误  
  
##### <a name="problem"></a>问题  
 使用 MQSeries 适配器向 MQSeries 服务器发送消息或从 MQSeries 适配器接收消息时，在事件查看器中查看时会发现应用程序日志中记录类似于以下内容的错误消息：  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  在此错误消息中， *servername*是服务器的名称和*queuename*是队列的名称。  
  
 另外，在尝试创建接收位置或发送端口（配置为使用用于 MQSeries 的 BizTalk 适配器）时，可能会在事件查看器中收到以下警告消息：  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a>原因  
 如果满足以下一个或多个条件，就会出现此问题：  
  
-   MQSeries 适配器的主机帐户没有 MQSeries 服务器上 MQSAgent COM+ 应用程序必需的权限。  
  
-   在基于 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的服务器上，MQSeries 适配器的主机帐户不是 MQSeries 服务器上 Distributed COM Users 组的成员。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用以下方法。 如果一种方法不能解决问题，请尝试另一种方法。  
  
 **方法 1： 启用 microsoft 网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机**  
  
 启用 Microsoft 网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-按照所述的步骤基于计算机[如何启用 Windows Server 2003 中的网络 COM + 访问](http://go.microsoft.com/fwlink/?LinkId=67076)。  
  
 **方法 2： 配置 MSDTC 设置**  
  
 按照中的步骤**上设置适当的 MSDTC 的安全配置选项[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** 部分[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)配置 MSDTC 设置。  
  
 **方法 3： 验证主机帐户已添加到 MQSAgent COM + 应用程序中的角色**  
  
 验证是否已将 MQSeries 适配器的主机帐户添加到在 MQSeries 服务器的 MQSAgent COM+ 应用程序中所创建的角色。 可以在组件服务管理控制台界面中进行验证。  
  
 **方法 4： 验证 MQSeries 适配器的主机帐户 Distributed COM Users 组的成员**  
  
 在基于 Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的服务器上，检查 MQSeries 适配器的主机帐户的组成员关系。 请确保该帐户的成员**Distributed COM Users** MQSAgent COM + 应用程序的安装位置的 MQSeries 服务器组。  
  
 有关在 Microsoft 中的 DCOM 安全增强功能的详细信息[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请参阅[DCOM 安全增强功能](http://go.microsoft.com/fwlink/?LinkId=67077)。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 MQSeries 适配器](../core/troubleshooting-the-mqseries-adapter.md)