---
title: 如何导出 BPEL4WS |Microsoft Docs
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
ms.openlocfilehash: 655c3947283b5cd4cb45d863c416051d08a37a98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385060"
---
# <a name="how-to-export-bpel4ws"></a>如何导出 BPEL4WS
可以将现有的 BizTalk 业务流程导出到 BPEL4WS。  
  
> [!IMPORTANT]
>  此版本的 BizTalk Server 支持 BPEL4WS 1.1。 无法导入或导出 BPEL4WS 1.0。  
  
 如果要导出，bpel4ws 编译需要业务流程包含仅是 XLANG/s 和 BPEL4WS 之间通用的功能或可翻译成 BPEL4WS 中，而不会影响行为的功能。  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a>导出的业务流程的 bpel4ws 的限制  
  
-   不能使用调用业务流程形状或启动业务流程形状。  
  
-   不能使用转换形状。  
  
-   不能调用自定义.NET 组件上的方法。  
  
-   不能对一个长时间运行的事务应用超时。  
  
-   您的业务流程不能采用参数。  
  
-   可调用补偿处理程序不能有参数。  
  
-   变量类型必须是在 XPATH 中受支持。  
  
-   不能使用挂起形状。  
  
-   文本值必须是以下类型之一：  
  
     布尔值、 char、 byte、 sbyte、 int32、 uint32、 int64、 uint64、 single、 double、 字符串  
  
-   仅在以下数字类型的操作数上不允许算术运算符：  
  
     byte、 sbyte、 int32、 uint32、 int64、 uint64、 single、 double  
  
-   关系运算符不能应用于类型 char。  
  
-   在表达式中不能对 servicelink 属性的引用。  
  
-   你不能执行任何操作之间**发送**形状和一个**接收**使用相同的出站请求-响应端口的形状。  
  
-   不能间接引用 web 服务，如通过对另一个项目的引用，其中包含一个引用。 在项目中，必须显式引用 web 服务。  
  
-   不能在延迟中指定常数 DateTime 或 TimeSpan。 而是在 System.Xml 命名空间中使用转换类之一：  
  
     对于常数 DateTime:System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")  
  
     对于常数 TimeSpan:System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")  
  
> [!NOTE]
>  字符文本导出为无符号整数。 例如，a 导出为 97，b 导出为 98，等等。  
  
> [!CAUTION]
>  标识符名称必须符合 W3C 可扩展标记语言 (XML) 1.0 规范。  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a>若要将业务流程导出到 BPEL4WS  
  
1.  将 BizTalk 业务流程类型的新项添加到你的项目。  
  
2.  单击设计图面以显示业务流程属性窗口。  
  
3.  设置**模块可导出**为 True。  
  
4.  所需的命名空间中的类型**模块 XML 目标 Namespace**。  
  
5.  设置**业务流程可导出**为 True。  
  
6.  所需的命名空间中的类型**业务流程 XML 目标 Namespace**。  
  
7.  在解决方案资源管理器中右键单击。您的业务流程的 ODX 文件。  
  
8.  选择**导出到 BPEL**。  
  
     您的业务流程将导出到 BPEL4WS。 请参阅输出窗口和任务列表以确认成功或诊断问题。 导出成功后,。WSDL 文件和一个。将你的项目目录中创建 BPEL 文件。  
  
> [!NOTE]
>  如果您的业务流程包含角色链接 （服务链接） 赋值或动态端口的文本赋值，BizTalk 将生成虚拟 BPEL4WS 终结点引用，并将引发警告。  
  
## <a name="see-also"></a>请参阅  
 [如何导入 BPEL4WS](../core/how-to-import-bpel4ws.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)