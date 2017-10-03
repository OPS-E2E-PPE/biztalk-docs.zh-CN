---
title: "单一登录： 事件 10605 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e7d0fb4befaacd8734f866f2c11c7446d4e5854
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10605"></a>单一登录： 事件 10605
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10605|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_DTC_IMPORT|  
|消息正文|无法导入 DTC 事务。 请检查是否正确配置 MSDTC 以用于远程操作。 有关详细信息，请参阅文档。%r<br /><br /> 错误代码： %1|  
  
## <a name="explanation"></a>解释  
 没有问题与 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
## <a name="user-action"></a>用户操作  
 有关 MSDTC 问题的帮助，请参阅[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)。