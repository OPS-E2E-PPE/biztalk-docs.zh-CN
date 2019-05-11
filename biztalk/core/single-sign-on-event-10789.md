---
title: 单一登录：Event 10789 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2821694e-e787-4942-8da5-4492e543b4da
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb18f1f6be9c4eae6d14e8ca662b1678be297169
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400554"
---
# <a name="single-sign-on-event-10789"></a>单一登录：事件 10789
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                    企业单一登录                                                                     |
| 产品版本 |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                    |
|    事件 ID     |                                                                              10789                                                                               |
|  事件源   |                                                                              ENTSSO                                                                              |
|    组件    |                                                                               不可用                                                                                |
|  符号名称  |                                                                   ENTSSO_E_DTC_IMPORT_FAILED2                                                                    |
|  消息正文   | 无法导入 DTC 事务。 请检查 MSDTC 正确配置用于远程操作。 查看更多详细信息的日志 （在计算机"%1"）。 |
  
## <a name="explanation"></a>解释  
 无法导入 DTC 事务。  
  
## <a name="user-action"></a>用户操作  
 检查 MSDTC 正确配置用于远程操作，并在指定计算机的更多详细信息，请参阅事件日志。  
  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。