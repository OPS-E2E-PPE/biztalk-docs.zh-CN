---
title: 配置 SWIFT 反汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f13de9a2b1566a289d2abee63035e9d1462bf44d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378526"
---
# <a name="configuring-the-swift-disassembler"></a><span data-ttu-id="12325-102">配置 SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="12325-102">Configuring the SWIFT Disassembler</span></span>
<span data-ttu-id="12325-103">SWIFT 反汇编程序 (DASM) 执行以下任务时调用在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：</span><span class="sxs-lookup"><span data-stu-id="12325-103">The SWIFT disassembler (DASM) performs the following tasks when you invoke it in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
- <span data-ttu-id="12325-104">动态发现消息类型和解析文档架构</span><span class="sxs-lookup"><span data-stu-id="12325-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="12325-105">将 SWIFT 平面文件分析为 XML</span><span class="sxs-lookup"><span data-stu-id="12325-105">Parses SWIFT flat files into XML</span></span>  
  
- <span data-ttu-id="12325-106">调用验证读取器执行 XML （架构） 验证 XML</span><span class="sxs-lookup"><span data-stu-id="12325-106">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
- <span data-ttu-id="12325-107">调用业务规则引擎 (BRE) 执行 BRE 验证</span><span class="sxs-lookup"><span data-stu-id="12325-107">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
- <span data-ttu-id="12325-108">将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML</span><span class="sxs-lookup"><span data-stu-id="12325-108">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
- <span data-ttu-id="12325-109">进程的入站的批处理</span><span class="sxs-lookup"><span data-stu-id="12325-109">Processes inbound batches</span></span>  
  
  <span data-ttu-id="12325-110">你可以配置以满足用户方案的特定要求上面所列的功能和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="12325-110">You can configure the functionality listed above to meet the specific requirements for a user scenario and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solution.</span></span>  
  
  <span data-ttu-id="12325-111">BizTalk 管道设计器在开发时的自定义接收管道配置 SWIFT 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="12325-111">BizTalk Pipeline Designer configures the SWIFT disassembler during development time of the custom receive pipeline.</span></span>  
  
  <span data-ttu-id="12325-112">若要配置 SWIFT 反汇编程序添加到自定义接收管道的拆装阶段之后，选择 BizTalk 管道设计器画布上的 SWIFT 反汇编程序组件。</span><span class="sxs-lookup"><span data-stu-id="12325-112">To configure the SWIFT disassembler after it has been added to the disassemble stage of a custom receive pipeline, select the SWIFT disassembler component on the BizTalk Pipeline Designer canvas.</span></span> <span data-ttu-id="12325-113">SWIFT 反汇编程序然后接收焦点，并可以设置其配置属性，使用 Microsoft 中的属性窗口[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="12325-113">The SWIFT disassembler then receives focus and you can set its configuration properties using the Properties window within Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
  <span data-ttu-id="12325-114">有关可用的配置属性及其说明和使用情况详细信息的表，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="12325-114">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span>  
  
  <span data-ttu-id="12325-115">有关不同的情况下使用 SWIFT 反汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="12325-115">For information about using the SWIFT disassembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
  <span data-ttu-id="12325-116">当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]编译二进制文件，以静态方式配置设置写入到自定义管道的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="12325-116">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compiles the custom pipeline binary, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="12325-117">因此，不能在部署过程中更改配置属性，或运行时。</span><span class="sxs-lookup"><span data-stu-id="12325-117">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12325-118">配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="12325-118">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="12325-119">有关创建、 生成和部署自定义管道的信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="12325-119">For information about creating, building, and deploying custom pipelines, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="12325-120">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="12325-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="12325-121">SWIFT 反汇编程序配置属性</span><span class="sxs-lookup"><span data-stu-id="12325-121">SWIFT Disassembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)