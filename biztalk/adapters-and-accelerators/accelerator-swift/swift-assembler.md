---
title: SWIFT 汇编程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214429"
---
# <a name="swift-assembler"></a><span data-ttu-id="85e44-102">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="85e44-102">SWIFT Assembler</span></span>
<span data-ttu-id="85e44-103">出站发送管道处理所有消息传输的[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（通过发送端口发送） 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="85e44-103">An outbound send pipeline processes all messages transmitted by an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (sent through a send port).</span></span>  
  
 <span data-ttu-id="85e44-104">与出站处理相关的逻辑执行阶段构成了 BizTalk 发送管道。</span><span class="sxs-lookup"><span data-stu-id="85e44-104">Logical execution stages related to outbound processing make up the BizTalk send pipelines.</span></span> <span data-ttu-id="85e44-105">管道组件服务或实现的每个阶段。</span><span class="sxs-lookup"><span data-stu-id="85e44-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="85e44-106">具体而言，汇编程序服务中接收管道的装配阶段。</span><span class="sxs-lookup"><span data-stu-id="85e44-106">In particular, the assembler services the assemble stage in the receive pipeline.</span></span> <span data-ttu-id="85e44-107">A4SWIFT 提供特定于 SWIFT 的出站消息处理自定义汇编程序组件中的功能。</span><span class="sxs-lookup"><span data-stu-id="85e44-107">A4SWIFT provides SWIFT-specific outbound message processing functionality in a custom assembler component.</span></span>  
  
 <span data-ttu-id="85e44-108">SWIFT 汇编程序，一个自定义的平面文件的汇编程序，用于处理出站 SWIFT 消息，提供功能，并执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="85e44-108">The SWIFT assembler, a custom flat file assembler, provides functionality for processing outbound SWIFT messages, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="85e44-109">动态发现消息类型，并解析文档架构</span><span class="sxs-lookup"><span data-stu-id="85e44-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="85e44-110">将已分析的 XML 序列化到 SWIFT 平面文件</span><span class="sxs-lookup"><span data-stu-id="85e44-110">Serializes parsed XML into SWIFT flat files</span></span>  
  
 <span data-ttu-id="85e44-111">下图显示了 SWIFT 汇编程序数据流。</span><span class="sxs-lookup"><span data-stu-id="85e44-111">The following figure shows the SWIFT assembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 <span data-ttu-id="85e44-112">SWIFT 汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。</span><span class="sxs-lookup"><span data-stu-id="85e44-112">For more information about the SWIFT assembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e44-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85e44-113">See Also</span></span>  
 [<span data-ttu-id="85e44-114">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="85e44-114">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)