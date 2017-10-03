---
title: "示例操作错误处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-operations-error-handler"></a>操作错误处理程序示例
示例操作错误处理程序有三个主要的程序集： **OperationsClient**， **OperationsHandler**，和**OperationsServer**。  
  
 解决方案配置的适配器以使用**OpsClient**对象在**OperationsClient**程序集。 如你所料， **OpsClient**对象实现**IOpsAIC**接口。  
  
 **OpsClient**对象使用**IOperationsSystem**接口来调用**OpsHandler**对象通过[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。 **IOperationsSystem**接口如下所示：  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 **OperationsServer**，控制台应用程序，侦听请求**OpsHandler**对象，并充当服务器[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。 调用**执行**方法**OpsClient**对象反过来调用**Post**方法**OpsHandler**对象。  
  
 **OpsHandler**方法响应通过写出使用其自变量字符串**跟踪**对象。 这会将错误发布到控制台。 有关详细信息**跟踪**对象，请参阅中的"跟踪类"[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。  
  
> [!NOTE]
>  此处的模式是，在相同**OrderHandler**接口在其中指定客户端与远程对象之间的方法调用。 不存在，但是，其他之间的间接层此处**OpsClient**和**OpsHandler**。  
  
## <a name="see-also"></a>另请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)