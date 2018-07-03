---
title: 从失败的数据库读取批说明 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e539cbc4a8a7227815c7d836b61b028bcee2f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990622"
---
# <a name="reading-batch-descriptions-from-database-failed"></a>从数据库读取批说明失败
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                 LoadBatchFiltersFailed                                 |
|  消息正文   |     从数据库中读取 BatchDescriptions 失败。 错误： {0}。 堆栈跟踪： {1}。      |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法加载为配置为比较传入消息的上下文属性的批处理指定的筛选器。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保管理数据库正在运行，并且可以连接。