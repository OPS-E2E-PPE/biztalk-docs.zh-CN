---
title: "单一登录： 事件 10819 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f2a98586d9c139674c64db6ca03aaa6abd6ba6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10819"></a>单一登录： 事件 10819
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10819|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_MAPPING_CONFLICT|  
|消息正文|由于存在映射冲突，因此未更新外部帐户。|  
  
## <a name="explanation"></a>解释  
 由于存在映射冲突，因此未更新外部帐户。  
  
## <a name="user-action"></a>用户操作  
 如果这是预期的行为，则不需要执行任何操作，此消息只是提供信息。 若要允许映射冲突，请对应用程序进行相应配置。  
  
 有关映射冲突的详细信息，请参阅**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。