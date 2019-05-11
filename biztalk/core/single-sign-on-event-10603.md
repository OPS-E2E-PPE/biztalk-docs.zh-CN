---
title: 单一登录：Event 10603 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57b75ba39be2b49606b351573f50c677077aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397783"
---
# <a name="single-sign-on-event-10603"></a>单一登录：事件 10603
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             企业单一登录                                                              |
| 产品版本 |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    事件 ID     |                                                                       10603                                                                        |
|  事件源   |                                                                       ENTSSO                                                                       |
|    组件    |                                                                        不可用                                                                         |
|  符号名称  |                                                                 SSO_WARN_DB_ACCESS                                                                 |
|  消息正文   | 无法访问 SSO 数据库。 如果此状况继续存在，SSO 服务将脱机 offline.%r<br /><br /> %1.%r<br /><br /> SQL 错误代码： %2 |
  
## <a name="explanation"></a>解释  
 SSO 数据库不可用。  
  
## <a name="user-action"></a>用户操作  
 检查警告中包含的 SQL 错误代码。 这可能会提供一些指导。 如果没有，请与 Microsoft 产品支持服务联系。