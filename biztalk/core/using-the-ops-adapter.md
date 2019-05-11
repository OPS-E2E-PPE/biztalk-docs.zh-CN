---
title: 使用 Ops 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b219d88ec07c63baf476cc3a3bf31775e03b2b4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246429"
---
# <a name="using-the-ops-adapter"></a>使用 Ops 适配器
业务流程管理解决方案使用 Ops 适配器来处理新的错误报告功能的错误报告。 不过，可以轻松地编写自己的并在其他解决方案中使用的适配器，该解决方案包含适配器，从示例处理程序处理消息。 有关错误报告功能的信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
> [!NOTE]
>  尽管该解决方案将适配器用于错误报告，但不限于错误处理其使用。 只要您想要执行的特定对象方法以响应一条消息，可以使用各种环境中的适配器。  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a>Ops 适配器如何处理错误报告  
 在解决方案中使用错误报告的端口最终将发送到的错误消息**BIZTALKERRORS-SP**端口。 在端口上的筛选器测试是否存在**ErrorReport.ErrorType**上下文属性。 只有错误报告消息具有此上下文属性。  
  
 **BIZTALKERRORS-SP**发送端口通过使用 XML 组装器组件将消息放在一个信封中的管道运行错误消息。 消息随后进入 Ops 适配器。  
  
 由 ErrorEnvelope 架构定义的信封被标记为接受任何类型的消息。 但是，"任何"是指任何消息类型定义中的 BizTalk 组。 如果解决方案接收未知类型的消息，这可能会产生挂起的消息。 此类消息将生成错误，并将路由到**BIZTALKERRORS-SP**端口。 反过来，消息会因为它不会已知的消息类型中管道的 XML 组装器组件中生成错误。 管道错误将挂起该消息。  
  
> [!NOTE]
>  若要处理因未知的消息类型的路由错误，必须编写一个自定义管道组件，并使用自定义管道中的组件**BIZTALKERRORS-SP**端口。 自定义组件将替换 XML 组装器组件。 自定义组件必须放**ErrorReport**信封标头中的属性并将消息添加到信封的正文。  
  
 Ops 适配器是事务性的单向发送适配器。 当适配器处理消息时，它首先加载指定的程序集，如有必要。 适配器缓存在内存中程序集，以避免加载的程序集的每个调用的开销。 它然后创建指定类的一个实例，然后使用反射来获取该对象中实现的程序集**IOpsAIC**接口。 如果所有这些都是成功，适配器调用**初始化**方法，然后调用**Execute**方法，传递错误报告消息。  
  
 如果错误调用**Execute**，适配器重新提交消息。 如果指定的类不实现**IOpsAIC**界面，或者类或程序集无法找到，则适配器将挂起该消息。  
  
> [!TIP]
>  因为适配器使用反射，所以包含类的程序集必须在全局程序集缓存 (GAC) 中。  
  
## <a name="the-iopsaic-interface"></a>IOpsAIC 接口  
 适配器需要实现的对象**IOpsAIC**接口。 该接口如下所示：  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 适配器将原始消息传递到字节数组的形式**Execute**方法。  
  
## <a name="configuring-the-adapter"></a>配置适配器  
 就像任何其他适配器配置适配器。 下表描述了适配器的配置属性：  
  
|显示名称|Description|  
|------------------|-----------------|  
|**.NET 程序集强名称**|程序集的完全限定的名称。|  
|**OpsAIC 类名**|类中实现的程序集的名称**IOpsAIC**接口。|  
|**初始化数据**|作为参数传递的字符串**初始化**类的方法。|  
  
 请注意，适配器需要程序集的完全限定的名称。 完全限定的名称是提供给程序集时将其添加到 gac 中的名称。 完全限定的名称是包含程序集的名称、 版本、 区域性和公钥标记的字符串。 您可以看到程序集的完全限定的名称使用全局程序集缓存工具 gacutil.exe。  
  
 有关完全限定的程序集名称的详细信息，请参阅.NET Framework 开发人员指南中的"程序集名称"。 有关 gacutil.exe 的详细信息，请参阅"全局程序集缓存工具 (Gacutil.exe)"中[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发人员指南。  
  
 必须将命名空间提供类名。 例如，如果此类是**OpsHandler**中**OperationsHandler**命名空间中，您将为类名作为**OperationsHandler.OpsHandler**。  
  
## <a name="see-also"></a>请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)