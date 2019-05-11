---
title: FIN 响应对帐疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fa60b9b9f3034e795c191cc6a40e7288f195ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377800"
---
# <a name="fin-response-reconciliation-troubleshooting"></a><span data-ttu-id="d781a-102">FIN 响应对帐疑难解答</span><span class="sxs-lookup"><span data-stu-id="d781a-102">FIN Response Reconciliation Troubleshooting</span></span>
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a><span data-ttu-id="d781a-103">FRR BAM 视图不显示一条消息的消息类型</span><span class="sxs-lookup"><span data-stu-id="d781a-103">The FRR BAM view does not show the message type of a message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d781a-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="d781a-104">Symptom</span></span>  
 <span data-ttu-id="d781a-105">MRSR 站点中的 FRR BAM 视图不显示一个或多个消息的消息类型。</span><span class="sxs-lookup"><span data-stu-id="d781a-105">The FRR BAM view in MRSR site does not show the message type for one or more messages.</span></span> <span data-ttu-id="d781a-106">显示为消息或消息的所有其他数据，并且消息类型显示的所有其他消息类型的实例。</span><span class="sxs-lookup"><span data-stu-id="d781a-106">All other data for the message or messages is shown, and the message type is shown for instances of all other message types.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="d781a-107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d781a-107">Possible Cause</span></span>  
 <span data-ttu-id="d781a-108">FRRMessageOut 活动不会记录 F21 消息 (Ack/NAKs) 的消息类型。</span><span class="sxs-lookup"><span data-stu-id="d781a-108">The FRRMessageOut activity does not record the message type for F21 messages (ACKs/NAKs).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="d781a-109">解决方案</span><span class="sxs-lookup"><span data-stu-id="d781a-109">Solution</span></span>  
 <span data-ttu-id="d781a-110">如果遇到此问题，将不具有作为 F21 消息 MRSR 站点中的 FRR BAM 视图中列出的消息类型的任何消息。</span><span class="sxs-lookup"><span data-stu-id="d781a-110">If you encounter this problem, interpret any message that does not have a message type listed in the FRR BAM view in MRSR site as an F21 message.</span></span>  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a><span data-ttu-id="d781a-111">部署项目中的系统级架构将生成错误</span><span class="sxs-lookup"><span data-stu-id="d781a-111">Deploying system-level schemas in a project generates an error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d781a-112">故障现象</span><span class="sxs-lookup"><span data-stu-id="d781a-112">Symptom</span></span>  
 <span data-ttu-id="d781a-113">当你尝试部署 FrrSchemas.dll 中在项目中的系统级架构时，您将收到错误。</span><span class="sxs-lookup"><span data-stu-id="d781a-113">When you attempt to deploy the system-level schemas in FrrSchemas.dll in a project, you receive an error.</span></span> <span data-ttu-id="d781a-114">有关这些架构中的列表，请参阅[FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d781a-114">For a list of these schemas, see [FIN Response Types](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="d781a-115">可能的原因</span><span class="sxs-lookup"><span data-stu-id="d781a-115">Possible Cause</span></span>  
 <span data-ttu-id="d781a-116">已部署在 FrrSchemas.dll FrrSchemas.dll 中的系统级架构。</span><span class="sxs-lookup"><span data-stu-id="d781a-116">The system-level schemas in FrrSchemas.dll are already deployed in FrrSchemas.dll.</span></span> <span data-ttu-id="d781a-117">尝试将其部署再次导致错误。</span><span class="sxs-lookup"><span data-stu-id="d781a-117">Trying to deploy them again results in an error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="d781a-118">解决方案</span><span class="sxs-lookup"><span data-stu-id="d781a-118">Solution</span></span>  
 <span data-ttu-id="d781a-119">没有必要部署 FrrSchemas.dll 中的系统级架构。</span><span class="sxs-lookup"><span data-stu-id="d781a-119">There is no need to deploy the system-level schemas in FrrSchemas.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d781a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d781a-120">See Also</span></span>  
 [<span data-ttu-id="d781a-121">故障排除：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="d781a-121">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)