---
title: "业务流程管理解决方案中的异常处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a>业务流程管理解决方案中的异常处理
业务流程管理解决方案使用一个特殊的异常处理业务流程以及标准的 BizTalk Server 异常处理方式，对于适配器、管道、映射和路由故障，则使用新的错误报告功能。 此自定义的系统围绕**ExceptionHandler**业务流程。 此解决方案使用**ExceptionHandler** orchestration 重试操作或重试后出现临时问题可能会成功的调用。  
  
> [!NOTE]
>  你可以重新使用支持业务流程，如下代码**激活**，使用**ExceptionHandler**业务流程。 所有这些业务流程包括标题为作用域**CallingCode**与一个附加**异常**块。 中的代码替换**CallingCode**与你的代码的作用域。 **异常**块定义所有变量需调用**ExceptionHandler**业务流程。 请编辑为这些变量指定的值。  
  
 对于错误不可恢复的情况，该解决方案将使用自定义异常以及若干预定义的 BizTalk 异常。  
  
> [!NOTE]
>  该解决方案使用自定义适配器来处理某些端口故障。 关于适配器的详细信息，请参阅[Ops 适配器](../core/the-ops-adapter.md)。  
  
 本部分介绍**ExceptionHandler**业务流程和自定义的异常。 在本部分中，还对解决方案如何利用错误报告产品功能进行了简要介绍。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)  
  
-   [自定义异常](../core/custom-exceptions.md)