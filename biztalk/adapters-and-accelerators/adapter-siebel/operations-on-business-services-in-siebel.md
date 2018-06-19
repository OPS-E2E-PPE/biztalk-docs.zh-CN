---
title: 对 Siebel 中的业务服务的操作 |Microsoft 文档
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
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221941"
---
# <a name="operations-on-business-services-in-siebel"></a>对 Siebel 中的业务服务的操作
Siebel 业务服务是可以在 Siebel 中直接调用的业务方法的集合。 业务组件和业务对象关联到特定的数据和 Siebel 中的表，而业务服务调用的对象执行特定任务。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]呈现业务服务方法，因为操作名称和支持 IN、 OUT 和 INOUT 参数。 例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面**ATPRunCheck**作为操作的方法。 此方法属于**ATP**业务服务。  
  
 某些条件[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]时使用 Siebel 业务服务有一定：  
  
-   如果 Siebel 业务服务方法所采用的没有指定的数据类型的参数，该适配器将作为文本公开自变量。  
  
-   Siebel 业务服务方法参数可以是以下类型：  
  
    -   字符串 （作为 xsd: string 公开）  
  
    -   数 (公开为 xsd： 十进制)  
  
    -   日期 （时间部分必须设置为 00:00:00 的化，使用模式方面，该值指示作为公开）  
  
    -   层次结构 （公开为 xsd: string）  
  
    -   集成对象 （作为 xsd: string 公开）  
  
     此外，业务服务方法验证传递给自变量的值是否符合相应的类型。 因此，如果业务服务方法接受或返回不符合相应的自变量类型的值，该适配器可能会引发异常。 如果在调用业务服务方法，该适配器未成功，则可能会失败的架构验证。  
  
 有关的信息：  
  
-   执行对使用 BizTalk Server 业务服务的操作，请参阅[调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。  
  
-   消息结构和 SOAP 操作对业务服务执行操作，请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。  
  
## <a name="see-also"></a>另请参阅  
 [连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)