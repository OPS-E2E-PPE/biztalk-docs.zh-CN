---
title: 单一登录： 事件 10757 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5887694e8fd307c0738fc7596c52354925bfbc7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277501"
---
# <a name="single-sign-on-event-10757"></a>单一登录： 事件 10757
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10757|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_NO_MAPPING|  
|消息正文|映射不存在。 对于配置存储应用程序，尚未设置配置信息。|  
  
## <a name="explanation"></a>解释  
 如果这是个人或组类型的应用程序，则不存在映射。  
  
 如果这是配置存储应用程序，则尚未设置配置数据。 当已重新初始化 SSO 数据库，但尚未重新初始化 BizTalk 管理数据库时，会发生此情况，反之亦然。  
  
## <a name="user-action"></a>用户操作  
 如果这是个人或组类型的应用程序，则创建所需的映射。 有关详细信息，请参阅[如何创建用户映射](../core/how-to-create-user-mappings.md)。