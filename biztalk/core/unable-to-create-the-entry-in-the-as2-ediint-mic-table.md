---
title: 无法在 AS2 EDIINT MIC 表中创建条目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35dd74bc872968b22dd74826e10cb6f23ea24b5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292818"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a>无法在 AS2 EDIINT MIC 表中创建条目
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    事件 ID     |                                                                                       -                                                                                       |
|  事件源   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    组件    |                                                                                  AS2 引擎                                                                                   |
|  符号名称  |                                                                        AS2MicDataStoreCreateEntryError                                                                        |
|  消息正文   | 无法在 AS2 EDIINT MIC 表中创建条目。 这可能引起重复的 AS2-From、as2-到和 MessageID 组合写入到表。  错误： {0} |
  
## <a name="explanation"></a>解释  
 此错误表示数据库连接问题或密钥已存在于数据库表的行。 完整的错误消息应提供有关插入操作失败的原因的信息。 MDN 接收后 （无论成功还是失败），因此收到 MDN 后应该永远不会发生此错误，将删除表中的条目。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，检查有关插入操作失败的原因的信息的完整的错误消息。 在 SQL 中，在 EDIINT_MIC 表中，确定是否存在重复的 AS2-从和 AS2-到 MessageID 组合。 如果是这样，请将其删除。