---
title: 查询和检索列表时的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, querying limitations
- querying, limitations [JD Edwards OneWorld adapters]
ms.assetid: 1b6f5d2a-d1e2-4c78-8f4a-f00d10f008b9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27880dc3f603f39c9cb9f71207edc1926df4df7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002822"
---
# <a name="limitations-when-querying-and-retrieving-lists"></a>查询和检索列表时的限制
JD Edwards OneWorld 通信体系结构是一种单消息、 单回复体系结构。 不能返回数组或消息的列表。 基础代码是 c + +，其中具有指向一个结构的指针调用、 在结构中，进行更改，然后退出。  
  
## <a name="querying-and-retrieving-lists"></a>查询和检索列出  
 您不能查询和检索的记录使用用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，由于与 JD Edwards OneWorld 业务函数体系结构的限制的搜索条件的列表。  
  
 在 JD Edwards OneWorld 数据库连接是通过使用一套专有 （和复杂） 的内部函数调用提供的。 这些调用屏蔽基础的数据库版本的要求非常显式和低级别的调用，以创建要检索或更新的列的列表，并创建专用的结构的排序或所选内容。 未通过 Java （或任何其他） 公开的 Api 集的连接方法;因此，不能通过业务功能处理记录集。  
  
 JD Edwards OneWorld 工具集，在中，你可以创建业务功能，处理的单个记录或通过使用上一组记录;但是，访问 JD Edwards OneWorld 工具以外的文件项的列表，更加困难。  
  
 若要解决此问题，可以创建一个自定义业务函数，返回基于查询的记录密钥的列表。 您必须段在列表中，，因为 JDENET （JD Edwards OneWorld 内部消息传递 API 的专有） 具有用于管理大型或不受限制的结果集的消息缓冲区大小限制。 客户端代码必须循环访问 （循环） 连续调用业务函数，直到指出该列表完整返回一个指示符。  
  
## <a name="controlling-iteration"></a>控制迭代  
 对 JD Edwards OneWorld 业务功能的所有调用都是无状态;因此，业务功能无法维护打开的游标，并在请求中返回更多的行。 定位信息必须传递到 JD Edwards OneWorld XE 业务功能在每次调用。  
  
 下面是用于控制迭代技术的列表：  
  
- 在 JD Edwards OneWorld 端，编写将结果集返回可以连续调用，以及记录号将游标定位在指定的 ID （如文件名称或作业数） 的临时存储文件。 基于传入的记录数的列表中的定位任何后续调用。  
  
  > [!NOTE]
  >  通过用于 JD Edwards OneWorld 的 BizTalk 适配器的调用可以进行负载平衡;但是，它们最终由基于凭据和被调用的业务函数的单个应用程序服务器提供。 因此，如果调用创建的服务器上的临时文件，其他调用会通过在同一台服务器提供服务。 有关详细信息，请参阅 JD Edwards OneWorld CNC Guides（《JD Edwards OneWorld CNC 指南》）中的 Object Configuration Mapping（“对象配置映射”）。  
  
- 位置信息 （如主键值） 可以返回在第二个和后续调用中，并可以基于其他参数作为密钥重新发出查询。 用于 JD Edwards OneWorld 的 BizTalk 适配器浏览代码存储库中使用此方法。  
  
  > [!NOTE]
  >  前两个技术的建议的方法是使用主键值，然后重新发出查询。 此方法要求最小的代码量，并将对数据库的优化和缓存的负担。  
  
- 调用应用程序可以存储 （如的交叉引用） 的主键的列表。 例如，如果客户关系管理 (CRM) 系统创建客户记录，然后将其添加到使用业务函数调用的 JD Edwards OneWorld 业务函数，用于添加客户记录设置 AN8 字段 （短地址号码） 的值返回缓冲区中。 此数字然后可以写入到一个引用字段上的原始客户记录，或存储到一个自定义交叉引用表。  
  
- JD Edwards OneWorld 中的所有主记录的大多数都具有查找或备用键的概念。 可以使用此密钥存储在调用系统中的密钥信息。 在 JD Edwards OneWorld 端业务功能可以执行查找。 当传递到业务函数，以创建客户记录的参数时，长的密钥值设置。  
  
  有关这些概念的详细信息，请参阅 JD Edwards OneWorld 帮助系统中的“Interoperability”（互操作性）主题。  
  
## <a name="see-also"></a>请参阅  
 [规划和体系结构](../core/planning-and-architecture17.md)