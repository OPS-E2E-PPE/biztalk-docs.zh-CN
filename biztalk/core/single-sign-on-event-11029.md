---
title: 单一登录：事件 11029 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4498b2a326138095bca4476c6a992e4259e81227
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379935"
---
# <a name="single-sign-on-event-11029"></a>单一登录：事件 11029
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              企业单一登录                                               |
| 产品版本 |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                              |
|    事件 ID     |                                                        11029                                                         |
|  事件源   |                                                        ENTSSO                                                        |
|    组件    |                                                         不可用                                                          |
|  符号名称  |                                               SSO_INFO_CASE_SENSITIVE                                                |
|  消息正文   | SSO 数据库是区分大小写。 SSO 服务器将在区分大小写模式下运行。 请参阅 details.%r 文档 |
  
## <a name="explanation"></a>解释  
 默认情况下，SSO 服务器不区分大小写。 但是，SQL Server SSO 数据库已配置为区分大小写，因此 SSO Server 也将在区分大小写的模式下运行。  
  
## <a name="user-action"></a>用户操作  
 请注意此时指定应用程序的名称和外部帐户名，因为现在它们是区分大小写。 有关详细信息，请参阅[SSO 服务器](../core/sso-server.md)。