---
title: 使用管道组件来缓存要求-响应路线 |Microsoft Docs
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
ms.openlocfilehash: 5ddb3f639286ba29e28230b53b9a8a26a8304ea1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396506"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a>使用管道组件来缓存要求-响应路线
通过提交消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线接入点即可完成单向路线或双向 （请求-响应） 路线。 若要支持请求-响应路线，路线机制必须提供 BizTalk 动态要求响应发送端口的缓存。  
  
 ESB 路线缓存管道组件将放入缓存中存储出站消息上下文中路线，并将其附加到响应消息中;使用可配置的缓存密钥的发送端口返回。 这样，路线服务来处理和执行后路线中的当前服务定义的后续服务。  
  
 默认情况下，ESB 路线缓存管道组件驻留在 ItineraryReceiveSend BizTalk 管道中，如图 1 中所示。 此管道应使用仅作为接收管道中，对于要求-响应发送端口中。  
  
 ![管道组件缓存](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")  
  
 **图 1**  
  
 **ESB 路线缓存管道组件**  
  
 使用 ESB 路线缓存管道组件在 BizTalk 接收管道要求响应发送端口。