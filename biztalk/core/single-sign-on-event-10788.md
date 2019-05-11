---
title: 单一登录：Event 10788 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deeb8859-6b2e-452d-a7e5-0cb10de68bd2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2594fdaf20acb55131d928f22506c164a5c1dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394137"
---
# <a name="single-sign-on-event-10788"></a>单一登录：事件 10788
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        企业单一登录                                                         |
| 产品版本 |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    事件 ID     |                                                                  10788                                                                   |
|  事件源   |                                                                  ENTSSO                                                                  |
|    组件    |                                                                   不可用                                                                    |
|  符号名称  |                                                       ENTSSO_E_DTC_IMPORT_FAILED1                                                        |
|  消息正文   | 无法导入 DTC 事务。 请检查 MSDTC 正确配置用于远程操作。 请参阅文档了解详细信息。 |
  
## <a name="explanation"></a>解释  
 无法导入 DTC 事务。  
  
## <a name="user-action"></a>用户操作  
 检查 MSDTC 正确配置用于远程操作，并在指定计算机的更多详细信息，请参阅事件日志。  
  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。