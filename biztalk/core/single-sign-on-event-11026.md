---
title: 单一登录：事件 11026 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9443afe9fd9101d5ede8e5e05adfc6f65d877c90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379982"
---
# <a name="single-sign-on-event-11026"></a>单一登录：事件 11026
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                企业单一登录                                                                                                                                |
| 产品版本 |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    事件 ID     |                                                                                                                                          11026                                                                                                                                          |
|  事件源   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    组件    |                                                                                                                                           不可用                                                                                                                                           |
|  符号名称  |                                                                                                                             SSO_WARN_EXISTING_GROUP_MAPPING                                                                                                                             |
|  消息正文   | 无法创建新的组映射，因为与现有的映射冲突。 请删除现有映射，然后尝试 again.%r<br /><br /> 现有映射: %1 %r<br /><br /> 新的映射: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 应用程序名称： %4 |
  
## <a name="explanation"></a>解释  
 最可能的原因是您的系统使用了旧版本的企业单一登录，并且旧的组应用程序。  
  
## <a name="user-action"></a>用户操作  
 删除并重新创建警告中建议的映射。 如果此操作失败，可能需要升级到最新版本的企业单一登录。