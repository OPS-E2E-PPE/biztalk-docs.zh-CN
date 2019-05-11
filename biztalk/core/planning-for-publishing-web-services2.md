---
title: 规划发布 Web Services2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1223dbb434df74728b3f7fe9b21dcecdc5378ba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395672"
---
# <a name="planning-for-publishing-web-services"></a>规划发布 Web 服务
您可以从您的业务流程访问 Web 服务。 此外可以使用 BizTalk Web Services 发布向导发布 Web 服务。  
  
 下表列出了一些需要进行 Web 服务时规划回答的问题。  
  
|规划问题|建议|  
|-----------------------|--------------------|  
|已生成了 BizTalk Server 项目？|必须构建 BizTalk Server 项目在运行 BizTalk Web Services 发布向导之前。|  
|已启用好系统以运行 Web 服务？|运行 BizTalk Web Services 发布向导之前，必须在计算机上启用 Web 服务。 有关启用 Web 服务系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。|  
|已验证您的架构包含仅有效的 XML 字符和元素？|Web 服务不支持中文、 日语或 Korean (CJK) Unified Ideograph Extension A 字符。 也有对某些 XML 架构 (XSD) 元素的限制。 有关有效的 XML 字符和受支持的元素和元素的注意事项的详细信息，请参阅[注意事项时发布 Web Services](../core/considerations-when-publishing-web-services.md)。|  
|任何在 BizTalk Server 项目中的消息类型是否使用用户定义的.NET 类？|必须安装包含用户定义的.NET 类在全局程序集缓存 (GAC) 中的消息类型引用的程序集。|  
|Web 客户端使用的提供的凭据**WindowsUser**上下文属性？|使用已发布的 Web 服务使用的 Web 客户端提供的凭据**WindowsUser**上下文属性。 参与方解析使用此属性。 如果使用您设置了参与方**WindowsUser**上下文属性和 Web 客户端使用 Web 服务使用与匹配参与方的凭据、 BizTalk Server 将消息标识为来自对应的预定义参与方。 有关参与方解析管道组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。|  
  
## <a name="see-also"></a>请参阅  
 [发布 Web 服务](../core/publishing-web-services.md)