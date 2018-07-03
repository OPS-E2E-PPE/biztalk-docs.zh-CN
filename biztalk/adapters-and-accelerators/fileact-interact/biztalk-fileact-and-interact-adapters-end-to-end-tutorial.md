---
title: BizTalk FileAct 和交互适配器端到端教程 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fbfb10-73e8-4365-a943-bcb9055f4f74
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af083b0e38d372c18bca4496033983cd7f579347
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014798"
---
# <a name="biztalk-fileact-and-interact-adapters-end-to-end-tutorial"></a><span data-ttu-id="05d02-102">BizTalk FileAct 和交互适配器端到端教程</span><span class="sxs-lookup"><span data-stu-id="05d02-102">BizTalk FileAct and InterAct Adapters End-to-End Tutorial</span></span>
<span data-ttu-id="05d02-103">The Microsoft®[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]端到端教程提供了有关如何使用的特定信息[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]来设置实时和存储和转发消息交换方案。</span><span class="sxs-lookup"><span data-stu-id="05d02-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-to-End Tutorial provides specific information about how you can use [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to set up real-time and store and forward message exchange scenarios.</span></span>  
  
 <span data-ttu-id="05d02-104">[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]端到端教程提供了四个不同的方案包括的每种类型的解决方案的教程形式的详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="05d02-104">The [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial provides four separate scenarios that include detailed steps in the form of tutorials for each type of solution.</span></span> <span data-ttu-id="05d02-105">在开始这些教程之前，应了解 BizTalk Server 的基本概念并熟悉 SWIFT 联盟网关 （压降） 文档。</span><span class="sxs-lookup"><span data-stu-id="05d02-105">Before you begin these tutorials, you should understand the fundamental concepts surrounding BizTalk Server, and be familiar with the SWIFT Alliance Gateway (SAG) documentation.</span></span>  
  
 <span data-ttu-id="05d02-106">A4SWIFT 端到端教程可配置实时的详细的步骤和 FileAct 和 InterAct 适配器存储和转发方案的 A4Swift。</span><span class="sxs-lookup"><span data-stu-id="05d02-106">The A4SWIFT end-to-end tutorial provides you with detailed steps to configure real-time and store-and-forward scenarios with both the FileAct and InterAct adapters for A4Swift.</span></span> <span data-ttu-id="05d02-107">对于每个方案中，将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05d02-107">For each of the scenarios, you will do the following:</span></span>  
  
- <span data-ttu-id="05d02-108">配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="05d02-108">Configure the SWIFT adapter</span></span>  
  
- <span data-ttu-id="05d02-109">配置 SWIFTNet paramfile</span><span class="sxs-lookup"><span data-stu-id="05d02-109">Configure the SWIFTNet paramfile</span></span>  
  
- <span data-ttu-id="05d02-110">创建发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="05d02-110">Create send ports and receive ports</span></span>  
  
- <span data-ttu-id="05d02-111">测试方案</span><span class="sxs-lookup"><span data-stu-id="05d02-111">Test the scenario</span></span>  
  
  <span data-ttu-id="05d02-112">在本教程中，您将扮演两个角色： 发送方和接收方。</span><span class="sxs-lookup"><span data-stu-id="05d02-112">In this tutorial, you will play two roles: Sender and Receiver.</span></span> <span data-ttu-id="05d02-113">您将创建将消息发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="05d02-113">You will create ports that send messages and receive them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05d02-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="05d02-114">In This Section</span></span>  
  
-   [<span data-ttu-id="05d02-115">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="05d02-115">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)  
  
-   [<span data-ttu-id="05d02-116">InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="05d02-116">InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="05d02-117">InterAct 存储和转发（推送）方案</span><span class="sxs-lookup"><span data-stu-id="05d02-117">InterAct Store and Forward (Push) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)  
  
-   [<span data-ttu-id="05d02-118">FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="05d02-118">FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="05d02-119">FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="05d02-119">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)