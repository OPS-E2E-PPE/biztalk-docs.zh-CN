---
title: 业务流程变量类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f388cf112a84d1e6ace00d3930cd6d815d728d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264573"
---
# <a name="orchestration-variable-types"></a>业务流程变量类型
您可以声明以下预定义类型的变量：  
  
|||||  
|-|-|-|-|  
|boolean|byte|char|datetime|  
|decimal|double|int16|int32|  
|int64|long|sbyte|single|  
|string|timespan|uint16|uint32|  
|uint64||||  
  
 还可以声明您的项目所引用的基于 .NET 的任意类型的变量。  
  
## <a name="considerations-for-declare-orchestration-variables"></a>声明业务流程变量的注意事项  
 声明业务流程变量时，请注意以下事项：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持多值的上下文属性对于某些基于内容的路由方案，但你无法在业务流程中使用此类属性。  
  
-   为支持业务流程的挂起和解除冻结，所有业务流程变量必须能够保持自身的状态。  通常，这是通过对变量的类型或类进行序列化或流式处理来实现的。  
  
-   这些基于 .NET 的类型（类）必须是可序列化的类。  通过使用“[Serializable]”属性进行声明或通过显式实现 ISerializable .NET 接口（在 System.Runtime.Serialization 命名空间中），可以实现这些类型（类）的序列化。  
  
-   如果基于 .NET 的类型实际上是某个底层 COM 组件的运行库可调用包装 (RCW)，那么该 COM 组件必须实现相应接口，RCW 才能成为可序列化的 .NET 类（例如 IPersistStream、IPersistStreamInit）。  
  
-   由于所有基于 .NET 的类型（或底层 COM）均在业务流程内部执行，这些类型中的方法不能延迟业务流程的执行（例如，通过资源争用等方式）。  而且，这些类型实现对资源的任何消耗将影响运行调用业务流程的主机实例。