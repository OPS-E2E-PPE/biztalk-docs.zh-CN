---
title: 单一登录： 事件 10806 |Microsoft Docs
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
ms.openlocfilehash: be61b0a48dde7b1c8de9ec716f4f9426c39fa0cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002694"
---
# <a name="single-sign-on-event-10806"></a>单一登录： 事件 10806
## <a name="details"></a>详细信息  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  产品名称   |                             企业单一登录                             |
| 产品版本 |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    事件 ID     |                                       10806                                       |
|  事件源   |                                      ENTSSO                                       |
|    组件    |                                        N/A                                        |
|  符号名称  |                         ENTSSO_E_APP_ASSIGNED_TO_ADAPTER                          |
|  消息正文   | 无法删除该应用程序，因为它当前已分配给某个适配器。 |
  
## <a name="explanation"></a>解释  
 应用程序被分配到适配器后无法删除。  
  
## <a name="user-action"></a>用户操作  
 取消将应用程序分配到适合器，然后再将其删除。