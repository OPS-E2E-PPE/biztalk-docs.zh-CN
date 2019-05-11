---
title: 单一登录：Event 10605 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181191572cd433ebcd6ab2356a1cb0455c6a4c09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397777"
---
# <a name="single-sign-on-event-10605"></a>单一登录：事件 10605
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                       企业单一登录                                                                       |
| 产品版本 |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    事件 ID     |                                                                                 10605                                                                                 |
|  事件源   |                                                                                ENTSSO                                                                                 |
|    组件    |                                                                                  不可用                                                                                  |
|  符号名称  |                                                                         SSO_ERROR_DTC_IMPORT                                                                          |
|  消息正文   | 无法导入 DTC 事务。 请检查 MSDTC 正确配置用于远程操作。 请参阅 details.%r 文档<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 没有与 Microsoft 分布式事务处理协调器 (MSDTC) 的问题。  
  
## <a name="user-action"></a>用户操作  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。