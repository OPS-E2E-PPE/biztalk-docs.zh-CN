---
title: 单一登录：Event 10566 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27530a47a1262cbc5baf9edede91dcee385fa91e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398780"
---
# <a name="single-sign-on-event-10566"></a>单一登录：事件 10566
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                     企业单一登录                                                                      |
| 产品版本 |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    事件 ID     |                                                                               10566                                                                                |
|  事件源   |                                                                               ENTSSO                                                                               |
|    组件    |                                                                                不可用                                                                                 |
|  符号名称  |                                                                  SSO_WARN_CANNOT_UPDATE_APP_FLAGS                                                                  |
|  消息正文   | 无法更新一些为此应用程序指定的标志。 它们将 ignored.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 指定标志掩码： %2 |
  
## <a name="explanation"></a>解释  
 不能更改应用程序中的某些标志。 （例如，它不是允许将来自单独的应用程序类型更改为组。）警告文本中指定了此应用程序的标志。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。