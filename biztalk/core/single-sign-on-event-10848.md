---
title: "单一登录： 事件 10848 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9511d46a43180626a31f36c9f887b0ac532e088a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10848"></a>单一登录： 事件 10848
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10848|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS|  
|消息正文|此应用程序不允许直接密码同步，因为其字段不明确。|  
  
## <a name="explanation"></a>解释  
 如果存在两个以上字段，则必须只对一个字段标记为密码同步。  
  
## <a name="user-action"></a>用户操作  
 若要更正这种情况下，必须删除该应用程序，并重新创建它，以便它遵循这些准则。