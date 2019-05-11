---
title: 使用 MQSeries 适配器的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 6185519c3669b61a805fb403b38ead9ad6316184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380897"
---
# <a name="known-issues-with-the-mqseries-adapter"></a>MQSeries 适配器的已知的问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="know-issues"></a>已知问题  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a>尝试发送或接收消息时，发生访问被拒绝错误  
  
##### <a name="problem"></a>问题  
 当使用 MQSeries 适配器将消息发送到或从 MQSeries 服务器接收消息时，在事件查看器应用程序日志中记录类似于以下的错误消息：  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  此错误消息中， *servername*是服务器的名称和*queuename*是队列的名称。  
  
 此外，当您尝试创建接收位置或配置为使用用于 MQSeries 的 BizTalk 适配器的发送端口，您可能会在事件查看器中收到以下警告消息：  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a>原因  
 可能出现此问题，如果一个或多个以下条件成立：  
  
- MQSeries 适配器的主机帐户没有 MQSeries 服务器的 MQSAgent COM + 应用程序所需的权限。  
  
- 上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-MQSeries 适配器不是 MQSeries 服务器上 Distributed COM Users 组的成员的基于服务器的主机帐户。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用以下方法。 如果一种方法无法解决此问题，请尝试下一个方法。  
  
 **方法 1:启用网络 COM + 访问 microsoft[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机**  
  
 Microsoft 上启用网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机中所述的步骤[如何在 Windows Server 2003 启用网络 COM + 访问](http://go.microsoft.com/fwlink/?LinkId=67076)。  
  
 **方法 2:配置 MSDTC 设置**  
  
 按照中的步骤**上设置相应的 MSDTC 安全配置选项[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** 一部分[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)配置 MSDTC 设置。  
  
 **方法 3:验证将主机帐户添加到 MQSAgent COM + 应用程序中的角色**  
  
 验证 MQSeries 适配器的主机帐户添加到在 MQSeries 服务器上的 MQSAgent COM + 应用程序中创建的角色。 可以将此验证，请在组件服务管理控制台界面中。  
  
 **方法 4:验证 MQSeries 适配器的主机帐户为 Distributed COM Users 组的成员**  
  
 在 Windows 上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于服务器上，检查 MQSeries 适配器的主机帐户的组成员身份。 请确保该帐户的成员**Distributed COM Users**安装 MQSAgent COM + 应用程序的 MQSeries 服务器组。  
  
 有关在 Microsoft 中 DCOM 安全性增强功能的详细信息[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请参阅[DCOM 安全增强功能](http://go.microsoft.com/fwlink/?LinkId=67077)。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器故障排除](../core/troubleshooting-the-mqseries-adapter.md)