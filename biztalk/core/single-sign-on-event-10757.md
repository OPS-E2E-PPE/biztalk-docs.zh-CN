---
title: 单一登录：Event 10757 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f62cdb2cbf0e5c3ba3477fdfc79376d1c22d3d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307715"
---
# <a name="single-sign-on-event-10757"></a>单一登录：事件 10757
## <a name="details"></a>详细信息  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  产品名称   |                                  企业单一登录                                   |
| 产品版本 |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    事件 ID     |                                            10757                                             |
|  事件源   |                                            ENTSSO                                            |
|    组件    |                                             不可用                                              |
|  符号名称  |                                     ENTSSO_E_NO_MAPPING                                      |
|  消息正文   | 映射不存在。 配置存储应用程序的配置信息尚未设置。 |
  
## <a name="explanation"></a>解释  
 如果这是个人或组类型的应用程序，则该映射不存在。  
  
 如果这是配置存储区的应用程序，则尚未设置的配置数据。 这可能已重新初始化 SSO 数据库，但 BizTalk 管理数据库已不是，反之亦然。  
  
## <a name="user-action"></a>用户操作  
 如果这是个人或组类型的应用程序，创建所需的映射。 有关详细信息，请参阅[如何创建用户映射](../core/how-to-create-user-mappings.md)。