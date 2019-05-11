---
title: 如何使用端口类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, port types
- port types, deleting
- port types, Web
- port types, request-response
- orchestrations, ports
- port types, modifier
- port types
- ports, port types
- port types, one-way
ms.assetid: 78ac731e-c330-4888-a9ee-10523fef8ed0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace5ba21f0e7615e2db9ecc192e696b229a0f3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332883"
---
# <a name="how-to-work-with-port-types"></a>如何使用端口类型
端口类型由通信模式、 一系列操作 （请求或响应），以及这些操作可处理的消息类型组成。 该模式可以是单向或请求-响应 （双向），并且该端口类型上定义的所有操作必须使用相同的模式。 请注意，端口类型与方向无关： 方向在各端口上指定。  
  
 定义端口类型的作用域**的类型修饰符**属性。 端口类型可以是公共、 私有或内部。 如果是公共的则对与该业务流程进行交互的任何人都可见。 如果它是私有的则在同一个项目和命名空间中的其他业务流程可见。 如果它在内部，端口类型为仅在项目内可见。 由于端口类型定义包括消息类型，消息类型的作用域必须包含的任何端口类型的使用它。  
  
> [!NOTE]
>  端口类型可以应用到任意数量的端口。 您可以将端口视为端口类型的实例。  
  
> [!NOTE]
>  端口类型本身并没有通信方向;在各端口上设置方向。  
  
### <a name="to-add-a-request-response-port-type"></a>若要添加请求-响应端口类型  
  
1.  在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建请求响应端口类型**。  
  
     **端口类型**节点会展开，如果处于折叠状态，且新的请求-响应端口类型添加一个带有一个默认操作。  
  
2.  指定端口类型的名称。  
  
3.  定义一个或多个端口操作。  
  
     可以命名你的端口操作，但在其选择从另一个项目，你将看到它们仅作为"请求"和"响应。 如果从另一个项目中选择端口操作，请验证它具有正确的消息类型。  
  
### <a name="to-add-a-one-way-port-type"></a>若要添加单向端口类型  
  
1.  在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建单向端口类型**。  
  
     **端口类型**节点将展开，如果处于折叠状态，并新建单向端口类型添加一个带有一种默认操作。  
  
2.  指定端口类型的名称。  
  
3.  定义一个或多个端口操作。  
  
### <a name="to-add-a-web-port-type"></a>若要添加 Web 端口类型  
  
-   添加对包含 Web 服务的代理类的程序集的项目引用。 有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。  
  
### <a name="to-remove-a-port-type"></a>若要删除的端口类型  
  
-   在业务流程视图窗口中，右键单击要删除，然后单击的端口类型**删除**。  
  
    > [!NOTE]
    >  如果端口类型正在使用中，则删除它会影响任何端口的配置为使用该的配置。  
  
    > [!NOTE]
    >  另一个业务流程中定义了项显示为只读的。  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a>若要设置端口类型的类型修饰符  
  
-   在属性窗口中，设置以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |类型修饰符|确定端口类型的作用域：<br /><br /> 私有 — 对此端口类型的访问仅限于包含模块。<br /><br /> 公共 — 对此端口类型的访问没有限制。<br /><br /> 内部 — 对此端口类型的访问仅限于同一项目中的模块。|  
  
## <a name="see-also"></a>请参阅  
 [通信模式](../core/communication-pattern.md)   
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [在业务流程中使用端口](../core/using-ports-in-orchestrations.md)