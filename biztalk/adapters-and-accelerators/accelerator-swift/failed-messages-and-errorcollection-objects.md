---
title: "失败消息和 ErrorCollection 对象 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65598ef44bfe3e34bd1695aa81bee368c5175793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="failed-messages-and-errorcollection-objects"></a><span data-ttu-id="cf5eb-102">失败的消息和 ErrorCollection 对象</span><span class="sxs-lookup"><span data-stu-id="cf5eb-102">Failed Messages and ErrorCollection Objects</span></span>
<span data-ttu-id="cf5eb-103">除了修饰使用提升的属性，失败的消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将在失败的消息发布到其他消息的 MessageBox 数据库*一部分*、 调用**ErrorSegment**.</span><span class="sxs-lookup"><span data-stu-id="cf5eb-103">In addition to decorating a failed message with promoted properties, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publishes the failed message to the MessageBox database with an additional message *part*, called **ErrorSegment**.</span></span> <span data-ttu-id="cf5eb-104">此错误一部分包含 XML 表示**ErrorCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-104">This error part contains XML representing an **ErrorCollection** object.</span></span> <span data-ttu-id="cf5eb-105">A4SWIFT 反汇编程序填充**ErrorCollection**消息处理 （分析，XML 验证和业务规则引擎 (BRE) 验证） 的每个阶段的对象。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-105">The A4SWIFT disassembler populates the **ErrorCollection** object during each stage of message processing (parsing, XML validation, and Business Rule Engine (BRE) validation).</span></span>  
  
 <span data-ttu-id="cf5eb-106">**ErrorCollection**对象是一个集合的*错误对象*，其中每个消息处理过程表示特定错误或失败。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-106">The **ErrorCollection** object is a collection of *error objects*, each of which represents a particular error or failure during message processing.</span></span> <span data-ttu-id="cf5eb-107">各个错误对象包含有关单个故障 （例如消息和失败的描述中的位置） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-107">The individual error objects contain details about a single failure (such as the location in the message and a description of the failure).</span></span>  
  
 <span data-ttu-id="cf5eb-108">有关详细信息**ErrorCollection**应用程序编程接口 (API) 和用法的详细信息，请参阅 ErrorCollection 类。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-108">For more information about the **ErrorCollection** application programming interface (API) and usage details, see ErrorCollection Class.</span></span> <span data-ttu-id="cf5eb-109">有关各个错误对象的详细信息，请参阅 ErrorBase 类 （错误对象的基类）、 BreValidationError 类、 ParseError 类和 XmlValidationError 类。</span><span class="sxs-lookup"><span data-stu-id="cf5eb-109">For more information about individual error objects, see ErrorBase Class (the base class for error objects), BreValidationError Class, ParseError Class, and XmlValidationError Class.</span></span>  
  
 <span data-ttu-id="cf5eb-110">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="cf5eb-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="cf5eb-111">捕获和消息修复扩展解决方案</span><span class="sxs-lookup"><span data-stu-id="cf5eb-111">Extending the Solution for Capture and Message Repair</span></span>](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)