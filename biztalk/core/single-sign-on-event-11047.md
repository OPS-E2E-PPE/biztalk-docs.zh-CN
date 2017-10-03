---
title: "单一登录： 事件 11047 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e16c2fa899642f20c67e171d0bd8f9536b6add2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11047"></a>单一登录： 事件 11047
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11047|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_SSOSQL_FAILED|  
|消息正文|无法创建 SSOSQL。 若要解决此问题，请重新安装 SSO，或尝试在 Visual Studio 命令提示符下输入“regasm SSOSQL.dll”。%r<br /><br /> 错误代码： %1|  
  
## <a name="explanation"></a>解释  
 这可能是由于安装错误所致。  
  
## <a name="user-action"></a>用户操作  
 若要解决此问题，请重新安装 SSO，或尝试在 Visual Studio 命令提示符下输入“regasm SSOSQL.dll”。