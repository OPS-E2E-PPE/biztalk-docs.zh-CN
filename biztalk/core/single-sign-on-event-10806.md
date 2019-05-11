---
title: 单一登录：Event 10806 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c7aee239e10e96147ff19ee29aa83e7578d8a80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396128"
---
# <a name="single-sign-on-event-10806"></a>单一登录：事件 10806
## <a name="details"></a>详细信息  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  产品名称   |                             企业单一登录                             |
| 产品版本 |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    事件 ID     |                                       10806                                       |
|  事件源   |                                      ENTSSO                                       |
|    组件    |                                        不可用                                        |
|  符号名称  |                         ENTSSO_E_APP_ASSIGNED_TO_ADAPTER                          |
|  消息正文   | 无法删除应用程序，因为当前已分配给某个适配器。 |
  
## <a name="explanation"></a>解释  
 分配给一个适配器时，无法删除应用程序。  
  
## <a name="user-action"></a>用户操作  
 取消分配应用程序通过该适配器，然后再删除它。