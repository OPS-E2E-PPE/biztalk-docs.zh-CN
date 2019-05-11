---
title: 常见错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57eb84b31082f6175f4a68b081130216be06b63e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528202"
---
# <a name="common-errors"></a>常见错误
本主题列出了使用 BizTalk 映射器创建映射时可能遇到的常见错误消息。  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a>分析日期时收到错误事件 ID 324  
  
### <a name="problem"></a>问题  
 当使用数据库**值提取程序**functoid 映射提取日期字段，在文档中的对出站文档定义的验证可能会失败。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可能会在事件日志中记录类似于以下的验证错误：  
  
 事件源：BizTalk Server  
  
 事件类别：文档处理  
  
 事件 ID：324  
  
 说明:  
  
 在 BizTalk Server 中出错。  
  
 详细信息：  
  
 -----------------------------\-  
  
 XML 文档验证失败的原因如下：错误分析"10/12/1995年作为日期数据类型。  
  
 挂起的队列 ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"  
  
### <a name="cause"></a>原因  
 日期格式 （如从数据源返回） 不是采用 ISO 8601 格式，这是所需的 XML 的格式。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
- 编辑出站文档定义使用而不是日期数据类型的字符串数据类型。  
  
- 创建自定义[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**脚本**functoid 会将转换数据库的输出**值提取程序**为 ISO 8601 格式的 functoid。  
  
  有关详细信息，请参阅知识库文章[278737](http://support.microsoft.com/kb/278737/en-us)。  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a>当收到内部编译器错误 (在地址 53624FD6 0xc0000005) 编译映射  
  
### <a name="problem"></a>问题  
 当编译包含大型架构、 映射或业务流程的单个 BizTalk 项目时，编译器可能会生成如下错误：  
  
 内部编译器错误 (在地址 53624FD6 0xc0000005): 可能的原因是代码生成。  
  
### <a name="cause"></a>原因  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器中的单个项目的所有字符串的总大小具有 16 兆字节的限制。 而编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，而这会增大可能会超出此限制的所有字符串的总大小。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以分隔架构或映射到不同的 BizTalk 项目。  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a>接收有关类型名称的 BizTalk 项目的错误  
  
### <a name="problem"></a>问题  
 在 BizTalk 项目中，使用文件名创建地图**System.btm**或**Microsoft.btm**。 生成项目时，BizTalk 映射器将生成类似于以下任一错误：  
  
-   "类型名称 'SerializableAttribute' 不存在..."  
  
-   "类型名称 'NonSerializableAttribute' 不存在..."  
  
-   "' Serializableattributeattribute ' 不存在..."  
  
-   "' Xlans ' 不存在..."  
  
### <a name="cause"></a>原因  
 **类型名称**中**属性**网格不应具有任何保留的.NET 命名空间，如**系统**， **Microsoft**，等等。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以执行任何以下解决方法：  
  
-   修改为任何字符串，这不是.NET 保留字的映射的名称。 默认情况下，创建 BizTalk 项目系统**类型名称**从各自的项目的名称。  
  
     对于如：具有名称创建新地图**Map1.btm**设置**类型名称**属性值设置为**Map1**。 但是，重命名现有 BizTalk 项目不会更改**类型名称**。  
  
-   请确保任何 BizTalk 项目中的项目的文件名不是.NET 保留命名空间。  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a>接收文件名称的 BizTalk 项目时出现的错误  
  
### <a name="problem"></a>问题  
 生成 BizTalk 项目时，BizTalk 映射器将生成类似于以下任一错误：  
  
-   "文件\<文件名\>具有重复的命名空间和类型名属性的值。"  
  
-   "命名空间\<名称\>已经包含 '_' 的定义。"  
  
### <a name="cause"></a>原因  
 在 BizTalk 项目中，检查有以下：  
  
-   多个项目具有相同的文件名。 对于如**Map1.xsd**并**Map1.btm**。  
  
-   文件名包括只由特殊字符 (**~**， **！**， **@**，等等。)。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，可以执行任何以下解决方法：  
  
-   重命名文件。 确保 BizTalk 项目中所有项目的文件名是唯一的。  
  
-   确保 BizTalk 项目中的所有项目都是唯一的类型名称。  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a>使用 BizTalk 映射器生成的任何 C# 工作流项目显示有关 EnvDTE.dll 的版本冲突有关的警告  
  
### <a name="problem"></a>问题  
 使用 BizTalk 映射器生成的任何 C# 工作流项目活动始终显示 EnvDTE.dll 的版本冲突有关的以下警告。  
  
 没有办法解决之间的冲突"EnvDTE，版本 = 8.0.0.0，区域性 = neutral，PublicKeyToken = b03f5f7f11d50a3a"和"EnvDTE，版本 = 7.0.3300.0，区域性 = 中性，PublicKeyToken = b03f5f7f11d50a3a"。 选择"EnvDTE，版本 = 8.0.0.0，区域性 = 中性，PublicKeyToken = b03f5f7f11d50a3a"任意。  请考虑 app.config 重新映射的程序集"EnvDTE，Culture = neutral，PublicKeyToken = b03f5f7f11d50a3a"版本"7.0.3300.0"[] 到版本"8.0.0.0"[C:\Program Files (x86) \Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll]若要解决冲突并消除警告。 C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247:找到的同一依赖程序集的不同版本之间的冲突。  
  
 WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe  
  
### <a name="cause"></a>原因  
 映射器活动所引用的 microsoft.biztalk.mapper.om.dll 发生这种情况。  
  
### <a name="resolution"></a>解决方法  
 忽略的警告。  
  
## <a name="see-also"></a>请参阅  
 [排除地图故障](../core/troubleshooting-maps.md)