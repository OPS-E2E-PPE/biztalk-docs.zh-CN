---
title: 单一登录： 事件 10855 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89bbdb3c004dc7533be9b7f6371ec69b67bde532
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276917"
---
# <a name="single-sign-on-event-10855"></a>单一登录： 事件 10855
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10855|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_PASSWORD_FILTER_FAILED|  
|消息正文|无法返回凭据，因为密码筛选器出现故障。|  
  
## <a name="explanation"></a>解释  
 密码筛选器无效。 最可能的原因是手动创建的该筛选器，这不是推荐的方法。  
  
## <a name="user-action"></a>用户操作  
 再次使用“创建筛选器”向导创建密码筛选器。