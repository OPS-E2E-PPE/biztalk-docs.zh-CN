---
title: "HTTP 适配器示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eb20ba2a9dc91f9b8bd17442f8bd3e7986fcfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-samples"></a>HTTP 适配器示例
本部分中包含的示例演示 BizTalk HTTP 适配器的高级功能。  
  
> [!NOTE]
>  在运行此示例之前，需要执行以下步骤：  
>   
>  1.  打开 IIS，添加 ISAPI 和 CGI 限制：  
>   
>      单击左侧面板中的计算机名称，再单击右侧面板中的“ISAPI 和 CGI 限制”，然后添加 ISAPI 或 CGI 路径：  
>   
>      在 64 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \HttpReceive64\BTSHTTPReceive.dll  
>   
>      在 32 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \HttpReceive\BTSHTTPReceive.dll  
>   
>      检查允许的扩展路径或执行。  
> 2.  单击左侧面板中的“HTTPRequestResponseSample”，再单击中间面板中的“处理程序映射”，然后单击“添加脚本映射”并进行以下设置：  
>   
>      请求路径：BTSHTTPReceive.dll  
>   
>      可执行文件：  
>   
>      在 64 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \HttpReceive64\  
>   
>      在 32 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \HttpReceive\  
>   
>      请求限制：  
>   
>      谓词： POST  
>   
>      访问： 脚本  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HTTPSolicitResponse](../core/httpsolicitresponse.md)  
  
-   [HTTPRequestResponse](../core/httprequestresponse.md)