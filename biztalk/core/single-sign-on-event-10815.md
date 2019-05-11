---
title: 单一登录：Event 10815 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf4ebb92-f0fa-499c-9bda-0cde726ec98e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22da14967d42a0a20bba7a79392e87f3a0052c35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396121"
---
# <a name="single-sign-on-event-10815"></a>单一登录：事件 10815
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10815                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |                   ENTSSO_E_WRONG_SECRET                    |
|  消息正文   |                  主密钥不正确。                  |
  
## <a name="explanation"></a>解释  
 在尝试还原主密钥，你可能已指定错误的文件。  
  
## <a name="user-action"></a>用户操作  
 再次检查该文件，并确保它是正确的。