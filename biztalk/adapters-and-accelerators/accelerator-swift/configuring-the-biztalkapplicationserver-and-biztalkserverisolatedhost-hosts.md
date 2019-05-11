---
title: 配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 462abf2b0b7f9fc0df8a1b754d0fa5803656ab88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378532"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a>配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机
若要限制到 BizTalk 消息传送服务器的消息 （发送和接收消息），需要配置的默认主机，哪些运行 MSMQT 发送并接收处理程序，仅在消息传送的服务器上运行。  
  
### <a name="to-configure-the-default-hosts"></a>若要配置的默认主机  
  
1.  使用 BizTalk 管理控制台，从 BizTalkApplicationServer 主机中删除业务流程服务器主机实例：  
  
    -   右键单击每个主机实例，然后单击**停止**。  
  
    -   右键单击每个主机实例，然后单击**删除**。  
  
2.  使用 BizTalk 管理控制台，从 BizTalkServerIsolatedHost 主机中删除业务流程服务器主机实例：  
  
    -   右键单击每个主机实例，然后单击删除。  
  
3.  配置主机后，重新启动所有服务器上的所有主机实例。