---
title: "SOA BizTalk 管理点的概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-soa-biztalk-management-point"></a>SOA BizTalk 管理点的概述
与 SOA 服务管理器和 Workbench 产品本机集成 BizTalk 管理点。 不像典型 Web 服务的管理点，此实现器关联与 Microsoft BizTalk Server 环境中，按 BizTalk Server 表示由提供的服务接收位置和发送端口。 由于任意性质接收位置和发送端口 （配置免受各种 BizTalk Server 适配器），这些服务不一定与 Web 服务相关联，但可以将它们视为 Web 服务根据 SOA 服务管理器和 SOA Workbench。  
  
 图 1 显示 SOA 服务管理器 Web 应用程序显示的示例应用程序的 Workbench 页。 左侧树视图允许用户浏览应用程序和 BizTalk Server 中安装的服务和右侧窗格中，用户可以查看应用程序详细信息、 操作、 访问端口、 类别、 规则和监视信息。  
  
 ![Ch9 &#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")  
  
 **图 1**  
  
 **SOA 服务管理器在 Workbench 页上显示可用的监视功能**  
  
 你可以监视所有应用程序 （所有发送端口和接收位置） 中的操作或特定操作;Workbench 显示了一个通过所选传递的消息列表发送端口和接收位置。 双击列表中的消息时，该 Workbench 将显示消息，并将其上下文属性的详细的信息 （如果启用了录制）。 或者，您可以选择特定的服务和监视器中实时通过该服务传递的消息。