---
title: "配置 SWIFT 汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e1309012abbaac27e2e0ae6ec9b35f37d88884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-assembler"></a><span data-ttu-id="6f27f-102">配置 SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="6f27f-102">Configuring the SWIFT Assembler</span></span>
<span data-ttu-id="6f27f-103">SWIFT 汇编程序将执行下列任务，在调用中时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送管道：</span><span class="sxs-lookup"><span data-stu-id="6f27f-103">The SWIFT assembler performs the following tasks when you invoke it in a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send pipeline:</span></span>  
  
-   <span data-ttu-id="6f27f-104">动态发现消息类型，并解析文档架构</span><span class="sxs-lookup"><span data-stu-id="6f27f-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="6f27f-105">将已分析的 XML 序列化到 SWIFT 平面文件</span><span class="sxs-lookup"><span data-stu-id="6f27f-105">Serializes parsed XML into SWIFT flat files</span></span>  
  
 <span data-ttu-id="6f27f-106">你可以配置将用于编码 （例如，若要使用 ASCII 或 Unicode 编码） 序列化的输出的编码字符集。</span><span class="sxs-lookup"><span data-stu-id="6f27f-106">You can configure the encoding character set used for encoding the serialized output (for example, to use ASCII or Unicode encoding).</span></span>  
  
 <span data-ttu-id="6f27f-107">在开发期间使用 SWIFT 汇编程序在自定义发送管道配置 SWIFT 汇编程序。</span><span class="sxs-lookup"><span data-stu-id="6f27f-107">You configure the SWIFT assembler during development time of the custom send pipeline that uses the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="6f27f-108">BizTalk 管道设计器配置的自定义发送管道的开发期间 SWIFT 汇编程序。</span><span class="sxs-lookup"><span data-stu-id="6f27f-108">BizTalk Pipeline Designer configures the SWIFT assembler during development time of the custom send pipeline.</span></span>  
  
 <span data-ttu-id="6f27f-109">若要添加到自定义发送管道的组装阶段之后，请配置 SWIFT 汇编程序，选择管道设计器画布上的 SWIFT 汇编程序组件。</span><span class="sxs-lookup"><span data-stu-id="6f27f-109">To configure the SWIFT assembler after it has been added to the assemble stage of a custom send pipeline, select the SWIFT assembler component on the Pipeline Designer canvas.</span></span> <span data-ttu-id="6f27f-110">SWIFT 汇编程序然后接收焦点时，还可以设置其使用属性窗口中的配置属性[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f27f-110">The SWIFT assembler then receives focus, and you can set its configuration properties using the Properties window within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
 <span data-ttu-id="6f27f-111">有关可用的配置属性及其说明和用法的详细信息的表，请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="6f27f-111">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).</span></span>  
  
 <span data-ttu-id="6f27f-112">有关为不同的方案使用 SWIFT 汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="6f27f-112">For information about using the SWIFT assembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
 <span data-ttu-id="6f27f-113">编译该自定义管道二进制文件后，它将以静态方式向自定义管道将配置设置。</span><span class="sxs-lookup"><span data-stu-id="6f27f-113">When the custom pipeline binary is compiled, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="6f27f-114">因此，你无法在部署过程中更改配置属性，或运行时间。</span><span class="sxs-lookup"><span data-stu-id="6f27f-114">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f27f-115">配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署自定义的管道。</span><span class="sxs-lookup"><span data-stu-id="6f27f-115">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="6f27f-116">有关创建的信息，生成和部署自定义管道，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="6f27f-116">For information about creating, building, and deploying custom pipelines, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="6f27f-117">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="6f27f-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="6f27f-118">SWIFT 汇编程序配置属性</span><span class="sxs-lookup"><span data-stu-id="6f27f-118">SWIFT Assembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)