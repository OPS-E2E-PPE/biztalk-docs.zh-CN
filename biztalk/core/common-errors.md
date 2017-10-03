---
title: "常见错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14ff75bff7d5b22efdafb7aa3327683fbe805514
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="common-errors"></a>常见错误
本主题列出来在使用 BizTalk 映射器创建映射时可能遇到的常见错误消息。  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a>在分析日期时接收错误事件 ID 324  
  
### <a name="problem"></a>问题  
 当你使用数据库**值提取程序**functoid 映射中提取日期字段，你的文档中可能会失败对出站文档定义的验证。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将在事件日志中记录类似于以下的验证错误：  
  
 事件来源： BizTalk Server  
  
 事件类别： 文档处理  
  
 事件 ID: 324  
  
 说明:  
  
 BizTalk Server 中出错。  
  
 详细信息：  
  
 -----------------------------\-  
  
 XML 文档未通过验证，原因如下： 错误分析"10/12/1995年为日期数据类型。  
  
 挂起的队列 ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"  
  
### <a name="cause"></a>原因  
 日期格式 （如从数据源返回） 不是 ISO 8601 格式，这是所需的 XML 格式。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   编辑出站文档定义要使用的字符串数据类型而不是日期数据类型。  
  
-   创建自定义[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**脚本**会将转换的输出数据库的 functoid**值提取程序**functoid 为 ISO 8601 格式。  
  
 有关详细信息，请参阅知识库文章[278737](http://support.microsoft.com/kb/278737/en-us)。  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a>当接收内部编译器错误 (在地址 53624FD6 0xc0000005) 编译地图  
  
### <a name="problem"></a>问题  
 编译单个 BizTalk 项目组成的大型架构、 地图或业务流程时，编译器也会生成类似于以下错误：  
  
 内部编译器错误 (在地址 53624FD6 0xc0000005): 可能的原因是代码。  
  
### <a name="cause"></a>原因  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器具有 16 兆字节限制单个项目中的所有字符串的总大小。 虽然编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，并且这会增加可能超出限制的所有字符串的总大小。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以分隔架构或映射到不同的 BizTalk 项目。  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a>你会收到有关 BizTalk 项目类型名称的错误  
  
### <a name="problem"></a>问题  
 在 BizTalk 项目中，使用文件名创建地图**System.btm**或**Microsoft.btm**。 生成项目时，BizTalk 映射程序将生成类似于以下任何类型的错误：  
  
-   “类型名称‘SerializableAttribute’不存在…”  
  
-   “类型名称‘NonSerializableAttribute’不存在…”  
  
-   “类型名称‘SerializableAttributeAttribute’不存在…”  
  
-   “类型名称‘XLANs’不存在…”  
  
### <a name="cause"></a>原因  
 **类型名称**中**属性**网格不应有任何保留的.NET 命名空间，如**系统**， **Microsoft**等。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以执行任何这些解决方法：  
  
-   将映射名称修改为非 .NET 保留字的任何字符串。 默认情况下，BizTalk 项目系统将创建**类型名称**从各自的项目的名称。  
  
     有关例如： 具有名称创建一个新图**Map1.btm**设置**类型名称**属性值设置为**Map1**。 但是，重命名现有 BizTalk 项目不会更改**类型名称**。  
  
-   确保 BizTalk 项目中的所有项目的文件名不是 .NET 保留命名空间。  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a>收到有关 BizTalk 项目的文件名的错误  
  
### <a name="problem"></a>问题  
 生成 BizTalk 项目时，BizTalk 映射器会生成一条类似以下任一内容的错误：  
  
-   "文件\<文件名 > 有重复的命名空间和类型名属性的值。"  
  
-   "命名空间\<名称 > 已经包含 _ 的定义。"  
  
### <a name="cause"></a>原因  
 在 BizTalk 项目中，检查是否存在以下情况：  
  
-   多个项目具有相同的文件名。 对于如**Map1.xsd**和**Map1.btm**。  
  
-   文件名包含的仅特殊字符 (**~**， **！**，  **@**等。)。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以执行任何这些解决方法：  
  
-   重命名文件。 确保 BizTalk 项目中所有项目的文件名都是唯一的。  
  
-   确保 BizTalk 项目中所有项目的类型名称都是唯一的。  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a>构建任何具有 BizTalk 映射器的 C# 工作流项目都会显示一个有关 EnvDTE.dll 的版本冲突的警告  
  
### <a name="problem"></a>问题  
 构建任何具有 BizTalk 映射器活动的 C# 工作流项目始终会显示以下有关 EnvDTE.dll 的版本冲突的警告。  
  
 没有办法解决“EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”和“EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”之间的冲突。 任意选择“EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”。  请考虑 app.config 重新映射程序集"EnvDTE，Culture = neutral，PublicKeyToken = b03f5f7f11d50a3a"版本"7.0.3300.0"[] 到版本"8.0.0.0"[C:\Program Files (x86) \Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll]若要解决冲突并消除警告。 C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9)： 警告 MSB3247： 同一从属程序集的不同版本之间出现冲突。  
  
 WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe  
  
### <a name="cause"></a>原因  
 之所以会发生这种情况是因为映射器活动所引用的 Microsoft.BizTalk.Mapper.OM.dll。  
  
### <a name="resolution"></a>解决方法  
 忽略此警告。  
  
## <a name="see-also"></a>另请参阅  
 [排除地图故障](../core/troubleshooting-maps.md)