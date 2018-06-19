---
title: ESB 管道互操作组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf4d4353e6928b998d31e8096ee642cd80bb60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294125"
---
# <a name="esb-pipeline-interop-components"></a>ESB 管道互操作组件
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供支持组件和服务，其中包括：  
  
-   **JMS 管道组件。** 这些组件识别、 验证和公开元数据和符合使用 IBM MQ 系列消息传递系统的 JMS MQRFH2 格式的消息的内容。 此功能允许[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]应用程序接收来自消息，并通过 MQ 系列将消息发送到 JMS 系统。 组件自动提升到，标头信息，并对其进行降级从消息内容。  
  
-   **Namespace 管道组件。** 这些组件可以添加或删除命名空间中的 XML 消息的内容。 这允许应用程序来修复冲突的命名空间或添加缺少的命名空间，以防止在消息框数据库和应用程序业务流程中的命名空间冲突。 组件还允许 BizTalk 服务器而无需修改外部发布系统使用 POX (Plain Old XML)。  
  
 有关 ESB 管道组件的详细信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。