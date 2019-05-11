---
title: 请求-响应解决方案的终结点和转换需求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ef1004d922fa8933ad021e958207ee36c91db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400213"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a>请求-响应解决方案的终结点和转换需求
在此用例，客户端应用程序提交的途径的请求消息并接收响应。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]可用作客户端和目标服务终结点之间的转存进程，并使用 ESB 解析程序和适配器框架来执行动态消息转换和路由根据选择的接入点配置，如图中所示1。  
  
 ![请求&#45;终结点响应解决方案](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")  
  
 **图 1**  
  
 **请求-响应解决方案的终结点和转换需求**  
  
 动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何将应用动态转换和解决方法用于使用 XML 路径语言 (XPath)、 通用描述、 发现和集成 (UDDI)，静态的双向方案或 BizTalk Server 业务规则引擎中的策略。  
  
 有关详细信息，请参阅双向消息传送的方案中所述[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。