---
title: 转换 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5812cd340d2f7e7a47f54e6e77ff39c144542615
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399658"
---
# <a name="the-transformation-web-service"></a>转换 Web 服务
转换 Web 服务允许外部应用程序提交到 ESB 应用程序文档，并让它使用已部署的 Microsoft BizTalk 映射转换。 转换代理与此服务不路由消息通过 BizTalk Messagebox 数据库。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称是**ESB。TransformServices**和**ESB。TransformServices.WCF**分别和服务公开一个方法：  
  
-   **转换。** 此方法将作为参数**字符串**，其中包含要转换的消息和一个**字符串**，其中包含部署在 BizTalk 映射的完全限定的名称。 该方法返回**字符串**，其中包含转换后的文档。 使用字符串参数，可降低风险异类环境; 中的互操作性问题但是，请记住，这是 Web 服务，因此，应避免使用它来转换 （在 BizTalk 转换服务更好地适合大型文档） 的大型文档。  
  
> [!NOTE]
>  默认情况下，转换 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。 应配置服务，因此它需要 SSL 客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问 BizTalk Server 之间的连接控制列表 (ACL) 权限。