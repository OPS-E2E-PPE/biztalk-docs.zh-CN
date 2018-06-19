---
title: 单一登录： 事件 10552 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa08100af7a7d324c7a84d15ac741ba858f60d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269989"
---
# <a name="single-sign-on-event-10552"></a>单一登录： 事件 10552
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10552|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED|  
|消息正文|映射服务器访问被拒绝。%r|  
  
## <a name="explanation"></a>解释  
 发出了一个从客户端到映射服务器的调用，但是该调用未被接受。 这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请记录下错误日志中的信息，然后与产品支持服务部门联系。