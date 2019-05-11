---
title: ESB 路线选择器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcce1fb4ab067e4620bbbca9134e5ac5f5c58889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399764"
---
# <a name="the-esb-itinerary-selector-component"></a>ESB 路线选择器组件
ESB 路线选择器组件允许不具有 SOAP 标头通过选择相应的服务器端路线的冲突解决程序帮助的消息通过 ESB 路线的传入消息。 该组件还用于使用 SOAP 标头来定义的名称和版本的路线，如客户端请求的消息。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**ItinerarySelector**组件的 BizTalk Server 管道组件文件夹中。  
  
## <a name="how-it-works"></a>其工作原理  
 ESB 路线选择器组件是可以仅在接收管道中驻留的 Microsoft BizTalk 管道组件。 该组件选择使用服务器端路线中处理消息。 消息通过接收管道中的组件，该组件读取其配置，并使用**ResolverConnectionString**属性来调用要查找适当的路线时要使用的正确解析程序处理消息。 然后，路线选择器组件执行路线管道组件以验证消息，并将提升以确保该消息将持续到下一个处理阶段所必需的属性与相同的步骤。  
  
## <a name="using-the-esb-itinerary-selector-component"></a>使用 ESB 路线选择器组件  
 您可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。 当此组件配置有中 WCF 接入点、 名称和版本 （如 SOAP 标头中所示），客户端请求路线的旅行计划静态解析程序将从消息上下文中检索并用于选择相应路线。  
  
## <a name="component-properties"></a>组件属性  
 ESB 路线选择器组件公开三个公共属性：  
  
-   **IgnoreErrorKey**。 此属性定义是否，如果由解析程序返回错误，消息应处理没有路线的情况下 (当设置为 **，则返回 True**) 或已挂起。  
  
-   **ItineraryFactKey**。 这表示由包含所选路线的实际 XML 解析程序返回的字典中的项。 通常情况下， **Resolver.Itinerary**，除非使用自定义冲突解决程序。  
  
-   **ResolverConnectionString**。 这是一个包含冲突解决程序可以使用选择的名称 / 值对的冲突解决程序连接字符串和/或查找路线。