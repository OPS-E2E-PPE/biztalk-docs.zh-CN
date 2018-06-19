---
title: MQSeries 适配器属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQXQH_MsgDesc_ReplyToQMgr property [MQSeries adapters]
- UserHttpHeaders property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQXQH_MsgDesc_MsgId property [MQSeries adapters]
- MQXQH_MsgDesc_ReplyToQ property [MQSeries adapters]
- SubmissionHandle property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- EnableChunkedEncoding property [MQSeries adapters]
- MQSeries adapters, properties
- MQXQH_MsgDesc_CorrelId property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: c3cfbc8c-4c9b-431e-b0b6-4c065a69ce6b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263565"
---
# <a name="mqseries-adapter-properties"></a>MQSeries 适配器属性
若要在 BizTalk 业务流程中访问 MQSeries 标头属性，必须向项目添加对 MQSeries.dll 程序集的引用。 此程序集位于 MQSeries 适配器的安装位置，例如 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
 引用 MQSeries 属性架构后，其他上下文属性可供各种 BizTalk Server 开发工具 (例如，**消息分配**形状中业务流程设计器)。  
  
> [!NOTE]
>  在使用 MQSeries 标头属性时，请确保按照 IBM WebSphere MQ 文档中的指南操作。  
  
 适配器会自动升级一些 MQSeries 属性。 应用程序和自定义组件必须避免对这些属性进行降级。 您可以通过使用自定义管道组件来升级其他属性。 自动升级的属性如下所示：  
  
-   **BizTalk_CorrelationID**  
  
-   **MQMD_CorrelId**  
  
-   **MQMD_MsgId**  
  
-   **MQMD_ReplyToQ**  
  
-   **MQMD_ReplyToQMgr**  
  
-   **MQXQH_RemoteQMgrName**  
  
-   **MQXQH_RemoteQName**  
  
-   **MQXQH_MsgDesc_CorrelId**  
  
-   **MQXQH_MsgDesc_MsgId**  
  
-   **MQXQH_MsgDesc_ReplyToQ**  
  
-   **MQXQH_MsgDesc_ReplyToQMgr**  
  
## <a name="in-this-section"></a>本节内容  
  
-   [数据类型转换的属性](../core/data-type-conversion-of-properties.md)  
  
-   [与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)  
  
-   [MQSeries 上下文属性](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a>另请参阅  
 [配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)