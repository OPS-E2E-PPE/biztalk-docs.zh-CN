---
title: "配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8459debcd52ce990bc98adf3a2a2372206bae336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a>配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机
若要限制到 BizTalk 消息传送服务器的消息传送的 （发送和接收消息），你需要配置运行 MSMQT 发送和接收处理程序，仅在消息传递的服务器上运行的默认主机。  
  
### <a name="to-configure-the-default-hosts"></a>若要将默认主机配置  
  
1.  使用 BizTalk 管理控制台，从 BizTalkApplicationServer 主机中删除业务流程服务器主机实例：  
  
    -   右键单击每个主机实例，然后单击**停止**。  
  
    -   右键单击每个主机实例，然后单击**删除**。  
  
2.  使用 BizTalk 管理控制台，从 BizTalkServerIsolatedHost 主机中删除业务流程服务器主机实例：  
  
    -   右键单击每个主机实例，然后单击删除。  
  
3.  配置主机后，重新启动所有服务器上的所有主机实例。