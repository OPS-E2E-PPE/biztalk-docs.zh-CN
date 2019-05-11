---
title: 在 Siebel 业务服务上的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19ff7bbc86931523cef0845720d855e8f3f2a4f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371191"
---
# <a name="operations-on-business-services-in-siebel"></a>在 Siebel 业务服务上的操作
Siebel 业务服务是一系列可以在 Siebel 中直接调用的业务方法。 业务组件和业务对象是关联到特定的数据和 Siebel 中的表，而业务服务调用的对象执行特定任务。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]呈现业务服务方法，如操作名称，并支持 IN，OUT 和 INOUT 参数。 例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面**ATPRunCheck**作为操作的方法。 此方法属于**ATP**业务服务。  
  
 某些条件的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]时使用的 Siebel 业务服务施加了：  
  
- 如果 Siebel 业务服务方法不具有指定的数据类型的参数，该适配器以文本形式公开参数。  
  
- Siebel 业务服务方法参数可以是以下类型之一：  
  
  - 字符串 （公开为 xsd: string）  
  
  - 数字 (公开为 xsd: decimal)  
  
  - 日期 （时间部分必须设置为 00:00:00 化，使用模式方面，该值指示作为公开）  
  
  - 层次结构 （公开为 xsd: string）  
  
  - 集成对象 （公开为 xsd: string）  
  
    此外，业务服务方法验证传递的参数的值是否符合相应的类型。 因此，如果业务服务方法接受或返回不符合相应的参数类型的值，该适配器可能会引发异常。 如果适配器未成功调用业务服务方法中，架构验证可能会失败。  
  
  有关信息：  
  
- 在执行业务服务使用 BizTalk Server 上的操作，请参阅[调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。  
  
- 消息结构和 SOAP 操作对业务服务执行操作，请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。  
  
## <a name="see-also"></a>请参阅  
 [连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)