---
title: 单一登录：Event 10611 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b0e07a7d3151cf4a25334d1d6b01fb46c3ad75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397720"
---
# <a name="single-sign-on-event-10611"></a>单一登录：事件 10611
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                         企业单一登录                                                                                                         |
| 产品版本 |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    事件 ID     |                                                                                                                   10611                                                                                                                   |
|  事件源   |                                                                                                                  ENTSSO                                                                                                                   |
|    组件    |                                                                                                                    不可用                                                                                                                    |
|  符号名称  |                                                                                                     SSO_INFO_SERVICE_STARTING_NO_SSL                                                                                                      |
|  消息正文   | SSO 服务正在 starting.%r<br /><br /> 计算机名称: %1 %r<br /><br /> SQL Server 名称: %2 %r<br /><br /> SSO 数据库名称: %3 %r<br /><br /> 不使用 SSL。 有关如何保护 SQL Server 连接，请参阅文档的详细信息。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 服务正在启动而无需使用安全套接字层 (SSL)。 建议为 SQL，SSO 服务从保护您的连接。  
  
## <a name="user-action"></a>用户操作  
 请参阅文档，[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)  
  
 .