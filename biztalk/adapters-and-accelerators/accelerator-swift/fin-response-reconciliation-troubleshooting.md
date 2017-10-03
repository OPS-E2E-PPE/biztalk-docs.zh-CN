---
title: "FIN 响应对帐疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a92812086f191d5777b387d9861b32a3147c1e96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-troubleshooting"></a><span data-ttu-id="1efc0-102">FIN 响应对帐故障排除</span><span class="sxs-lookup"><span data-stu-id="1efc0-102">FIN Response Reconciliation Troubleshooting</span></span>
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a><span data-ttu-id="1efc0-103">FRR BAM 视图不显示一条消息的消息类型</span><span class="sxs-lookup"><span data-stu-id="1efc0-103">The FRR BAM view does not show the message type of a message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1efc0-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="1efc0-104">Symptom</span></span>  
 <span data-ttu-id="1efc0-105">MRSR 站点中的 FRR BAM 视图不显示一个或多个消息的消息类型。</span><span class="sxs-lookup"><span data-stu-id="1efc0-105">The FRR BAM view in MRSR site does not show the message type for one or more messages.</span></span> <span data-ttu-id="1efc0-106">显示的消息或消息的所有其他数据，并为显示的消息类型的所有其他消息类型的实例。</span><span class="sxs-lookup"><span data-stu-id="1efc0-106">All other data for the message or messages is shown, and the message type is shown for instances of all other message types.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1efc0-107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="1efc0-107">Possible Cause</span></span>  
 <span data-ttu-id="1efc0-108">FRRMessageOut 活动不会记录 F21 消息 (Ack/NAKs) 的消息类型。</span><span class="sxs-lookup"><span data-stu-id="1efc0-108">The FRRMessageOut activity does not record the message type for F21 messages (ACKs/NAKs).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1efc0-109">解决方案</span><span class="sxs-lookup"><span data-stu-id="1efc0-109">Solution</span></span>  
 <span data-ttu-id="1efc0-110">如果你遇到此问题，解释没有作为 F21 消息 MRSR 站点中的 FRR BAM 视图中列出的消息类型的任何消息。</span><span class="sxs-lookup"><span data-stu-id="1efc0-110">If you encounter this problem, interpret any message that does not have a message type listed in the FRR BAM view in MRSR site as an F21 message.</span></span>  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a><span data-ttu-id="1efc0-111">部署项目中的系统级架构生成一个错误</span><span class="sxs-lookup"><span data-stu-id="1efc0-111">Deploying system-level schemas in a project generates an error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1efc0-112">故障现象</span><span class="sxs-lookup"><span data-stu-id="1efc0-112">Symptom</span></span>  
 <span data-ttu-id="1efc0-113">当你尝试部署中 FrrSchemas.dll 项目中的系统级架构时，你将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="1efc0-113">When you attempt to deploy the system-level schemas in FrrSchemas.dll in a project, you receive an error.</span></span> <span data-ttu-id="1efc0-114">有关这些架构的列表，请参阅[FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1efc0-114">For a list of these schemas, see [FIN Response Types](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1efc0-115">可能的原因</span><span class="sxs-lookup"><span data-stu-id="1efc0-115">Possible Cause</span></span>  
 <span data-ttu-id="1efc0-116">FrrSchemas.dll 中的系统级架构已部署在 FrrSchemas.dll。</span><span class="sxs-lookup"><span data-stu-id="1efc0-116">The system-level schemas in FrrSchemas.dll are already deployed in FrrSchemas.dll.</span></span> <span data-ttu-id="1efc0-117">尝试将它们部署再次导致错误。</span><span class="sxs-lookup"><span data-stu-id="1efc0-117">Trying to deploy them again results in an error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1efc0-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="1efc0-118">Solution</span></span>  
 <span data-ttu-id="1efc0-119">没有无需部署中 FrrSchemas.dll 的系统级架构。</span><span class="sxs-lookup"><span data-stu-id="1efc0-119">There is no need to deploy the system-level schemas in FrrSchemas.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1efc0-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1efc0-120">See Also</span></span>  
 [<span data-ttu-id="1efc0-121">疑难解答： 问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="1efc0-121">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)