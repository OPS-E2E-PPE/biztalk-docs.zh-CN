---
title: 自定义处理程序的消息的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8ba2b085268f2c0c272b81b27768db716b63c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996150"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a><span data-ttu-id="e2bd1-102">自定义处理程序的消息的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="e2bd1-102">FRR Send Ports for Messages to the Custom Handlers</span></span>
<span data-ttu-id="e2bd1-103">若要启用 FRR 自定义处理程序，必须创建一系列的 FRR 发送端口，每个将某一类型的原始消息的副本路由到自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2bd1-103">To enable custom handlers for FRR, you must create a series of FRR send ports, each one of which routes a copy of an original message of a certain type to the custom handlers.</span></span> <span data-ttu-id="e2bd1-104">这些发送端口都必须具有以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="e2bd1-104">These send ports must have the following pipeline components:</span></span>  

- <span data-ttu-id="e2bd1-105">SWIFT 汇编程序的组装阶段中</span><span class="sxs-lookup"><span data-stu-id="e2bd1-105">The SWIFT assembler in the Assemble stage</span></span>  

- <span data-ttu-id="e2bd1-106">SWIFTSendFrrComponent 管道组件中的编码阶段</span><span class="sxs-lookup"><span data-stu-id="e2bd1-106">The SWIFTSendFrrComponent pipeline component in the Encode stage</span></span>  

  <span data-ttu-id="e2bd1-107">对于除类别 0 到 9 SWIFT FIN 消息未成功发送的所有消息，发送端口必须具有以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="e2bd1-107">For all messages except Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="e2bd1-108">_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="e2bd1-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- <span data-ttu-id="e2bd1-109">BTS。操作设置为每种消息类型所需的值。</span><span class="sxs-lookup"><span data-stu-id="e2bd1-109">BTS.Operation set to the value required for each message type.</span></span> <span data-ttu-id="e2bd1-110">有关可能的值为 BTS。操作属性，请参阅中的表[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="e2bd1-110">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  

  <span data-ttu-id="e2bd1-111">对于未成功发送的类别 0 到 9 SWIFT FIN 消息，发送端口必须具有以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="e2bd1-111">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="e2bd1-112">_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="e2bd1-112">_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="e2bd1-113">_FrrFailed = = true</span><span class="sxs-lookup"><span data-stu-id="e2bd1-113">_FrrFailed==True</span></span>  

- <span data-ttu-id="e2bd1-114">BTS。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span><span class="sxs-lookup"><span data-stu-id="e2bd1-114">BTS.Operation==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="e2bd1-115">_FRRFailedReason 设置为每种消息类型所需的值。</span><span class="sxs-lookup"><span data-stu-id="e2bd1-115">_FRRFailedReason set to the value required for each message type.</span></span> <span data-ttu-id="e2bd1-116">有关可能的值为 BTS。操作属性，请参阅中的表[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="e2bd1-116">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>
