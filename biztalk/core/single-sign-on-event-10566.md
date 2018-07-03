---
title: 单一登录： 事件 10566 |Microsoft Docs
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
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015086"
---
# <a name="single-sign-on-event-10566"></a>单一登录： 事件 10566
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                     企业单一登录                                                                      |
| 产品版本 |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    事件 ID     |                                                                               10566                                                                                |
|  事件源   |                                                                               ENTSSO                                                                               |
|    组件    |                                                                                N/A                                                                                 |
|  符号名称  |                                                                  SSO_WARN_CANNOT_UPDATE_APP_FLAGS                                                                  |
|  消息正文   | 您无法更新此应用程序的某些指定标志。 这些标志将会被忽略。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 指定标志掩码： %2 |
  
## <a name="explanation"></a>解释  
 应用程序中的某些标志无法更改。 （例如，不允许将应用程序类型从“个人”更改为“组”。）此应用程序的标志在警告文本中列出。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。