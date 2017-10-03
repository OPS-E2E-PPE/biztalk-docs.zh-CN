---
title: "配置 SWIFT 反汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa71ce6ba1d2a910626446ed45439b8c7132e75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-disassembler"></a><span data-ttu-id="cfe40-102">配置 SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="cfe40-102">Configuring the SWIFT Disassembler</span></span>
<span data-ttu-id="cfe40-103">SWIFT 反汇编程序 (DASM) 将执行下列任务，在调用中时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：</span><span class="sxs-lookup"><span data-stu-id="cfe40-103">The SWIFT disassembler (DASM) performs the following tasks when you invoke it in a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="cfe40-104">动态发现消息类型，并解析文档架构</span><span class="sxs-lookup"><span data-stu-id="cfe40-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="cfe40-105">为 XML 分析 SWIFT 平面文件</span><span class="sxs-lookup"><span data-stu-id="cfe40-105">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="cfe40-106">调用验证读取器执行 XML （架构） 验证的 XML</span><span class="sxs-lookup"><span data-stu-id="cfe40-106">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="cfe40-107">调用以执行 BRE 验证业务规则引擎 (BRE)</span><span class="sxs-lookup"><span data-stu-id="cfe40-107">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="cfe40-108">将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML</span><span class="sxs-lookup"><span data-stu-id="cfe40-108">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="cfe40-109">进程入站的批处理</span><span class="sxs-lookup"><span data-stu-id="cfe40-109">Processes inbound batches</span></span>  
  
 <span data-ttu-id="cfe40-110">你可以配置上面列出的、 以满足用户方案的特定要求的功能和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="cfe40-110">You can configure the functionality listed above to meet the specific requirements for a user scenario and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solution.</span></span>  
  
 <span data-ttu-id="cfe40-111">BizTalk 管道设计器配置的自定义接收管道的开发期间 SWIFT 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="cfe40-111">BizTalk Pipeline Designer configures the SWIFT disassembler during development time of the custom receive pipeline.</span></span>  
  
 <span data-ttu-id="cfe40-112">若要添加到自定义接收管道的拆装阶段之后，请配置 SWIFT 反汇编程序，选择 BizTalk 管道设计器画布上的 SWIFT 反汇编程序组件。</span><span class="sxs-lookup"><span data-stu-id="cfe40-112">To configure the SWIFT disassembler after it has been added to the disassemble stage of a custom receive pipeline, select the SWIFT disassembler component on the BizTalk Pipeline Designer canvas.</span></span> <span data-ttu-id="cfe40-113">SWIFT 反汇编程序然后接收到焦点并可以设置使用内的属性窗口其配置属性[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cfe40-113">The SWIFT disassembler then receives focus and you can set its configuration properties using the Properties window within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
 <span data-ttu-id="cfe40-114">有关可用的配置属性及其说明和用法的详细信息的表，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe40-114">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span>  
  
 <span data-ttu-id="cfe40-115">有关为不同的方案使用 SWIFT 反汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe40-115">For information about using the SWIFT disassembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
 <span data-ttu-id="cfe40-116">当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]编译二进制文件，以静态方式的配置设置写入到自定义管道自定义的管道。</span><span class="sxs-lookup"><span data-stu-id="cfe40-116">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compiles the custom pipeline binary, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="cfe40-117">因此，你无法在部署过程中更改配置属性，或运行时间。</span><span class="sxs-lookup"><span data-stu-id="cfe40-117">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfe40-118">配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署自定义的管道。</span><span class="sxs-lookup"><span data-stu-id="cfe40-118">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="cfe40-119">有关创建的信息，生成和部署自定义管道，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="cfe40-119">For information about creating, building, and deploying custom pipelines, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="cfe40-120">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="cfe40-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="cfe40-121">SWIFT 反汇编程序配置属性</span><span class="sxs-lookup"><span data-stu-id="cfe40-121">SWIFT Disassembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)