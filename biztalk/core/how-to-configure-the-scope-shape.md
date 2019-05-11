---
title: 如何配置作用域形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5627f3463b1d2797abe742462cf60e948e8bbb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340418"
---
# <a name="how-to-configure-the-scope-shape"></a>如何配置作用域形状
**作用域**形状提供了上下文框架对其内容。 第一个块**作用域**形状是上下文模块或正文中，作用域的基本操作发生; 它类似于 try/catch 语句的 try 块。 正文的后面，**作用域**形状还可以包含一个或多个异常处理程序模块和补偿模块。  
  
> [!NOTE]
>  在多台计算机环境中位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和协调世界时 (UTC) 与在两台计算机上，SQL Server 位于不同计算机上则**超时**为配置的属性**作用域**形状可能会早于预期由于 UTC 时间上触发[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 计算机不同步。 请注意，这不是一个时区问题如协调世界时是不受时区影响。  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a>若要将作用域形状配置为事务边界  
  
1.  在属性窗口中设置**事务类型**属性设置为**原子**或**长期**。  
  
    > [!NOTE]
    >  业务流程本身必须是为了使您可以将事务类型设置为原子或运行时间长时间运行的事务。  
  
2.  如果**事务类型**设置为**原子**，然后在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |批处理|布尔值，该值确定是否可以进行此事务与其他事务批处理业务流程的多个实例。 在 BizTalk Server 中永远不会使用此属性，因为 BizTalk Server 不支持跨多个实例的业务流程的批处理原子事务。 此属性将在未来版本中弃用。|  
    |隔离级别|确定数据访问并发事务的程度：<br /><br /> 读取已提交，以防止访问并行事务中的数据修改，直到提交所选的事务。 此选项是 Microsoft SQL Server 默认设置。<br />-可重复读-为所选的事务完成之前要求读的锁定。<br />可序列化，以允许并行事务进行数据修改所选的事务完成之前。 此选项是限制性最强的隔离级别。|  
    |重试|布尔值，该值确定发生错误时是否重试此事务。 默认值是 **True**秒。 **注意：** 原子事务将重试，如果引发了 Microsoft.XLANG.BaseTypes.RetryTransactionException，或如果业务流程引擎不能存储其状态或提交事务。|  
    |超时|确定以秒为单位由于处于非活动状态的事务失败之前的时间。 如果不希望使用超时，则设置此属性的值为 0。 **注意：** 这是 DTC 超时，并不强制使用业务流程引擎。 仅对于原子事务，该引擎将不会中断事务。 它继续，通常直到做出的承诺，此时它无法提交，仅当参与 DTC 事务通过其内部的对象之一。|  
  
3.  如果**事务类型**设置为**长期**，然后在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |超时|确定在秒钟，直到事务超时并被视为失败的事务的时间。 如果不希望使用超时，则设置此属性的值为 0。|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a>若要配置作用域形状以包含本地变量  
  
1.  双击业务流程视图窗口中的作用域。  
  
2.  右键单击作用域下的变量文件夹，然后单击**新变量**。  
  
3.  在"添加变量"步骤 2 中，然后[如何添加业务流程变量](../core/how-to-add-orchestration-variables.md)。