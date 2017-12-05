---
title: "RNIF 管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNIF, pipelines
- pipelines, RNIF
ms.assetid: 6cf480fe-6b54-4b13-8318-617f3bba71d0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cfdc50906f356a7eceeea50dd716c903720f785
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="rnif-pipelines"></a><span data-ttu-id="417d8-102">RNIF 管道</span><span class="sxs-lookup"><span data-stu-id="417d8-102">RNIF Pipelines</span></span>
<span data-ttu-id="417d8-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]接收和发送管道执行接收所需的处理或发送 RosettaNet 实现框架 (RNIF) 消息。</span><span class="sxs-lookup"><span data-stu-id="417d8-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive and send pipelines perform the processing required for receive or send RosettaNet Implementation Framework (RNIF) messages.</span></span> <span data-ttu-id="417d8-104">此处理过程包括预处理、解码/编码、解密/加密、拆装/组装以及参与方验证。</span><span class="sxs-lookup"><span data-stu-id="417d8-104">This processing includes preprocessing, decoding/encoding, decrypting/encrypting, disassembly/assembly, and party authentication.</span></span>  
  
## <a name="pipeline-files"></a><span data-ttu-id="417d8-105">管道文件</span><span class="sxs-lookup"><span data-stu-id="417d8-105">Pipeline Files</span></span>  
 <span data-ttu-id="417d8-106">标准[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收和发送管道不以本机方式处理 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="417d8-106">Standard [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive and send pipelines do not process RNIF messages natively.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="417d8-107">已添加自定义接收和发送管道实现此目的。</span><span class="sxs-lookup"><span data-stu-id="417d8-107"> has added custom receive and send pipelines for this purpose.</span></span> <span data-ttu-id="417d8-108">这些管道基于 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管道构建，但添加了 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 特定的处理功能。</span><span class="sxs-lookup"><span data-stu-id="417d8-108">These pipelines are built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] pipelines, but add [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-specific processing capability.</span></span> <span data-ttu-id="417d8-109">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管道 （RNIFReceive.btp 和 RNIFSend.btp） 位于[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK: \<*驱动器*\>: \Microsoft BizTalk\<版本\>RosettaNet\SDK\RNPipelines 快捷键。</span><span class="sxs-lookup"><span data-stu-id="417d8-109">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipelines (RNIFReceive.btp and RNIFSend.btp) are available in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK at \<*drive*\>:\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="417d8-110">这可让你根据自己的目的来自定义管道。</span><span class="sxs-lookup"><span data-stu-id="417d8-110">This lets you customize them for your own purposes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417d8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="417d8-111">See Also</span></span>  
 <span data-ttu-id="417d8-112">[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="417d8-112">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="417d8-113">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="417d8-113">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)