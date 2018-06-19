---
title: 查询和检索列表时的限制 |Microsoft 文档
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
ms.openlocfilehash: 0f2e0f813a793aa05756ef52925081375203f2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262333"
---
# <a name="limitations-when-querying-and-retrieving-lists"></a>查询和检索列表时的限制
博士 Edwards OneWorld 通信体系结构是单个消息，单答复体系结构。 不能返回数组或消息的列表。 基础代码是 c + +，其中带有指向单个结构的指针的调用，在结构中，进行更改，然后退出。  
  
## <a name="querying-and-retrieving-lists"></a>查询和检索列出  
 您不能查询和检索基于 Microsoft BizTalk 适配器用于博士 Edwards OneWorld 由于博士 Edwards OneWorld 业务函数体系结构方面的限制的搜索条件的记录的列表。  
  
 在博士 Edwards OneWorld 使用专有 （和复杂） 内部函数调用的一组提供数据库连接。 这些调用通过要求非常显式和低级别的调用，以创建要检索或更新的列的列表屏蔽基础数据库版本，创建专用的结构的排序或所选内容。 不通过 Java （或任何其他） 公开的 Api 集连接方法;因此，不能通过业务函数处理记录集。  
  
 博士 Edwards OneWorld 工具集，在中，你可以创建处理单个记录或运行的业务函数上的一组记录;但是，访问的外部博士 Edwards OneWorld 工具的项列表会更加困难。  
  
 若要解决此问题，可以创建返回基于查询的记录密钥的列表的自定义业务函数。 你必须分段列表中，因为 JDENET （博士 Edwards OneWorld 内部消息传递 API 的专有） 具有用于管理大型或不受限制的结果集的消息缓冲区大小的限制。 客户端代码必须循环执行对业务函数中，连续调用 （循环），直到指出该列表完整返回一个指示符。  
  
## <a name="controlling-iteration"></a>控制迭代  
 对博士 Edwards OneWorld 业务功能的所有调用都是无状态;因此，业务功能无法维护打开的游标，并在请求中返回更多的行。 定位信息必须传递到博士 Edwards OneWorld XE 业务功能在每次调用。  
  
 下面是用于控制迭代技术的列表：  
  
-   在博士 Edwards OneWorld 一侧，写入结果设置为临时存储文件，它返回可以连续调用，以及记录编号，以将光标提供的 ID （如文件名称或作业数量）。 在基于传入的记录数量的列表中放置任何后续调用。  
  
    > [!NOTE]
    >  通过用于博士 Edwards OneWorld 的 BizTalk Adapter 调用可以进行负载平衡;但是，它们最终由提供服务的凭据和被调用的业务函数的单个应用程序服务器。 因此，如果调用创建的服务器上的临时文件，其他调用进行处理由同一个服务器。 有关详细信息，请参阅 JD Edwards OneWorld CNC Guides（《JD Edwards OneWorld CNC 指南》）中的 Object Configuration Mapping（“对象配置映射”）。  
  
-   可在第二个和后续调用中，返回位置信息 （如主键值），并且可以基于为一个附加参数的密钥重新颁发查询。 BizTalk 适配器博士 Edwards OneWorld 浏览代码的存储库中使用此方法。  
  
    > [!NOTE]
    >  前两个技术的建议的方法是使用主键值，然后重新发出查询。 此方法要求最小的代码量，并且对数据库中会将优化和缓存的负担。  
  
-   调用应用程序可以存储的主键 （如的交叉引用） 的列表。 例如，如果客户关系管理 (CRM) 系统创建 customer 记录，且然后将其添加到博士 Edwards OneWorld 使用业务函数调用，将添加一个客户记录的业务函数设置 AN8 字段 （短地址数） 的值并显示在返回的缓冲区。 可以然后写入到的引用字段上的原始的客户记录，此数字，或为其存储到自定义的交叉引用表。  
  
-   博士 Edwards OneWorld 中的所有主记录的大部分具有查找或替换密钥的概念。 此密钥可用于存储从调用的系统的密钥信息。 业务函数可以对博士 Edwards OneWorld 端执行查找。 参数传递给业务函数来创建 customer 记录，长的密钥的值设置。  
  
 有关这些概念的详细信息，请参阅 JD Edwards OneWorld 帮助系统中的“Interoperability”（互操作性）主题。  
  
## <a name="see-also"></a>另请参阅  
 [规划和体系结构](../core/planning-and-architecture17.md)