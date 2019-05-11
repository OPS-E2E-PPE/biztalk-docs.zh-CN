---
title: 点到点解析的终结点和转换需求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 518604865f05019b9f466efaf9b73f767143d247
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400030"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a>点到点解析的终结点和转换需求
在此用例，Web 服务客户端调用 Web 服务，而无需通过 ESB。 两个点直接通信，但客户端进行调用之前，它必须解析 Web 服务的终结点。 对 Web 服务的调用可以是单向或请求响应。 实现此目的的一种方法是使用 ESB 的动态解析功能，如图 1 中所示。  
  
 ![点&#45;到&#45;终结点的点解决方案](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")  
  
 **图 1**  
  
 **解决使用 UDDI 的终结点**  
  
 使用提供的解析程序服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 此示例演示如何调用 ESB 解析程序服务来执行解析，这样就可以测试解决方法，在你开发的后端存储，例如通用描述、 发现和集成 (UDDI)，XML 路径语言 (XPath) 的内容静态或 BizTalk Server 业务规则引擎中的策略。  
  
 有关详细信息，请参阅[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)。