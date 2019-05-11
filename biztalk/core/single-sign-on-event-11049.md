---
title: 单一登录：事件 11049 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a41631744b25149135de4e3c65b5ccd436dcd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400993"
---
# <a name="single-sign-on-event-11049"></a>单一登录：事件 11049
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             11049                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              不可用                               |
|  符号名称  |                      SSO_ERROR_DTC_FAILED                      |
|  消息正文   | 无法获取 MSDTC。 SSO 需要使用 MSDTC 才能正常工作。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 系统无法连接到 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
## <a name="user-action"></a>用户操作  
 检查 MSDTC 是否当前正常运行。  
  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。