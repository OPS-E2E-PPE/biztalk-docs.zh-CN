---
title: 单一登录： 事件 10819 |Microsoft Docs
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
ms.openlocfilehash: f196bb49cd0e5825551bbffe45757c327e2cbcca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972110"
---
# <a name="single-sign-on-event-10819"></a>单一登录： 事件 10819
## <a name="details"></a>详细信息  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10819                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    N/A                                    |
|  符号名称  |                         ENTSSO_E_MAPPING_CONFLICT                         |
|  消息正文   | 由于存在映射冲突，因此未更新外部帐户。 |
  
## <a name="explanation"></a>解释  
 由于存在映射冲突，因此未更新外部帐户。  
  
## <a name="user-action"></a>用户操作  
 如果这是预期的行为，则不需要执行任何操作，此消息只是提供信息。 若要允许映射冲突，请对应用程序进行相应配置。  
  
 有关映射冲突的详细信息，请参阅**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。