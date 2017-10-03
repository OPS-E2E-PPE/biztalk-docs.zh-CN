---
title: "ESB 路线的选择器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83cdd0b2022eb7dc4ad78e5702f5c21e4c4f432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-selector-component"></a>ESB 路线的选择器组件
ESB 路线选择器组件允许没有路线 SOAP 标头来通过 ESB，通过选择冲突解决程序的帮助消息相应服务器端路线的传入消息。 组件还用于使用 SOAP 标头来定义的名称和版本的一条路线，如客户端请求的消息。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**ItinerarySelector**组件 BizTalk Server 管道组件文件夹中。  
  
## <a name="how-it-works"></a>它是如何工作  
 ESB 路线选择器组件是可以仅位于接收管道的 Microsoft BizTalk 管道组件。 组件选择使用服务器端路线中处理消息。 消息传递中接收管道的组件，组件读取其配置和使用**ResolverConnectionString**调用正确的冲突解决程序，以查找相应路线时要使用的属性处理消息。 路线选择器组件然后执行与路线管道组件，以验证消息，并将提升确保消息继续到下一个处理阶段所需的属性相同的步骤。  
  
## <a name="using-the-esb-itinerary-selector-component"></a>使用 ESB 路线的选择器组件  
 你可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。 当使用在 WCF 提升、 名称和版本的客户端 （如在 SOAP 标头中表示） 请求路线路线静态解析程序配置此组件将可从消息上下文中检索并用于选择相应路线。  
  
## <a name="component-properties"></a>组件属性  
 ESB 路线选择器组件公开三个公共属性：  
  
-   **IgnoreErrorKey**。 此属性定义是否，如果由解析程序返回错误，消息应处理没有路线的情况下 (当设置为**True**) 或挂起。  
  
-   **ItineraryFactKey**。 这表示由包含选择路线的实际 XML 解析程序返回的字典中的键。 通常情况下， **Resolver.Itinerary**，除非使用自定义解析程序。  
  
-   **ResolverConnectionString**。 这是一个包含一个冲突解决程序可以使用选择的名称-值对的冲突解决程序连接字符串和/或查找路线。