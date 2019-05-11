---
title: 单一登录：Event 10819 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f338b78cd9c19b337b83eb829736cb7e81612e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396640"
---
# <a name="single-sign-on-event-10819"></a>单一登录：事件 10819
## <a name="details"></a>详细信息  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10819                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    不可用                                    |
|  符号名称  |                         ENTSSO_E_MAPPING_CONFLICT                         |
|  消息正文   | 因为存在映射冲突未更新外部帐户。 |
  
## <a name="explanation"></a>解释  
 因为存在映射冲突未更新外部帐户。  
  
## <a name="user-action"></a>用户操作  
 如果这是预期的行为，则不不需要任何操作，此消息仅供参考。 如果应允许映射冲突然后相应地配置应用程序。  
  
 有关映射冲突的详细信息，请参阅**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。