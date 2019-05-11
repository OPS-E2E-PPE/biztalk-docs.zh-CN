---
title: Loopback 教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f96d81e59686759300e996e2f257da5afbc91ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283290"
---
# <a name="loopback-tutorial"></a><span data-ttu-id="921f1-102">Loopback 教程</span><span class="sxs-lookup"><span data-stu-id="921f1-102">Loopback Tutorial</span></span>
<span data-ttu-id="921f1-103">本教程包含详细的步骤，描述如何使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]来模拟一台计算机上的家庭和合作伙伴组织之间的流程实施。</span><span class="sxs-lookup"><span data-stu-id="921f1-103">This tutorial contains detailed steps that describe how you can use Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to simulate a process implementation between the home and partner organization on a single computer.</span></span>  
  
 <span data-ttu-id="921f1-104">在实际生产环境中，您的合作伙伴组织实现驻留在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="921f1-104">In a real production environment, your partner organization implementation resides on a remote computer.</span></span> <span data-ttu-id="921f1-105">本教程使用 Loopback 实用工具创建镜像贸易协议，从而模拟贸易合作伙伴的同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="921f1-105">This tutorial uses the Loopback utility to create a mirror trading agreement to simulate the trading partner on the same computer.</span></span> <span data-ttu-id="921f1-106">使用单台计算机环回方案适用于开发和测试目的。</span><span class="sxs-lookup"><span data-stu-id="921f1-106">Using a single computer loop-back scenario works for development and test purposes.</span></span> <span data-ttu-id="921f1-107">建议您不应在生产环境中使用 Loopback 实用工具。</span><span class="sxs-lookup"><span data-stu-id="921f1-107">It is recommended that you do not to use the Loopback utility in a production environment.</span></span>  
  
 <span data-ttu-id="921f1-108">此环回方案不支持签名消息，并因此不支持不可否认性。</span><span class="sxs-lookup"><span data-stu-id="921f1-108">This loopback scenario does not support signing messages, and thus does not support non-repudiation.</span></span>  
  
 <span data-ttu-id="921f1-109">如果你具有证书颁发机构配置，且具有私钥的加密可用于测试目的，这种情况下支持加密的消息。</span><span class="sxs-lookup"><span data-stu-id="921f1-109">This scenario supports encryption of messages if you have a certification authority configured, and you have a private key for encryption available for test purposes.</span></span>  
  
 <span data-ttu-id="921f1-110">在本教程中，您将创建本组织、 合作伙伴组织和贸易协议、 使用 Loopback 实用工具创建镜像协议，，然后运行示例流程来验证环回方案。</span><span class="sxs-lookup"><span data-stu-id="921f1-110">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="921f1-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="921f1-111">In This Section</span></span>  
  
-   [<span data-ttu-id="921f1-112">准备教程</span><span class="sxs-lookup"><span data-stu-id="921f1-112">Preparing for the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [<span data-ttu-id="921f1-113">步骤 1：创建本组织</span><span class="sxs-lookup"><span data-stu-id="921f1-113">Step 1: Create the Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [<span data-ttu-id="921f1-114">步骤 2：创建合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="921f1-114">Step 2: Create the Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [<span data-ttu-id="921f1-115">步骤 3：编辑合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="921f1-115">Step 3: Edit the Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [<span data-ttu-id="921f1-116">步骤 4：创建贸易协议</span><span class="sxs-lookup"><span data-stu-id="921f1-116">Step 4: Create a Trade Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [<span data-ttu-id="921f1-117">步骤 5：创建镜像协议</span><span class="sxs-lookup"><span data-stu-id="921f1-117">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [<span data-ttu-id="921f1-118">步骤 6：启动业务流程</span><span class="sxs-lookup"><span data-stu-id="921f1-118">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [<span data-ttu-id="921f1-119">步骤 7：创建示例 LOB 消息</span><span class="sxs-lookup"><span data-stu-id="921f1-119">Step 7: Create a Sample LOB Message</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [<span data-ttu-id="921f1-120">步骤 8：在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="921f1-120">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)