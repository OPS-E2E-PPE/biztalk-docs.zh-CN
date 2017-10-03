---
title: "生成任务列表中的错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfd5b9f7b974b00d63831484ecbaa44e2568fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="build-errors-in-the-task-list"></a>生成任务列表中的错误
在生成项目或解决方案时，其结果将显示在“输出”窗口中，而各个错误和警告将显示在任务列表中。  
  
 错误和警告将显示在任务列表中。 你可以双击错误，焦点将指向未正确配置的对象。  
  
> [!NOTE]
>  在生成过程中，编译器将不会验证 XPath。 所以，请谨慎使用有效的 XPath 语法。  
  
## <a name="insufficient-configuration-action"></a>不完全的配置操作  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  尽管业务流程设计器将在发生配置不完全时提供配置不完全警告，但这并不能确保没有此类警告业务流程的编译就是正确的。  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a>编译器询问是否缺少程序集引用  
  
### <a name="problem"></a>问题  
 在编译业务流程时，你收到一条错误消息，该错误消息的末尾询问“是否缺少程序集引用?” 最常见的两条消息是：  
  
-   命名空间“Y”中不存在类型或命名空间名称“X”(是否缺少程序集引用?)  
  
-   标识符“X”在“Y”中不存在；是否缺少程序集引用?  
  
### <a name="cause"></a>原因  
 下面任何一项都可能是导致此错误的原因。  
  
-   你的项目不能引用一个或多个所需程序集。  
  
-   你的项目具有与项目同名的映射或其他对象类型。  
  
-   你的项目使用基于 XML 架构定义语言 (XSD) 的合作伙伴接口流程 (PIP) 架构并在名为“System”的子文件夹中包含 XSD 架构。  
  
-   你的项目使用命名空间为当前项目命名空间子集的全局属性。 例如，在项目“Accounts.FILE”包含的业务流程中使用全局属性命名空间“File.ReceivedFileName”。  
  
### <a name="resolution"></a>解决方法  
 根据导致问题的原因，解决方法可为以下某一种：  
  
-   添加指向你的项目需要但缺少了的程序集的引用。  
  
-   将映射或其他对象的名称更改为项目名称以外的其他名称。 通常，这可通过对象的属性页完成（例如，“映射属性”页包含“名称”属性）。  
  
-   更改 Visual Studio 中架构的命名空间。 若要执行此操作使用 Visual Studio，请单击**显示所有文件**上**项目**菜单，然后展开**系统**在解决方案资源管理器中的节点。 单击每个文件中的系统文件夹和所有子文件夹中，然后更改属性窗口中的命名空间条目这样的任何匹配项**系统**变得 _**系统**。 例如，更改**MyProject.System.SubFolder**的命名空间**MyProject._System.Subfolder**命名空间。 有关此问题，请参阅知识库文章[916649](http://support.microsoft.com/?kbid=916649)。  
  
-   从项目中删除相冲突的全局属性命名空间。  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a>在生成项目时，收到错误“construct 语句中未初始化消息”  
  
### <a name="problem"></a>问题  
 在编译 BizTalk 应用程序时，收到错误“construct 语句中未初始化消息”。  
  
### <a name="cause"></a>原因  
 在构造消息时，应指定所有消息变量。 然后对消息或其成分进行赋值。 如果在单独的包含的特定消息分配一部分**构造消息**形状，你可能会收到初始化错误消息。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，请确保在同一个包括特定消息分配的所有部分**构造消息**形状。 对于相关的支持问题，请参阅知识库文章[870606](http://support.microsoft.com/?kbid=870606)。  
  
 您也可以通过创建你的消息中解决此行为**构造**在使用中它的实例之前的形状**表达式**形状。 例如，下面的代码会导致错误，如果置于**表达式**形状：  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 若要解决问题，请创建 XMLDOM 中实例**构造**形状，，然后执行中下游的分配**表达式**形状。  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a>在生成项目时，收到错误“使用未构造的消息”  
  
### <a name="problem"></a>问题  
 编译你的 BizTalk 项目时，你将收到错误"使用未构造的消息\<消息 >'"。  
  
### <a name="cause"></a>原因  
 在使用非的消息时发生此错误**发送**形状。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，将添加**构造消息**形状上的与业务流程。 包括**构造消息**之前调整**发送**已绑定到 Web 服务的形状。  
  
 有关详细信息，有关此错误和 Web 服务，请参阅知识库文章[921043](http://support.microsoft.com/?kbid=921043)。  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a>设置作用域的事务级别将导致错误  
  
### <a name="problem"></a>问题  
 在业务流程中配置作用域或支持事务的其他实体的事务类型时，收到错误“非事务性业务流程不能包含任何其他事务”。  
  
### <a name="cause"></a>原因  
 当尝试在业务流程中将作用域（或其他实体）的事务类型配置为“原子”或“长期”，而业务流程本身的业务类型为“无”时，将出现此错误。  
  
### <a name="resolution"></a>解决方法  
 确保业务流程和构成对象的事务类型设置相兼容。  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a>项目生成导致错误“必须为非自相关端口上的非激活接收指定至少一个已初始化的相关集”  
  
### <a name="problem"></a>问题  
 在编译 BizTalk 项目时，收到错误“必须为非自相关端口上的非激活接收指定至少一个已初始化的相关集”。  
  
### <a name="cause"></a>原因  
 如果您的业务流程具有没有激活，会出现此错误**接收**形状 (激活 = true) 或具有没有激活**接收**形状并不直接由另一个业务流程调用。  
  
### <a name="resolution"></a>解决方法  
 如果您的业务流程不由另一个业务流程调用，则必须配置之一**接收**形状要激活的接收。 有关配置的详细信息**接收**形状，包括指向相关，请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a>你将收到错误"程序集生成失败--引用的程序集\<程序集 > 不具有强名称"生成解决方案时  
  
### <a name="problem"></a>问题  
 你将收到错误"程序集生成失败--引用的程序集\<程序集 > 不具有强名称"当生成你的解决方案具有一个业务流程。  
  
### <a name="cause"></a>原因  
 当在业务流程中使用未签名的引用程序集中的类型时，将出现此问题。  
  
### <a name="resolution"></a>解决方法  
 对引用的程序集应用强名称。 如果该程序集是可重新编译的自定义程序集，请使用强名称工具创建 .snk（密钥）文件，然后在项目的程序集属性中引用该密钥文件。 有关强命名程序集的详细信息，请参阅[如何配置一个强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a>在部署业务流程时，出现错误“无法添加资源。 对某些资源的更改请求失败”  
  
### <a name="problem"></a>问题  
 在部署业务流程时，出现类似下面的错误并且业务流程部署失败：  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a>原因  
 如果业务流程包含使用 C# 关键字的任何对象，则可能会出现此错误。  
  
### <a name="resolution"></a>解决方法  
 删除业务流程中的任何 C# 关键字。 C# 关键字的列表，请参阅[http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)。  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a>在编译业务流程时，收到错误“无效的属性值”  
  
### <a name="problem"></a>问题  
 在生成业务流程时，出现错误对话框“无效的属性值”。  
  
### <a name="cause"></a>原因  
 解决方案中的一个或多个对象与其他对象同名。 例如，消息名称与端口名称相同。  
  
### <a name="resolution"></a>解决方法  
 确保解决方案中的每个对象具有唯一名称。 遵守命名约定可将发生此错误的风险降到最低。  
  
## <a name="see-also"></a>另请参阅  
 [如何构建业务流程](../core/how-to-build-orchestrations.md)