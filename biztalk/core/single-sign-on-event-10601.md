---
title: 单一登录：Event 10601 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dedc94aa8cb5881e4ef738f6414f51463684003a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397793"
---
# <a name="single-sign-on-event-10601"></a>单一登录：事件 10601
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                  企业单一登录                                                                                                                   |
| 产品版本 |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    事件 ID     |                                                                                                                            10601                                                                                                                             |
|  事件源   |                                                                                                                            ENTSSO                                                                                                                            |
|    组件    |                                                                                                                             不可用                                                                                                                              |
|  符号名称  |                                                                                                                    SSO_WARN_INVALID_FLAGS                                                                                                                    |
|  消息正文   | 指定的标志不能用于创建此类应用程序。<br /><br /> 请参阅 details.%r 文档<br /><br /> 应用程序名称: %1 %r<br /><br /> 指定的标志: %2 %r<br /><br /> 允许的标志: %3 %r<br /><br /> 不允许的标志： %4 |
  
## <a name="explanation"></a>解释  
 指定的标志不能用于创建此类应用程序。 警告中列出了而言，应用程序，以及允许的标志和无效。  
  
## <a name="user-action"></a>用户操作  
 重新创建应用程序的警告消息中所述的指导。