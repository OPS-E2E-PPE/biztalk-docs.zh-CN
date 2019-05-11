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
ms.openlocfilehash: 0cb73c44cde4d2839633179f8c6f9274999fcb68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395000"
---
# <a name="planning-to-create-maps"></a>计划创建映射
使用映射来转换输入的消息的输出消息符合不同的架构符合一个架构。 这些转换可能很简单，也可能相当复杂，涉及计算和的信息合并。  

 下表列出了一些需要你计划创建映射时，必须解决的问题。  


|       规划问题        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                  建议                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 我需要创建哪些映射？ |                                                                                                                  您将处理与 Microsoft 的业务文档的列表设为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 例如，此列表可能包括采购订单、 发票、 发货确认等。 列表也可能包括多个此类每个业务文档，如您从一个贸易合作伙伴接收采购订单的结构不同于采购订单的结构时从另一个贸易合作伙伴接收。<br /><br /> 浏览列表并决定哪些文档需要以不同的格式，或哪些文档最适合转换为通用格式。                                                                                                                   |
|     其中需要映射？      |                                                                                                                                                                                                                                                                                                                                                                                            可以使用映射在发送端口、 接收端口和业务流程中表示业务流程。 请考虑希望或需要将文档转换的位置。                                                                                                                                                                                                                                                                                                                                                                                            |
| 是否有旧的映射要转换？ | 中创建的映射[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年应迁移而无需修改。 分配足够的时间来测试所迁移的映射。 但是，较旧版本的 BizTalk 中创建的映射可能不一定是打开中 BizTalk Server 中。 **注意：** 以前的版本中创建的映射[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]中可能正常运行[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年。 但是，这些映射可能无法打开 BizTalk Server 中。 <br /><br /> 映射包含**脚本**functoid 或自定义 functoid 可能需要额外的工作。 有关详细信息，请参阅[迁移 Functoid](../core/migrating-functoids.md)。 |

## <a name="see-also"></a>请参阅  
 [有关地图](../core/about-maps.md)   
 [“迁移”Functoid](../core/migrating-functoids.md)