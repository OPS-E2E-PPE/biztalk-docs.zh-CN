---
title: ESB 管道互操作组件 |Microsoft Docs
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
ms.openlocfilehash: 794ce6407d10fc820444384550357f10d24f7723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024236"
---
# <a name="esb-pipeline-interop-components"></a>ESB 管道互操作组件
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供支持组件和服务，包括以下：  
  
- **JMS 管道组件。** 这些组件识别、 验证和公开元数据和遵守使用 IBM MQ Series 的消息传递系统的 JMS MQRFH2 格式的消息的内容。 此功能允许[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]应用程序接收消息并通过 MQ Series 将消息发送到 JMS 系统。 组件会自动将提升到，标头信息和从消息内容对其进行降级。  
  
- **Namespace 管道组件。** 这些组件可以添加或删除命名空间中的 XML 消息的内容。 这样，应用程序来修复冲突的命名空间或添加缺少的命名空间以避免在 Messagebox 数据库和应用程序业务流程中的命名空间冲突。 组件还允许 BizTalk Server 使用 POX (Plain Old XML)，而无需修改外部发布系统。  
  
  ESB 管道组件的详细信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。