---
title: 如何导出 BPEL4WS |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253829"
---
# <a name="how-to-export-bpel4ws"></a>如何导出 BPEL4WS
可以将现有的 BizTalk 业务流程导出到 BPEL4WS。  
  
> [!IMPORTANT]
>  此版本的 BizTalk Server 支持 BPEL4WS 1.1。 无法导入或导出 BPEL4WS 1.0。  
  
 如果要导出，BPEL4WS 编译规范要求业务流程仅包含在 XLANG/s 和 BPEL4WS 之间通用的功能或者在不影响操作的情况下可翻译成 BPEL4WS 的功能。  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a>对符合 BPEL4WS 规范的业务流程的导出限制  
  
-   不能使用调用业务流程形状或启动业务流程形状。  
  
-   不能使用转换形状。  
  
-   不能调用自定义 .NET 组件的方法。  
  
-   不能对长期事务应用超时。  
  
-   业务流程不能采用参数。  
  
-   可调用补偿处理程序不能具有参数。  
  
-   变量类型在 XPATH 中必须是受支持的。  
  
-   不能使用挂起形状。  
  
-   文本值必须是以下类型之一：  
  
     boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、string  
  
-   算术运算符只允许用于以下数字类型的操作数：  
  
     byte、sbyte、int32、uint32、int64、uint64、single、double  
  
-   关系运算符不能应用于 char 类型。  
  
-   不能引用表达式中的 servicelink 属性。  
  
-   你无法执行任何操作之间**发送**形状和**接收**使用相同的出站请求-响应端口的形状。  
  
-   不能间接引用 Web Services，例如引用包含引用的其他项目。 必须在项目中显式引用 Web Services。  
  
-   不能在延迟中指定常数 DateTime 或 TimeSpan。 而是在 System.Xml 命名空间中使用以下转换类之一：  
  
     对于常数 DateTime，使用 System.Xml.XmlConvert.ToDateTime，例如 System.Xml.XmlConvert.ToDateTime("2004-04-15")  
  
     对于常数 TimeSpan，使用 System.Xml.XmlConvert.ToTimeSpan，例如 System.Xml.XmlConvert.ToTimeSpan("2004-04-15")  
  
> [!NOTE]
>  字符文本导出为无符号整数。 例如，“a”导出为 97，“b”导出为 98，以此类推。  
  
> [!CAUTION]
>  标识符名称必须符合 W3C 可扩展标记语言 (XML) 1.0 规范。  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a>将业务流程导出到 BPEL4WS  
  
1.  将类型为 BizTalk 业务流程的新项添加到项目中。  
  
2.  单击设计图面以打开“业务流程属性”窗口。  
  
3.  设置**模块可导出**为 True。  
  
4.  要用于命名空间中的类型**模块 XML 目标 Namespace**。  
  
5.  设置**业务流程可导出**为 True。  
  
6.  要用于命名空间中的类型**Orchestration XML 目标 Namespace**。  
  
7.  在解决方案资源管理器，右键单击。您的业务流程的 ODX 文件。  
  
8.  选择**将导出到 BPEL**。  
  
     业务流程将导出到 BPEL4WS。 查看“输出”窗口和“任务列表”以确认是否成功或诊断问题。 导出成功后，将在项目目录中创建 .WSDL 文件和 .BPEL 文件。  
  
> [!NOTE]
>  如果业务流程包含角色链接（服务链接）的赋值或动态端口的文本赋值，BizTalk 将生成虚拟 BPEL4WS 终结点引用并发出警告。  
  
## <a name="see-also"></a>另请参阅  
 [如何导入 BPEL4WS](../core/how-to-import-bpel4ws.md)   
 [XLANG-s 的 BPEL4WS 类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)