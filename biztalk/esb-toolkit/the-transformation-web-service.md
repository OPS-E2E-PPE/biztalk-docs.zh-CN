---
title: 转换 Web 服务 |Microsoft 文档
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
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294869"
---
# <a name="the-transformation-web-service"></a>转换 Web 服务
转换 Web 服务使外部应用程序提交到 ESB 应用程序的文档，并让它使用已部署的 Microsoft BizTalk 映射转换。 与不同的是转换代理，此服务不路由通过 BizTalk 消息框数据库的消息。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称**ESB。TransformServices**和**ESB。TransformServices.WCF**分别和服务公开一种方法：  
  
-   **转换。** 此方法使用作为参数**字符串**，包含要转换的消息和**字符串**，其中包含部署在 BizTalk 映射的完全限定的名称。 该方法返回**字符串**包含转换后的文档。 使用字符串参数降低了异类环境; 中的互操作性问题的风险但是，请记住，这是 Web 服务，因此应避免使用它来转换大型文档 （BizTalk 中的转换服务更适合大型文档）。  
  
> [!NOTE]
>  默认情况下，转换 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。 你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问你 BizTalk Server 之间的连接控制列表 (ACL) 权限。