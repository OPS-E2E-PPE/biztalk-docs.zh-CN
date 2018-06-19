---
title: 使用管道组件来缓存请求作出响应一条路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b6822a4f4ca70e88ee86277e00645982595b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294989"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a>使用管道组件来缓存请求作出响应一条路线
通过提交消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线上负载增加可以通过单向路线或双向 （请求-响应） 路线。 若要支持请求-响应路线，路线机制必须提供 BizTalk 动态请求-响应发送端口的缓存。  
  
 ESB 路线缓存管道组件将存储到缓存中的出站消息上下文路线，并将其附加到响应消息中;它将返回发送端口的使用可配置的缓存密钥。 这允许路线的服务处理和执行后续后路线中的当前服务定义的服务。  
  
 默认情况下，ESB 路线缓存管道组件的驻留在 ItineraryReceiveSend BizTalk 管道中，如图 1 中所示。 此管道应只可用作接收管道请求-响应发送端口。  
  
 ![管道组件缓存](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "第四章第 4 PipelineComponentCache")  
  
 **图 1**  
  
 **ESB 路线缓存管道组件**  
  
 使用 BizTalk 中的 ESB 路线缓存管道组件接收请求-响应发送端口的管道。