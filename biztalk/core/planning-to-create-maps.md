---
title: 计划创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, planning
ms.assetid: e86af976-b989-4e24-80d5-3a9a3ac4e443
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb421f7ca67fce583fde7a7b85e653209da6d5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981846"
---
# <a name="planning-to-create-maps"></a>计划创建映射
使用映射可以将符合某种架构的输入消息转换为符合另一种架构的输出消息。 这些转换可能很简单也可能相当复杂，涉及到信息的计算与合并。  

 下表列出了在规划创建映射时需要回答的一些问题。  


|       规划问题        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                  建议                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 需要创建哪些映射？ |                                                                                                                  列出要使用 Microsoft® [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理的业务文档的列表。 此列表中应包括如采购订单、发票、发货确认等信息。 列表也可能包括多个此类每个业务文档，如您从一个贸易合作伙伴接收采购订单的结构不同于采购订单的结构时从另一个贸易合作伙伴接收。<br /><br /> 检查列表并决定哪些文档需要使用不同的格式，哪些文档最适合转换为通用格式。                                                                                                                   |
|     需要在何处使用映射？      |                                                                                                                                                                                                                                                                                                                                                                                            可以在发送端口、接收端口和代表业务程序的业务流程中使用映射。 请考虑希望或需要在何处转换文档。                                                                                                                                                                                                                                                                                                                                                                                            |
| 是否有旧的映射要转换？ | [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 中创建的映射应在未修改的情况下进行迁移。 应分配足够的时间来测试所迁移的映射。 但是，较旧版本的 BizTalk 中创建的映射可能不一定是打开中 BizTalk Server 中。 **注意：** 以前的版本中创建映射[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]可能中正常运行[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年。 但是，这些映射可能无法打开 BizTalk Server 中。 <br /><br /> 映射包含**脚本**functoid 或自定义 functoid 可能需要额外的工作。 有关详细信息，请参阅[迁移 Functoid](../core/migrating-functoids.md)。 |

## <a name="see-also"></a>请参阅  
 [有关地图](../core/about-maps.md)   
 [“迁移”Functoid](../core/migrating-functoids.md)