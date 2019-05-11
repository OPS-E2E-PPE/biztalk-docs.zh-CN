---
title: 单一登录：Event 10538 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d1a1b8b09d9bc4725c55060aebe705f256e691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250381"
---
# <a name="single-sign-on-event-10538"></a>单一登录：事件 10538
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10538                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    CO                                     |
|  符号名称  |                           SSO_WARN_APP_DISABLED                           |
|  消息正文   | 应用程序当前被 disabled.%r<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件表明 SSO 关联应用程序已禁用了由应用程序管理员。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 请联系你的应用程序管理员联系以启用 SSO 关联应用程序。 这可以使用 SSO 管理工具 （GUI 或命令行）。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)  

- [如何禁用关联应用程序](../core/how-to-disable-an-affiliate-application.md)
