---
title: 单一登录： 事件 10821 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2200011e-3e4f-4fe4-b01f-f3b86cdc96db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1b9d5499ac11f29034f0110e0ff0fe6850f66a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988078"
---
# <a name="single-sign-on-event-10821"></a>单一登录： 事件 10821
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   |                             企业单一登录                              |
| 产品版本 |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    事件 ID     |                                       10821                                        |
|  事件源   |                                       ENTSSO                                       |
|    组件    |                                        N/A                                         |
|  符号名称  |                     ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER                     |
|  消息正文   | 无法删除适配器，因为它当前已分配给一个组适配器。 |
  
## <a name="explanation"></a>解释  
 无法删除适配器，因为它当前已分配给一个组适配器。  
  
## <a name="user-action"></a>用户操作  
 取消分配该适配器，然后删除它。