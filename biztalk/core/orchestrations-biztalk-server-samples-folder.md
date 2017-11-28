---
title: "业务流程 （BizTalk Server 的示例文件夹） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- SDK examples
ms.assetid: f70f8d67-763f-4e3c-b233-c7156026b514
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a018f52985e54f72749903aef58f40236d0618
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrations-biztalk-server-samples-folder"></a><span data-ttu-id="45bde-102">业务流程 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="45bde-102">Orchestrations (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="45bde-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在其软件开发工具包 (SDK) 中包括了几个业务流程示例。</span><span class="sxs-lookup"><span data-stu-id="45bde-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several orchestration samples in its software development kit (SDK).</span></span> <span data-ttu-id="45bde-104">本部分将提供有关这些业务流程示例所演示功能的详细信息、生成和运行这些示例的说明以及可预期的结果。</span><span class="sxs-lookup"><span data-stu-id="45bde-104">This section provides detailed information about the functionality demonstrated by these orchestration samples, instructions for building and running the samples, and the results you can expect.</span></span> <span data-ttu-id="45bde-105">下面所列的示例按其复杂程度排序，即 HelloWorld 是列表中最基本的示例。</span><span class="sxs-lookup"><span data-stu-id="45bde-105">The samples listed below are sorted by complexity, that is, HelloWorld is the most basic sample in the list.</span></span> <span data-ttu-id="45bde-106">列表中排在后面的示例可能基于列表中排在前面的示例所示的功能。</span><span class="sxs-lookup"><span data-stu-id="45bde-106">Samples later in the list might be based upon functionalities shown in samples earlier in the list.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45bde-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="45bde-107">In This Section</span></span>  
  
-   <span data-ttu-id="45bde-108">[HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-108">[HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-109">演示如何使用来处理 XML 消息的 XML 消息的相关，但不同的类型到 BizTalk 业务流程和映射。</span><span class="sxs-lookup"><span data-stu-id="45bde-109">Demonstrates how to process XML messages into related, but distinct, types of XML messages by using BizTalk orchestrations and maps.</span></span>  
  
-   <span data-ttu-id="45bde-110">[MethodCall （BizTalk Server 示例）](../core/methodcall-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-110">[MethodCall (BizTalk Server Sample)](../core/methodcall-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-111">演示如何调用。从 BizTalk 业务流程的基于网络的方法。</span><span class="sxs-lookup"><span data-stu-id="45bde-111">Demonstrates how to call a .NET-based method from a BizTalk orchestration.</span></span>  
  
-   <span data-ttu-id="45bde-112">[CallOrchestration （BizTalk Server 示例）](../core/callorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-112">[CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-113">演示如何从另一个业务流程调用 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="45bde-113">Demonstrates how to call a BizTalk orchestration from another orchestration.</span></span>  
  
-   <span data-ttu-id="45bde-114">[补偿 （BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-114">[Compensation (BizTalk Server Sample)](../core/compensation-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-115">演示如何使用**Compensate**形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="45bde-115">Demonstrates how to use the **Compensate** shape in an orchestration.</span></span>  
  
-   <span data-ttu-id="45bde-116">[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-116">[PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-117">演示如何将 BizTalk 业务流程与实例消息路由到的参与方解析一起使用。</span><span class="sxs-lookup"><span data-stu-id="45bde-117">Demonstrates how to use BizTalk orchestrations with party resolution to route instance messages.</span></span>  
  
-   <span data-ttu-id="45bde-118">[BPEL 导入 （BizTalk Server 示例）](../core/bpel-import-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="45bde-118">[BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span> <span data-ttu-id="45bde-119">演示如何从业务进程执行语言 (BPEL) 的进程和相关的项目的说明创建一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="45bde-119">Demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) description of a process and related artifacts.</span></span>