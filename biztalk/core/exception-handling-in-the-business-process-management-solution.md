---
title: 业务流程管理解决方案中的异常处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d06209f49a4702397ea13407593d9286e1f31be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388312"
---
# <a name="exception-handling-in-the-business-process-management-solution"></a>业务流程管理解决方案中的异常处理
业务流程管理解决方案使用一个特殊的异常处理业务流程，以及标准 BizTalk Server 异常处理功能，以及适配器、 管道、 映射和路由故障，新的错误报告功能。 此自定义的系统围绕**ExceptionHandler**业务流程。 该解决方案使用**ExceptionHandler**重试操作或重试暂时性问题后可能会成功的调用的业务流程。  
  
> [!NOTE]
>  您可以重用代码从业务流程，如**激活**，使用**ExceptionHandler**业务流程。 所有这些业务流程都包括一个标题为的作用域**CallingCode**具有一个附加**异常**块。 中的代码替换**CallingCode**与您的代码的作用域。 **异常**块定义的变量需要调用所有**ExceptionHandler**业务流程。 编辑分配给变量的值。  
  
 该解决方案使用自定义异常以及几个预定义的 BizTalk 异常，对于如格式不正确的订单消息不可恢复错误的情况。  
  
> [!NOTE]
>  该解决方案使用自定义适配器来处理某些端口故障。 有关适配器的详细信息，请参阅[Ops 适配器](../core/the-ops-adapter.md)。  
  
 本部分介绍**ExceptionHandler**业务流程和自定义异常。 它还讨论了，简单地说，对解决方案如何利用错误报告产品功能。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)  
  
-   [自定义异常](../core/custom-exceptions.md)