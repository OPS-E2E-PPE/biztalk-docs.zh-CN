---
title: "如何使用端口类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e3b4307cb9d48679ae1b90f7e02dd0288ec2957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-work-with-port-types"></a>如何使用端口类型
端口类型由通信模式、一组操作（请求或响应）和这些操作可处理的消息类型组成。 通信模式可以为单向通信或请求响应（双向）通信，在该端口类型上定义的所有操作都必须使用相同的模式。 请注意，端口类型与方向无关：方向是在各端口上指定的。  
  
 端口类型的作用域定义通过**类型修饰符**属性。 端口类型可以为公有、私有或内部。 如果端口类型为公有，则该端口类型对于与业务流程交互的所有用户均可见。 如果端口类型为私有，则该端口类型只对在同一个项目和命名空间中的其他业务流程可见。 如果端口类型为内部，则该端口类型只在项目内可见。 由于端口类型定义包括消息类型，因此消息类型作用域必须包含使用该消息类型的所有端口类型的作用域。  
  
> [!NOTE]
>  端口类型可应用到的端口数不限。 您可以将端口视为端口类型的实例。  
  
> [!NOTE]
>  端口类型本身并没有通信方向，您只能对各个端口设置方向。  
  
### <a name="to-add-a-request-response-port-type"></a>添加请求响应端口类型  
  
1.  在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建请求-响应端口类型**。  
  
     **端口类型**节点会展开，如果折叠状态，且与一个默认操作增加了新的请求-响应端口类型。  
  
2.  指定端口类型的名称。  
  
3.  定义一个或多个端口操作。  
  
     您可以对端口操作进行命名，但是当从其他项目选择这些端口操作时，这些端口操作只显示为“请求”和“响应”。 如果从其他项目选择端口操作，请验证该端口操作具有正确的消息类型。  
  
### <a name="to-add-a-one-way-port-type"></a>添加单向端口类型  
  
1.  在业务流程视图窗口中，右键单击**端口类型**，然后单击**新单向端口类型**。  
  
     **端口类型**节点会展开，如果折叠状态，且与一个默认操作增加了新的单向端口类型。  
  
2.  指定端口类型的名称。  
  
3.  定义一个或多个端口操作。  
  
### <a name="to-add-a-web-port-type"></a>添加 Web 端口类型  
  
-   添加对包含 Web Services 代理类的程序集的项目引用。 有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。  
  
### <a name="to-remove-a-port-type"></a>删除端口类型  
  
-   在业务流程视图窗口中，右键单击要删除，并依次的端口类型**删除**。  
  
    > [!NOTE]
    >  如果该端口类型正在使用，则删除该端口类型将会影响配置为使用该端口类型的所有端口的配置。  
  
    > [!NOTE]
    >  显示为只读的项目将在其他业务流程中定义。  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a>设置端口类型的类型修饰符  
  
-   在“属性”窗口中，设置以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |类型修饰符|确定端口类型的作用域：<br /><br /> 私有-为此端口类型的访问仅限于包含模块。<br /><br /> 公共-访问此端口类型不受限制。<br /><br /> 内部 — 为此端口类型的访问仅限于同一项目中的模块。|  
  
## <a name="see-also"></a>另请参阅  
 [通信模式](../core/communication-pattern.md)   
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [使用在业务流程中的端口](../core/using-ports-in-orchestrations.md)