---
title: 单一登录： 事件 10601 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34711cf02711ec0ee2a259cc7d8f8fca9c87b7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270701"
---
# <a name="single-sign-on-event-10601"></a>单一登录： 事件 10601
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10601|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_INVALID_FLAGS|  
|消息正文|指定的标志无法用于创建此类型的应用程序。<br /><br /> 有关详细信息，请参阅文档。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 指定的标志: %2 %r<br /><br /> 允许的标志: %3 %r<br /><br /> 不允许的标志： %4|  
  
## <a name="explanation"></a>解释  
 指定的标志无法用于创建此类型的应用程序。 警告中列出了相关的应用程序，以及允许和不允许的标志。  
  
## <a name="user-action"></a>用户操作  
 遵循警告消息中列出的准则来重新创建应用程序。