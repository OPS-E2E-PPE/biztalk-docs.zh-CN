---
title: 由于类型名冲突无法继续 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ced6de4-0950-498e-a548-5c85419726d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742d537f2329c53cd974abbaac9a6b9f7f8f5126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008478"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a>由于类型名冲突无法继续
## <a name="details"></a>详细信息  
  
|                 |                                                                                       |
|-----------------|---------------------------------------------------------------------------------------|
|  产品名称   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |              [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    事件 ID     |                                           0                                           |
|  事件源   |                                           0                                           |
|    组件    |                                           0                                           |
|  符号名称  |                                           0                                           |
|  消息正文   | 由于类型名称冲突而无法继续。 名称"{0}"命名空间中已存在 |
  
## <a name="explanation"></a>解释  
 此错误表明定义的同一命名空间中的多个项目具有同一名称。  
  
## <a name="user-action"></a>用户操作  
 重新命名相同命名空间中的项目或将其置于不同命名空间中。