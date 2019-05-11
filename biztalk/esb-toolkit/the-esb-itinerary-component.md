---
title: ESB 路线组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0e92c62f0ae764ed8123c578d7bc2975d4b10b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399800"
---
# <a name="the-esb-itinerary-component"></a>ESB 路线组件
ESB 路线组件设置与消息一起发送到 ESB 路线接入点的 SOAP 标头上下文属性。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**路线**BizTalk Server 管道组件文件夹中的管道组件。  
  
## <a name="how-it-works"></a>其工作原理  
 ESB 路线组件是可以仅在接收管道中驻留的 Microsoft BizTalk 管道组件。 它将提升从 SOAP 消息标头或组件设置到消息上下文属性的值。 您可以找到的升级中使用提供的路线接入点 Web 服务的 SOAP 标头示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 这些 Web 服务作为其协定的一部分公开的 SOAP 标头和客户端应用程序必须设置标头。 消息通过接收管道中的组件，该组件将读取 SOAP 标头值，并将升级 （写入） 到消息上下文属性。  
  
## <a name="using-the-esb-itinerary-component"></a>使用 ESB 路线组件  
 您可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。 SOAP 标头值或传入消息的上下文属性的组件设置，会自动将升级该组件。  
  
 有关如何使用此组件的示例，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。