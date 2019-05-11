---
title: 示例操作错误处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad378180fbf6b29ce69c21a5546243d8891fd81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379946"
---
# <a name="the-sample-operations-error-handler"></a>示例操作错误处理程序
示例操作错误处理程序具有三个主要的程序集：**OperationsClient**， **OperationsHandler**，和**OperationsServer**。  
  
 解决方案配置为使用的适配器**OpsClient**对象中**OperationsClient**程序集。 如您所料**OpsClient**对象将实现**IOpsAIC**接口。  
  
 **OpsClient**对象使用**IOperationsSystem**接口来调用**OpsHandler**对象，通过[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。 **IOperationsSystem**接口如下所示：  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 **OperationsServer**，控制台应用程序，侦听请求**OpsHandler**对象，并充当服务器[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。 调用**Execute**方法**OpsClient**对象又调用**Post**方法**OpsHandler**对象。  
  
 **OpsHandler**方法将响应通过编写出使用其参数字符串**跟踪**对象。 这将发布到控制台错误。 有关详细信息**跟踪**对象，请参阅中的"Trace 类"[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。  
  
> [!NOTE]
>  此处的模式是，在相同**OrderHandler** ，接口将在其中指定客户端与远程对象之间的方法调用。 没有，但是，其他层之间的间接下面**OpsClient**并**OpsHandler**。  
  
## <a name="see-also"></a>请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)