---
title: SOA BizTalk 管理点的概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a6631135272d2e58571ebdf8c4afed95f967ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400039"
---
# <a name="overview-of-the-soa-biztalk-management-point"></a>SOA BizTalk 管理点的概述
与 SOA 服务管理器和 Workbench 产品以本机方式集成 BizTalk 管理点。 与典型 Web Services 的管理点，不同的此实现关联与服务提供的 Microsoft BizTalk Server 环境，以 BizTalk Server 接收位置和发送端口。 由于任意性质的接收位置和发送端口 （针对各种 BizTalk Server 适配器已配置），这些服务不一定与 Web 服务相关联，但可以将它们视为 Web 服务方面 SOA 服务管理器和 SOA Workbench。  
  
 图 1 显示了 SOA Service Manager Web 应用程序显示一个示例应用程序的 Workbench 页。 左侧树视图使用户能够浏览应用程序和安装 BizTalk Server 中的服务和右侧窗格中，用户可以查看应用程序详细信息、 操作、 访问端口、 类别、 规则和监视信息。  
  
 ![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")  
  
 **图 1**  
  
 **SOA 服务管理器在 Workbench 页上显示可用的监视功能**  
  
 你可以监视所有应用程序 （所有发送端口和接收位置） 中的操作或特定操作;通过所选传递的消息列表 Workbench 显示发送端口和接收位置。 双击列表中的消息时，Workbench 会显示该消息，并将其上下文属性的详细信息 （如果记录已启用）。 或者，可以通过该服务传递实时消息中选择特定的服务和监视器。