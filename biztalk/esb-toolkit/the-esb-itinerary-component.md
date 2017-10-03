---
title: "ESB 路线组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80aa7c1ef4bc53ad2e2821eaf8dc4184777900a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-component"></a>ESB 路线组件
ESB 路线组件从 ESB 路线入口随消息一起发送的 SOAP 标头设置的上下文属性。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**路线**BizTalk Server 管道组件文件夹中的管道组件。  
  
## <a name="how-it-works"></a>它是如何工作  
 ESB 路线组件是可以仅位于接收管道的 Microsoft BizTalk 管道组件。 它将提升从 SOAP 消息标头或组件设置到消息上下文属性的值。 你可以找到将提升随附路线上负载增加 Web 服务中的 SOAP 标头的一个示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 这些 Web 服务公开 SOAP 标头作为其协定的一部分，并且客户端应用程序必须设置标头。 如消息传递中接收管道的组件，该组件将读取的 SOAP 标头值，并促进 （写入） 到消息上下文属性。  
  
## <a name="using-the-esb-itinerary-component"></a>使用 ESB 路线组件  
 你可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。 SOAP 标头值或传入消息的上下文属性的组件设置，会自动将升级组件。  
  
 有关如何使用此组件的示例，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。