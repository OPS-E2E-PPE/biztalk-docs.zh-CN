---
title: 单一登录：Event 10855 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9519453d0209caf46fa75c1bce52d60fe792d0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306652"
---
# <a name="single-sign-on-event-10855"></a>单一登录：事件 10855

|                 |                                                                        |
|-----------------|------------------------------------------------------------------------|
|  产品名称   |                       企业单一登录                        |
| 产品版本 |       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    事件 ID     |                                 10855                                  |
|  事件源   |                                 ENTSSO                                 |
|    组件    |                                  不可用                                   |
|  符号名称  |                    ENTSSO_E_PASSWORD_FILTER_FAILED                     |
|  消息正文   | 无法返回凭据，因为密码筛选器失败。 |

## <a name="explanation"></a>解释  
 密码筛选器无效。 最可能的原因是，该筛选器手动创建的但并不推荐。  

## <a name="user-action"></a>用户操作  
 创建密码筛选器再次使用创建筛选器向导。