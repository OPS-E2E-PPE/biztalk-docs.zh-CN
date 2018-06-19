---
title: 如何配置作用域形状 |Microsoft 文档
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
ms.openlocfilehash: ef17f5d1ab94875af118d17551da4334525535fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249445"
---
# <a name="how-to-configure-the-scope-shape"></a>如何配置作用域形状
**作用域**形状提供其内容的上下文的框架。 第一个块**作用域**形状是上下文块或正文中，作用域的基本操作发生; 它是类似于在 try/catch 语句的 try 块。 以下正文，**作用域**形状可能还包含一个或多个异常处理程序块和补偿块。  
  
> [!NOTE]
>  在多个机环境中其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和协调世界时 (UTC) 是否在两台计算机上的不同，SQL Server 位于不同计算机上则**超时**为配置的属性**作用域**可能早于由于 UTC 时间应在触发形状[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 计算机不同步。 请注意，这不是一个时区问题，因为世界时不受时区影响。  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a>将作用域形状配置为事务边界  
  
1.  在属性窗口中，设置**事务类型**属性**原子**或**运行长时间**。  
  
    > [!NOTE]
    >  业务流程本身必须为长期事务，这样您才能将“事务类型”设置为“原子”或“长期”。  
  
2.  如果**事务类型**设置为**原子**，然后在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |批处理|布尔值，确定此事务是否可与多个业务流程实例中的其他事务一起成批处理。 由于 BizTalk Server 不支持对多个业务流程实例中的原子事务进行成批处理，所以 BizTalk Server 中从不使用此属性。 在将来版本中将弃用此属性。|  
    |隔离级别|确定并发事务中数据可访问的程度：<br /><br /> 读提交-若要阻止访问在并发事务中的数据进行修改，直到提交所选的事务。 此选项是 Microsoft SQL Server 的默认设置。<br />可重复的读取-所选的事务完成之前需要读取的锁。<br />序列化-以防止并发事务完成所选的事务之前进行数据修改。 此选项是最严格的隔离级别。|  
    |重试|布尔值，确定是否在出错时重试此事务。 默认值是 **True**秒。 **注意：** 原子事务将重试，如果引发了 Microsoft.XLANG.BaseTypes.RetryTransactionException，或如果业务流程引擎不能存储其状态或提交该事务。|  
    |超时|确定事务失败之前处于非活动状态的时间（以秒计）。 如果不想使用超时，可将此属性值设置为 0。 **注意：** 这的 DTC 超时，且不强制通过业务流程引擎。 仅对于原子事务，该引擎不会中断事务。 该引擎会在提交前正常运行，只有在通过 DTC 事务中的某一对象参与该事务时，该引擎才会在提交时失败。|  
  
3.  如果**事务类型**设置为**运行长时间**，然后在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |超时|确定事务超时并被视为失败事务之前经过的时间（以秒计）。 如果不想使用超时，可将此属性值设置为 0。|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a>配置作用域形状以包含局部变量  
  
1.  在“业务流程视图”窗口中，双击作用域。  
  
2.  右键单击作用域下的变量文件夹，然后单击**新变量**。  
  
3.  请在"要添加变量"步骤 2 中按[如何添加业务流程变量](../core/how-to-add-orchestration-variables.md)。