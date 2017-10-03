---
title: "使用的分析和序列化引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-parsing-and-serializing-engines"></a><span data-ttu-id="0aa84-102">使用了分析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="0aa84-102">Using the Parsing and Serializing Engines</span></span>
<span data-ttu-id="0aa84-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括分析和序列化引擎来简化分析和序列化平面文件文档的过程。</span><span class="sxs-lookup"><span data-stu-id="0aa84-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes a parsing and serializing engine to simplify the process of parsing and serializing flat file documents.</span></span>  
  
 <span data-ttu-id="0aa84-104">解析引擎是一个架构驱动的框架，可以将许多不同的文档格式解析为 XML。</span><span class="sxs-lookup"><span data-stu-id="0aa84-104">The parsing engine is a schema-driven framework that can parse many different document formats into XML.</span></span> <span data-ttu-id="0aa84-105">此外，该引擎还具有明确定义的扩展模型，以便简化对自定义格式的解析。</span><span class="sxs-lookup"><span data-stu-id="0aa84-105">In addition, the engine has a well-defined extensibility model to make parsing custom formats even easier.</span></span>  
  
 <span data-ttu-id="0aa84-106">对于复杂解析，需使用拆装器。</span><span class="sxs-lookup"><span data-stu-id="0aa84-106">For complex parsing, disassemblers are used.</span></span> <span data-ttu-id="0aa84-107">除了将本地格式转换为 XML 外，拆装器还可以将单个文档划分为多个文档。</span><span class="sxs-lookup"><span data-stu-id="0aa84-107">In addition to converting the native format to XML, the disassembler can also separate a single document into multiple documents.</span></span>  
  
 <span data-ttu-id="0aa84-108">序列化引擎类似于解析引擎，只是它以相反方向工作。</span><span class="sxs-lookup"><span data-stu-id="0aa84-108">The serializing engine is similar to the parsing engine, except that it works in the opposite direction.</span></span> <span data-ttu-id="0aa84-109">解析引擎将本地格式转换为 XML，而序列化引擎则将 XML 转换为本地格式。</span><span class="sxs-lookup"><span data-stu-id="0aa84-109">Where the parsing engine converts native formats to XML, the serializing engine converts XML to native formats.</span></span> <span data-ttu-id="0aa84-110">此外，与解析引擎使用拆装器相反，序列化引擎使用组装器。</span><span class="sxs-lookup"><span data-stu-id="0aa84-110">And just as the parsing engine uses disassemblers, the serializing engine uses assemblers.</span></span>  
  
 <span data-ttu-id="0aa84-111">本部分论述如何基于 XML 架构定义语言 (XSD) 架构执行字符编码、解析和序列化，以及使用解析引擎和序列化引擎 API 执行其他常见任务。</span><span class="sxs-lookup"><span data-stu-id="0aa84-111">This section discusses how to perform character encoding, parse and serialize based on XML Schema definition language (XSD) schemas, and perform other common tasks using the parsing engine and serializing engine APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0aa84-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="0aa84-112">In This Section</span></span>  
  
-   [<span data-ttu-id="0aa84-113">实现管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="0aa84-113">Implementing Character Encoding in a Pipeline Component</span></span>](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [<span data-ttu-id="0aa84-114">使用架构</span><span class="sxs-lookup"><span data-stu-id="0aa84-114">Using Schemas</span></span>](../core/using-schemas.md)  
  
-   [<span data-ttu-id="0aa84-115">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="0aa84-115">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)  
  
-   [<span data-ttu-id="0aa84-116">使用序列化引擎的平面文件</span><span class="sxs-lookup"><span data-stu-id="0aa84-116">Using the Flat File Serializing Engine</span></span>](../core/using-the-flat-file-serializing-engine.md)