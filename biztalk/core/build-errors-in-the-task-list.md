---
title: 任务列表中生成错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc22550629d8ae66652e0afe1da61b1443dc580
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357780"
---
# <a name="build-errors-in-the-task-list"></a>任务列表中生成错误
在生成项目或解决方案时，结果将显示在输出窗口中，而各个错误和警告将显示任务列表中。  
  
 任务列表中会显示错误和警告。 你可以双击错误，并且焦点将适用于未正确配置的对象。  
  
> [!NOTE]
>  在生成时，编译器不会验证 Xpath。 请务必使用有效的 XPath 语法。  
  
## <a name="insufficient-configuration-action"></a>缺少配置的操作  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  尽管业务流程设计器将提供可以在其中配置不完全警告，则您的业务流程能够正确编译中没有此类警告无法保证。  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a>编译器询问是否缺少程序集引用  
  
### <a name="problem"></a>问题  
 在编译您的业务流程时你收到错误消息的末尾询问"缺少程序集引用？" 两个更常见的消息是：  
  
-   命名空间 Y 中不存在类型或命名空间名称 X （是否缺少程序集引用？）  
  
-   Y; 中不存在标识符 X是否缺少程序集引用？  
  
### <a name="cause"></a>原因  
 以下任何可能导致此错误的原因。  
  
-   你的项目不会引用一个或多个所需的程序集。  
  
-   你的项目已映射或其他对象类型具有与项目相同的名称。  
  
-   你的项目使用 XML 架构定义语言 (XSD) 的基础合作伙伴接口流程 (PIP) 架构，并包含名为系统的子文件夹中的 XSD 架构。  
  
-   你的项目使用的命名空间为当前项目的命名空间子集的全局属性。 例如，使用在项目"Accounts.FILE"包含的业务流程中的全局属性命名空间"File.ReceivedFileName"。  
  
### <a name="resolution"></a>解决方法  
 根据问题的原因，解决方法可能是以下任一项：  
  
-   添加对缺失的引用你的项目需要的程序集。  
  
-   将代码图或其他对象的名称更改为项目名称以外的内容。 这通常可以通过对象的属性页 （例如，映射属性页包含一个 Name 属性）。  
  
-   更改 Visual Studio 中的架构的命名空间。 若要执行此操作使用 Visual Studio，请单击**显示所有文件**上**项目**菜单中，然后展开**系统**在解决方案资源管理器中的节点。 单击每个文件系统文件夹及其任何子文件夹，然后更改属性窗口中的命名空间条目，以使所有匹配项**系统**变为 _**系统**。 例如，更改**MyProject.System.SubFolder**命名空间**MyProject._System.Subfolder**命名空间。 详细了解此问题，请参阅知识库文章[916649](http://support.microsoft.com/?kbid=916649)。  
  
-   从项目中删除冲突的全局属性命名空间。  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a>生成项目时，收到"未初始化消息构造语句中"错误  
  
### <a name="problem"></a>问题  
 当编译 BizTalk 应用程序时，则会收到错误"消息尚未初始化 construct 语句中"。  
  
### <a name="cause"></a>原因  
 在构造一条消息时，你指定所有消息变量。 然后对该消息或其各个部分进行赋值。 如果特定消息赋值的一部分包含在单独**构造消息**形状，可能会收到初始化错误消息。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，请确保在同一个包括特定的消息分配的所有部分**构造消息**形状。 对于相关的支持问题，请参阅知识库文章[870606](http://support.microsoft.com/?kbid=870606)。  
  
 您也可以通过创建您的消息中解决此行为**构造**然后才能使用它在中的一个实例的形状**表达式**形状。 例如，下面的代码将导致出错，如果按放置**表达式**形状：  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 若要解决问题，请创建在 XMLDOM 的实例**构造**形状，然后再进行分配在下游**表达式**形状。  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a>生成项目时，收到了"使用未构造的消息"错误  
  
### <a name="problem"></a>问题  
 在编译 BizTalk 项目时，收到错误"使用未构造的消息\<消息\>'"。  
  
### <a name="cause"></a>原因  
 在中使用未构造的消息时出现此错误**发送**形状。  
  
### <a name="resolution"></a>解决方法  
 若要解决此问题，请添加**构造消息**向业务流程的形状。 包括**构造消息**前**发送**形状绑定到 Web 服务。  
  
 有关详细信息，有关此错误和 Web 服务，请参阅知识库文章[921043](http://support.microsoft.com/?kbid=921043)。  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a>在错误中设置结果范围的事务级别  
  
### <a name="problem"></a>问题  
 配置事务的作用域键入或其他业务流程中支持事务的实体，您会收到错误后是"非事务性业务流程不能包含任何其他事务"。  
  
### <a name="cause"></a>原因  
 此错误时发生 when you try to 配置作用域 （或其他实体） 的事务类型为"原子"或"长期"业务流程中业务流程本身具有事务类型为"None"。  
  
### <a name="resolution"></a>解决方法  
 确保您的业务流程和构成对象的事务类型设置兼容。  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a>项目生成导致错误"必须指定至少一个已初始化的相关集的非激活接收非自相关端口上"  
  
### <a name="problem"></a>问题  
 在编译 BizTalk 项目时，你收到错误"必须指定至少一个已初始化的相关集的非激活接收非自相关端口上"。  
  
### <a name="cause"></a>原因  
 如果您的业务流程没有激活，会出现此错误**接收**形状 (Activate = true) 或者没有激活**接收**形状并且不由另一个业务流程直接调用。  
  
### <a name="resolution"></a>解决方法  
 如果您的业务流程不由另一个业务流程调用的则必须配置之一**接收**已激活的接收形状。 有关配置详细信息**接收**形状，其中包括指向相关的更多信息，请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a>收到错误"程序集生成失败--引用的程序集 '\<程序集\>不具有强名称"生成解决方案时  
  
### <a name="problem"></a>问题  
 收到错误"程序集生成失败--引用的程序集 '\<程序集\>不具有强名称"时，生成你的解决方案包含一个业务流程。  
  
### <a name="cause"></a>原因  
 当业务流程中使用从无符号的引用程序集的类型时，将发生此问题。  
  
### <a name="resolution"></a>解决方法  
 适用于引用的程序集的强名称。 如果它是可以重新编译的自定义程序集，使用强名称工具创建.snk （密钥） 文件，然后引用程序集属性中的项目的该密钥文件。 有关强命名程序集的详细信息，请参阅[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a>错误"无法添加资源。 更改对某些资源失败的请求"时发生部署业务流程  
  
### <a name="problem"></a>问题  
 在部署业务流程时，将显示类似于以下的错误，业务流程的部署失败：  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a>原因  
 如果该业务流程包含使用的所有对象可能发生此错误C#关键字。  
  
### <a name="resolution"></a>解决方法  
 删除任何C#关键字从业务流程。 有关列表的C#关键字，请参见[ http://go.microsoft.com/fwlink/?LinkId=74346 ](http://go.microsoft.com/fwlink/?LinkId=74346)。  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a>编译您的业务流程时收到"无效的属性值"错误  
  
### <a name="problem"></a>问题  
 出现错误对话框"无效的属性值"构建您的业务流程时。  
  
### <a name="cause"></a>原因  
 一个或多个解决方案中的对象具有相同名称与另一个对象。 例如，消息名称是与端口名称相同。  
  
### <a name="resolution"></a>解决方法  
 请确保你的解决方案中的每个对象具有唯一的名称。 可以通过遵守命名约定此错误的风险降至最低。  
  
## <a name="see-also"></a>请参阅  
 [如何生成业务流程](../core/how-to-build-orchestrations.md)