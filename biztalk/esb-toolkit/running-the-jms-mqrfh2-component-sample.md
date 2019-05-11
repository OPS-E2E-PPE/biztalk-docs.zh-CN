---
title: 运行 JMS MQRFH2 组件示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44f4b48c-398a-4ec1-a033-1fc4a76a305c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f22daf7e5b3372bc5eb952139aeac94c971b8048
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242824"
---
# <a name="running-the-jms-mqrfh2-component-sample"></a>运行 JMS MQRFH2 组件示例
JMS MQRFH2 组件示例包含三个部分：  
  
-   [运行 JMS MQRFH2 Header 保留示例](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md)。 本部分演示了完全保真的标头保留，因为在 IBM WebSphere MQ，通过 ESB 和 Microsoft BizTalk Server，并返回到 IBM WebSphere MQ 间传递消息。  
  
-   [从业务流程示例运行 Header 属性](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md)。 本部分演示了如何 ESB 业务流程内部的代码可以访问 MQRFH2 标头属性。 在这种情况下，代码使用标头属性来指定目标队列名称。  
  
-   [运行大容量加载基于内容的路由示例](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md)。 本部分演示了大容量加载的队列消息，并显示应用程序如何将消息路由到目标队列指定消息内容的一部分。