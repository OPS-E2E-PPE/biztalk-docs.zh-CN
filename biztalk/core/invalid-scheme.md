---
title: "方案无效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5736a3738a9598f4c4b419d7e291c3c3e32207f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-scheme"></a>方案无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|方案无效;预期的方案"{0}"或"{1}"|  
  
## <a name="explanation"></a>解释  
 发生以下情况之一： URI （统一资源标识符） 字段中指定的地址必须以 http:// 或 https:// 开头。 或者，该方案与传输绑定元素的实现中指定的方案不匹配。  
  
## <a name="user-action"></a>用户操作  
 输入以 http:// 或 https:// 开头的有效代理地址 URI