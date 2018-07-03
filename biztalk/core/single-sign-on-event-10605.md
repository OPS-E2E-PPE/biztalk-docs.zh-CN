---
title: 单一登录： 事件 10605 |Microsoft Docs
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
ms.openlocfilehash: c578462759d2eeb69767d21191e028ef9e8ce1e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972510"
---
# <a name="single-sign-on-event-10605"></a>单一登录： 事件 10605
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                       企业单一登录                                                                       |
| 产品版本 |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    事件 ID     |                                                                                 10605                                                                                 |
|  事件源   |                                                                                ENTSSO                                                                                 |
|    组件    |                                                                                  N/A                                                                                  |
|  符号名称  |                                                                         SSO_ERROR_DTC_IMPORT                                                                          |
|  消息正文   | 无法导入 DTC 事务。 请检查是否正确配置 MSDTC 以用于远程操作。 有关详细信息，请参阅文档。%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 没有与 Microsoft 分布式事务处理协调器 (MSDTC) 的问题。  
  
## <a name="user-action"></a>用户操作  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。