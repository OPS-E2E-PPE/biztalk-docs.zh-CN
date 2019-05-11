---
title: HTTP 适配器示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1747a9bb28bc84dc0f6772435411d07557bf463e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383115"
---
# <a name="http-adapter-samples"></a>HTTP 适配器示例
本节包含演示使用 BizTalk HTTP 适配器时的高级的功能的示例。  
  
> [!NOTE]
>  运行此示例之前，需要执行以下步骤：  
> 
> 1. 打开 IIS，添加 ISAPI 和 CGI 限制：  
> 
>    在左面板中，单击计算机名称，然后单击"ISAPI 和 CGI 限制"的右侧面板中，然后添加 ISAPI 或 CGI 路径：  
> 
>    在 64 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll  
> 
>    在 32 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll  
> 
>    检查允许的扩展路径或执行。  
>    2.  左面板中，单击"HTTPRequestResponseSample"，中间面板中，单击"处理程序映射"，然后单击"添加脚本映射"，使用以下设置：  
> 
>    请求路径： btshttpreceive.dll  
> 
>    可执行文件：  
> 
>    64 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\  
> 
>    在 32 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\  
> 
>    请求限制：  
> 
>    谓词：发布  
> 
>    访问：脚本  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HTTPSolicitResponse](../core/httpsolicitresponse.md)  
  
-   [HTTPRequestResponse](../core/httprequestresponse.md)