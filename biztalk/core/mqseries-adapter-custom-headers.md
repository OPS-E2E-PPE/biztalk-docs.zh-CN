---
title: MQSeries 适配器自定义标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 758b0bb33be70f681d4d7ef732e50555d6eca026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323788"
---
# <a name="mqseries-adapter-custom-headers"></a>MQSeries 适配器自定义标头
由于在 MQSeries 消息中所使用的标头结构，你必须管理任何你想要使用的自定义标头。 自定义标头必须是消息正文，以便避免干扰 MQSeries 标头的处理的一部分。 请确保您避免降级自动升级的属性之一。 有关自动升级的属性的详细信息，请参阅[MQSeries 适配器属性](../core/mqseries-adapter-properties.md)。  
  
 反过来，消息正文中的自定义标头合并需要进行其他处理。 一种解决方案是处理的应用程序管道中的自定义标头。 接收管道提取自定义标头信息并将升级为上下文属性的信息。 同样，发送管道使用对应于自定义标头上下文属性，并将消息的正文中的属性降级。  
  
 有关在管道组件中使用自定义标头的示例，请参阅[MQSSendPipelineComponent （BizTalk Server 示例）](../core/mqssendpipelinecomponent-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)