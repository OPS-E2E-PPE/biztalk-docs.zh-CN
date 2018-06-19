---
title: 单一登录： 事件 10555 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22cf26269a661673008a715fe0bfb2a442f30b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270325"
---
# <a name="single-sign-on-event-10555"></a>单一登录： 事件 10555
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10555|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED|  
|消息正文|密钥服务器访问被拒绝。%r<br /><br /> 客户端用户： %1|  
  
## <a name="explanation"></a>解释  
 消息已发送至服务器，但答复被阻止。 此错误可能由许多不同原因导致，如协议不正确或对服务器没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请记录下错误日志中的信息，然后与产品支持服务部门联系。