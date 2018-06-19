---
title: 从 SAP 系统用于 mySAP 适配器 BizTalk 发送到的 Idoc |Microsoft 文档
description: ''
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f7d1ccdaa8cb6a4ee12ad1cc4263c487a164c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215589"
---
# <a name="sending-idocs-from-an-sap-system"></a><span data-ttu-id="fc37d-102">从 SAP 系统发送到的 Idoc</span><span class="sxs-lookup"><span data-stu-id="fc37d-102">Sending IDOCs from an SAP System</span></span>
<span data-ttu-id="fc37d-103">在 SAP 系统将从 SAP 系统的 IDOC 发送到外部应用程序上完成的高级任务。</span><span class="sxs-lookup"><span data-stu-id="fc37d-103">High-level tasks to complete on the SAP system to send an IDOC from the SAP system to an external application.</span></span> <span data-ttu-id="fc37d-104">与您的 SAP 管理员联系以执行这些任务，或请参阅 SAP 指南。</span><span class="sxs-lookup"><span data-stu-id="fc37d-104">Contact your SAP administrator for performing these tasks or see the SAP guidance.</span></span>  
  
## <a name="send-an-idoc-from-sap"></a><span data-ttu-id="fc37d-105">从 SAP 发送 IDOC</span><span class="sxs-lookup"><span data-stu-id="fc37d-105">Send an IDOC from SAP</span></span>  
  
1.  <span data-ttu-id="fc37d-106">启动 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="fc37d-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="fc37d-107">创建使用 BD54 事务的逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="fc37d-107">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="fc37d-108">创建一个 RFC 目标中使用 SM59 事务的 TCP/IP 连接。</span><span class="sxs-lookup"><span data-stu-id="fc37d-108">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="fc37d-109">创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="fc37d-109">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="fc37d-110">创建合作伙伴配置文件具有必需的消息类型和 IDOC 类型使用 WE20 事务，然后将其附加到的最后一步中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="fc37d-110">Create a partner profile using WE20 transaction with the required message type and IDOC type, and then attach it to the port created in the last step.</span></span>  
  
6.  <span data-ttu-id="fc37d-111">通过连接到使用销售事务的端口的消息类型维护分布式的模型。</span><span class="sxs-lookup"><span data-stu-id="fc37d-111">Maintain a distributed model by connecting the message type to the port using the SALE transaction.</span></span>  
  
7.  <span data-ttu-id="fc37d-112">生成中 SAP IDOC。</span><span class="sxs-lookup"><span data-stu-id="fc37d-112">Generate an IDOC within SAP.</span></span> <span data-ttu-id="fc37d-113">例如，使用 BD10 事务来触发 MATMAS IDOC。</span><span class="sxs-lookup"><span data-stu-id="fc37d-113">For example, use BD10 transaction to trigger a MATMAS IDOC.</span></span> <span data-ttu-id="fc37d-114">有关其他事务来触发特定 Idoc 信息，请与您的 SAP 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="fc37d-114">Contact your SAP administrator for information about other transactions to trigger specific IDOCs.</span></span>  

## <a name="view-transaction-ids-in-sap"></a><span data-ttu-id="fc37d-115">SAP 中的视图事务 Id</span><span class="sxs-lookup"><span data-stu-id="fc37d-115">View Transaction IDs in SAP</span></span>
<span data-ttu-id="fc37d-116">当[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用 tRFC 或发送 IDOC 到 SAP 系统，SAP 系统寄存器事务 ID (TID) 在响应中。</span><span class="sxs-lookup"><span data-stu-id="fc37d-116">When the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] invokes a tRFC or sends an IDOC to an SAP system, the SAP system registers a transaction ID (TID) in response.</span></span> <span data-ttu-id="fc37d-117">在某些情况下，你可能需要知道与 SAP 系统以响应从调用注册 TID [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc37d-117">In some scenarios, you might need to know the TID that is registered with the SAP system in response to a call from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="fc37d-118">例如，你可能想要标识的工作 (LUW) 的逻辑单元上的 SAP 系统以解决问题。</span><span class="sxs-lookup"><span data-stu-id="fc37d-118">For example, you might want to identify the logical unit of work (LUW) on the SAP system to troubleshoot an issue.</span></span>  
  
 <span data-ttu-id="fc37d-119">若要查看 Tid SAP 系统中，你必须使用事务 SM58。</span><span class="sxs-lookup"><span data-stu-id="fc37d-119">To view the TIDs in an SAP system, you must use transaction SM58.</span></span> <span data-ttu-id="fc37d-120">请与您的 SAP 管理员或者参考有关此事务的详细信息的 SAP 指南。</span><span class="sxs-lookup"><span data-stu-id="fc37d-120">Contact your SAP administrator or refer to the SAP guidance for more information about this transaction.</span></span> 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a><span data-ttu-id="fc37d-121">查看有关发送和接收从 SAP Idoc 详细信息</span><span class="sxs-lookup"><span data-stu-id="fc37d-121">View details about IDOCs sent and received from SAP</span></span>
<span data-ttu-id="fc37d-122">使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，可以将 IDOC 发送到 SAP 系统，也可以从某个 SAP 系统接收 IDOC。</span><span class="sxs-lookup"><span data-stu-id="fc37d-122">Using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you can send an IDOC to an SAP system or receive an IDOC from an SAP system.</span></span> <span data-ttu-id="fc37d-123">若要跟踪某个 SAP 系统的状态和视图的数据的 IDOC 发送或接收，可以使用事务 WE02。</span><span class="sxs-lookup"><span data-stu-id="fc37d-123">To track the status and view the data of an IDOC sent or received by an SAP system, you can use transaction WE02.</span></span> <span data-ttu-id="fc37d-124">请与您的 SAP 管理员，或参阅有关此事务的详细信息的 SAP 指南。</span><span class="sxs-lookup"><span data-stu-id="fc37d-124">Contact your SAP administrator, or refer to the SAP guidance for more information about this transaction.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="fc37d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc37d-125">See Also</span></span>  
 [<span data-ttu-id="fc37d-126">对于特定 SAP 适配器方案中使用 SAP GUI 执行任务</span><span class="sxs-lookup"><span data-stu-id="fc37d-126">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)