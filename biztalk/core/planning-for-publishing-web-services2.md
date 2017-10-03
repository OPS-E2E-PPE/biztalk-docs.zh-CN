---
title: "规划发布 Web Services2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0b9d593a3309f7b4477f2fa735f7e265b614c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-publishing-web-services"></a>规划发布 Web 服务
您可以从业务流程访问 Web Services， 还可以使用 BizTalk Web Services 发布向导发布 Web Services。  
  
 下表列出了在规划 Web Services 时需要回答的一些问题。  
  
|规划问题|建议|  
|-----------------------|--------------------|  
|是否已构建 BizTalk Server 项目？|请注意，在运行 BizTalk Web Services 发布向导之前，必须构建 BizTalk Server 项目。|  
|是否已将系统配置为可以运行 Web Services？|在运行 BizTalk Web Services 发布向导之前，必须在计算机上启用 Web Services。 有关启用你的 Web 服务的系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。|  
|是否已验证架构仅包含有效的 XML 字符和元素？|Web Services 不支持 Chinese、Japanese 或 Korean (CJK) Unified Ideograph Extension A 字符。 同时，某些 XML 架构 (XSD) 元素也存在一定限制。 有关有效的 XML 字符和受支持的元素和注意事项的元素的详细信息，请参阅[注意事项发布 Web 服务时](../core/considerations-when-publishing-web-services.md)。|  
|BizTalk Server 项目中的任一消息类型是否使用用户定义的 .NET 类？|您必须在全局程序集缓存 (GAC) 中安装包含可供消息类型引用的用户定义的 .NET 类的程序集。|  
|执行 Web 客户端使用的提供的凭据**WindowsUser**上下文属性？|通过使用已发布的 Web 服务使用的 Web 客户端提供的凭据**WindowsUser**上下文属性。 参与方解析也可使用此属性。 如果你设置了方使用**WindowsUser**上下文属性和 Web 客户端使用具有匹配方的凭据的 Web 服务、 BizTalk Server 标识作为来自相应的预定义方的消息。 有关与管道组件的参与方解析的详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [发布 Web 服务](../core/publishing-web-services.md)