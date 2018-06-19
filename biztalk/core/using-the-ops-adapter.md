---
title: 使用 Ops 适配器 |Microsoft 文档
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
ms.openlocfilehash: d93436e727265c4b381cdff72c42b3a677d0a4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288733"
---
# <a name="using-the-ops-adapter"></a>使用 Ops 适配器
业务流程管理解决方案使用 Ops 适配器处理由新的错误报告功能生成的错误报告。 该解决方案包含一个示例处理程序，用于处理来自适配器的消息，但是，您可以轻松地编写自己的处理程序，从而将适配器用于其他解决方案中。 有关错误报告功能的信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
> [!NOTE]
>  虽然该解决方案将适配器用于错误报告，但其用途并不限于错误处理。 要执行特定对象方法以响应消息时，可以将适配器用于各种情况。  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a>Ops 适配器如何处理错误报告  
 在解决方案中使用错误报告的端口最终错误将消息发送到**BizTalkErrors SP**端口。 端口上的筛选器测试是否存在**ErrorReport.ErrorType**上下文属性。 只有错误报告消息具有该上下文属性。  
  
 **BizTalkErrors SP**发送端口通过使用 XML 汇编程序组件以将消息放入信封中的管道中运行的错误消息。 消息随后进入 Ops 适配器。  
  
 由 ErrorEnvelope 架构定义的信封被标记为接受任何类型的消息。 但是，“任何”是指在 BizTalk 组中定义的任何消息类型。 如果解决方案接收到未知类型的消息，则会生成挂起消息。 此类消息将产生错误，并且将被路由到**BizTalkErrors SP**端口。 该消息还将在管道的 XML 组装器组件中生成错误，因为它不是已知的消息类型。 该管道错误将挂起该消息。  
  
> [!NOTE]
>  若要处理路由错误由于未知的消息类型，你必须编写自定义管道组件和使用自定义管道中的组件**BizTalkErrors SP**端口。 该自定义组件将替换 XML 组装器组件。 自定义组件必须放置**ErrorReport**信封标头中的属性并将消息添加到信封的正文。  
  
 Ops 适配器是事务性的单向发送适配器。 适配器处理消息时，如有必要，它会首先加载指定的程序集。 适配器在内存中缓存程序集，以避免在每次调用时加载程序集的系统开销。 它然后创建指定类的实例，然后使用反射获取的对象中实现的程序集**IOpsAIC**接口。 如果上述所有操作均成功，则适配器调用**初始化**方法，然后调用**执行**方法，并传递错误报告消息。  
  
 如果错误调用**执行**，适配器重新提交消息。 如果指定的类不实现**IOpsAIC**接口或类或程序集的找不到，该适配器将挂起消息。  
  
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
  
 适配器将原始消息传递为字节数组**执行**方法。  
  
## <a name="configuring-the-adapter"></a>配置适配器  
 配置该适配器的方法和配置其他任何适配器的方法一样。 下表介绍了该适配器的配置属性：  
  
|显示名称|Description|  
|------------------|-----------------|  
|**.NET 程序集强名称**|程序集的完全限定名。|  
|**OpsAIC 类名称**|类中实现的程序集的名称**IOpsAIC**接口。|  
|**初始化数据**|作为参数传递的字符串**初始化**类的方法。|  
  
 请注意，适配器需要程序集的完全限定名。 完全限定名是将程序集添加到 GAC 中时为其提供的名称。 完全限定名是一个包含程序集的名称、版本、区域性和公钥标记的字符串。 可以使用全局程序集缓存工具 gacutil.exe 查看程序集的完全限定名。  
  
 有关完全限定的程序集名称的详细信息，请参阅 .NET Framework 开发人员指南中的“程序集名称”。 有关 gacutil.exe 的详细信息，请参阅 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 开发人员指南中的“全局程序集缓存工具 (Gacutil.exe)”。  
  
 必须为命名空间提供类名。 例如，如果此类是**OpsHandler**中**OperationsHandler**命名空间，您将为类名作为**OperationsHandler.OpsHandler**。  
  
## <a name="see-also"></a>另请参阅  
 [Ops 适配器](../core/the-ops-adapter.md)