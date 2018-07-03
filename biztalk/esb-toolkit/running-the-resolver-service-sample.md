---
title: 运行解析程序服务示例 |Microsoft Docs
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
ms.openlocfilehash: 21c569f0be544292b4a70d49f4c75a038e2fed65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006670"
---
# <a name="running-the-resolver-service-sample"></a>运行解析程序服务示例
解析程序服务示例演示以下方案：  

- 解析服务终结点使用的绑定键的 UDDI3 的 URI  

- 解析服务终结点 URI 从 UDDI3 使用分类搜索  

- 解决使用静态的冲突解决程序的转换 （BizTalk 映射类型）  

- 解析服务终结点 URI 使用静态的冲突解决程序  

- 解析服务终结点 URI 使用 XPath 表达式  

- 解决使用静态的旅行计划冲突解决程序路线  

- 解决使用路线静态 (Unity) 冲突解决程序路线  

- 解决路线使用 BRE （BRI 冲突解决程序）  

- 解决 BRE （BRI 冲突解决程序） 使用消息路线  

- 解析服务终结点 URI 使用 BRE  

- 解决使用 BRE 的转换  

  **若要运行使用解析程序服务的 ASMX 实现的所有解决方法方案**  

1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  

2. 在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹，并双击文件 RunTestClient_ASMX.cmd。  

3. 打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。  

   **若要运行使用解析程序服务的 WCF 实现的所有解决方法方案**  

4. 如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  

5. 在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹，并双击文件 RunTestClient_WCF.cmd。  

6. 打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。
