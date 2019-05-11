---
title: 单一登录：事件 10851 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172eae8de676cb581dd07b823ab362bf1a2401b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306634"
---
# <a name="single-sign-on-event-10851"></a>单一登录：事件 10851
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10851                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        不可用                                                        |
|  符号名称  |                                     ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC                                      |
|  消息正文   | 应用程序不能分配到密码同步适配器，因为它具有直接密码同步标志设置。 |
  
## <a name="explanation"></a>解释  
 应用程序不能使用直接密码同步和密码同步适配器。  
  
## <a name="user-action"></a>用户操作  
 查看你的应用程序并确定它应具有直接密码同步。如果应该则保留标记设置，它是并不尝试分配到密码同步适配器应用程序。 如果不应，然后关闭标志并将分配到密码同步适配器根据应用程序。