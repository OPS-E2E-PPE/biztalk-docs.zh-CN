---
title: 单一登录：Event 10804 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a93cce2d1ad17248c1ad007f07c0a885b1a8fa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399515"
---
# <a name="single-sign-on-event-10804"></a>单一登录：事件 10804
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10804                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |                ENTSSO_E_INCORRECT_COMPUTER                 |
|  消息正文   |     此适配器未配置此计算机。      |
  
## <a name="explanation"></a>解释  
 每个适配器配置为在由其长名称标识的特定计算机上运行。 名称不正确，或者想要在另一台计算机上运行的适配器。  
  
## <a name="user-action"></a>用户操作  
 请参阅此适配器，以确定相应的计算机的正确名称的配置。