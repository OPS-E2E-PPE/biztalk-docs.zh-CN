---
title: 运行解析程序服务示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9d7e3e4d4bce4e46653f7b650004928368eced
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294749"
---
# <a name="running-the-resolver-service-sample"></a>运行解析程序服务示例
解析程序服务示例演示以下方案：  
  
-   解决服务终结点 URI 从 UDDI3 使用绑定密钥  
  
-   解决服务终结点 URI 从 UDDI3 使用分类搜索  
  
-   解决使用静态冲突解决程序的转换 （BizTalk 映射类型）  
  
-   解决服务终结点使用静态冲突解决程序的 URI  
  
-   解决服务终结点使用 XPath 表达式的 URI  
  
-   解决使用静态路线冲突解决程序路线  
  
-   解决使用一个路线静态 (Unity) 冲突解决程序路线  
  
-   解决使用 BRE （BRI 冲突解决程序） 路线  
  
-   解决 BRE （BRI 冲突解决程序） 使用消息路线  
  
-   解决服务终结点 URI 使用 BRE  
  
-   解决使用 BRE 转换  
  
 **若要运行使用解析程序服务的 ASMX 实现的所有解析方案**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹中，，然后双击文件 RunTestClient_ASMX.cmd。  
  
3.  打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。  
  
 **若要运行使用解析程序服务的 WCF 实现的所有解析方案**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹中，，然后双击文件 RunTestClient_WCF.cmd。  
  
3.  打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。