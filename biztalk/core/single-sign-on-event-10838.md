---
title: 单一登录：Event 10838 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e4de1c1-6529-4f97-8510-d10bf6f30ddc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11665ca8843d26af8518d391f1846ec9b3b69e70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307556"
---
# <a name="single-sign-on-event-10838"></a>单一登录：事件 10838
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              企业单一登录                                              |
| 产品版本 |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                              |
|    事件 ID     |                                                        10838                                                        |
|  事件源   |                                                       ENTSSO                                                        |
|    组件    |                                                         不可用                                                         |
|  符号名称  |                                          ENTSSO_E_MAX_SSO_DATABASE_CREATE                                           |
|  消息正文   | SSO 可以创建的最大 SQL 数据库名称长度为 123 个字符，以允许默认日志文件名称。 |
  
## <a name="explanation"></a>解释  
 SSO 可以创建的最大 SQL 数据库名称长度为 123 个字符，以允许默认日志文件名称。  
  
## <a name="user-action"></a>用户操作  
 使用符合这些准则的名称。