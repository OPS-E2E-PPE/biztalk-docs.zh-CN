---
title: 点到点解析终结点以及转换要求 |Microsoft 文档
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
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294461"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a>点到点解析终结点以及转换要求
在使用这种情况下，Web 服务客户端调用 Web 服务，而无需通过 ESB。 两个点进行直接通信，但客户端进行的调用之前，它必须解析 Web 服务的终结点。 对 Web 服务的调用可以是单向或请求-响应。 实现此目的的一种方法是使用 ESB，动态解析功能，如图 1 中所示。  
  
 ![点 &#45; 到 &#45;终结点解析点](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3 PointToPoint")  
  
 **图 1**  
  
 **解决使用 UDDI 终结点**  
  
 附带的解析程序服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 此示例演示如何调用 ESB 解析程序服务，以执行解析，使你可以测试解决方法，如你正在开发的后端存储，例如通用、 描述、 发现和集成 (UDDI)，XML 路径语言 (XPath) 的内容静态的或 BizTalk Server 业务规则引擎中的策略。  
  
 有关详细信息，请参阅[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)。