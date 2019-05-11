---
title: 单一登录：事件 10850 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd240e9176465c431ca13a5069c3d510f7c2d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306667"
---
# <a name="single-sign-on-event-10850"></a>单一登录：事件 10850
## <a name="details"></a>详细信息  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  产品名称   |                      企业单一登录                      |
| 产品版本 |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    事件 ID     |                                10850                                |
|  事件源   |                               ENTSSO                                |
|    组件    |                                 不可用                                 |
|  符号名称  |                 ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE                 |
|  消息正文   | 指定了已启用标志不能创建的应用程序。 |
  
## <a name="explanation"></a>解释  
 启用应用程序前, 有必要，以创建应用程序并输入其每个字段 （即用户 Id 和密码） 的字段信息。 不能与"已启用"字段中创建的应用程序已设置。  
  
## <a name="user-action"></a>用户操作  
 创建一次应用程序 （使用创建应用程序 API 或创建新关联应用程序向导）。 当应用程序已完成，字段填充，使应用程序。