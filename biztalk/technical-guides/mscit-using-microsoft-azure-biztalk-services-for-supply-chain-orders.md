---
title: "MSCIT： 使用 Microsoft Azure BizTalk 服务用于供应链订单 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22091261-cd17-45b2-8746-dc174b52dcff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a1609be7326db4988d31d51597cde3fd280227
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mscit-using-microsoft-azure-biztalk-services-for-supply-chain-orders"></a><span data-ttu-id="2261e-102">MSCIT： 使用 Microsoft Azure BizTalk 服务用于供应链订单</span><span class="sxs-lookup"><span data-stu-id="2261e-102">MSCIT: Using Microsoft Azure BizTalk Services for Supply Chain Orders</span></span>
<span data-ttu-id="2261e-103">**Microsoft 设备 （&) Studio： 使用 Microsoft Azure BizTalk 服务用于供应链订单**</span><span class="sxs-lookup"><span data-stu-id="2261e-103">**Microsoft Devices & Studios: Using Microsoft Azure BizTalk Services for Supply Chain Orders**</span></span>  
  
 <span data-ttu-id="2261e-104">BizTalk 技术文章</span><span class="sxs-lookup"><span data-stu-id="2261e-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="2261e-105">**编写器：** Anil Kongari (Microsoft) Dipti Sharma (Microsoft) Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="2261e-105">**Writer:** Anil Kongari (Microsoft), Dipti Sharma (Microsoft), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="2261e-106">**技术审阅人员：** Anil Kongari (Microsoft)、 Hariharan Sundaram (Microsoft)、 Dipti Sharma (Microsoft)、 Heena Parmar (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="2261e-106">**Technical Reviewers:** Anil Kongari (Microsoft), Hariharan Sundaram (Microsoft), Dipti Sharma (Microsoft), Heena Parmar (Microsoft)</span></span>  
  
 <span data-ttu-id="2261e-107">**发布日期：** 2013 年 10 月</span><span class="sxs-lookup"><span data-stu-id="2261e-107">**Published:** October 2013</span></span>  
  
 <span data-ttu-id="2261e-108">**适用于：** Microsoft Azure BizTalk 服务 (MABS) 和 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="2261e-108">**Applies To:** Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013</span></span>  
  
 <span data-ttu-id="2261e-109">**摘要：**制造、 供应链和信息服务 (MSCIS) 组是在 Microsoft Global Supply Chain Management 组。</span><span class="sxs-lookup"><span data-stu-id="2261e-109">**Summary:** The Manufacturing, Supply Chain, and Information Services (MSCIS) group is a Global Supply Chain Management group at Microsoft.</span></span> <span data-ttu-id="2261e-110">每年，Microsoft 将启动新产品。</span><span class="sxs-lookup"><span data-stu-id="2261e-110">Every year, Microsoft launches new products.</span></span> <span data-ttu-id="2261e-111">MSCIS 负责将这些新产品推向市场。</span><span class="sxs-lookup"><span data-stu-id="2261e-111">MSCIS is responsible for bringing these new products to market.</span></span> <span data-ttu-id="2261e-112">若要支持这些产品，新的合作伙伴添加到供应链，其中包括供应商、 制造商、 分发服务器、 零售商、 服务中心、 运营商和等等。</span><span class="sxs-lookup"><span data-stu-id="2261e-112">To support these products, new partners are added to the Supply Chain, including Supplier, Manufacturer, Distributor, Retailer, Service Center, Carrier, and so on.</span></span>  
  
 <span data-ttu-id="2261e-113">合作伙伴事务数会增加每年。</span><span class="sxs-lookup"><span data-stu-id="2261e-113">The number of partner transactions increases yearly.</span></span> <span data-ttu-id="2261e-114">在高负载，过程有吞吐量与相关的问题。</span><span class="sxs-lookup"><span data-stu-id="2261e-114">During high load, there are issues related to throughput.</span></span> <span data-ttu-id="2261e-115">虽然提供链 BizTalk 中心处理更多的事务 （增加的卷），结束系统或合作伙伴系统不能够保持同步。</span><span class="sxs-lookup"><span data-stu-id="2261e-115">While the Supply Chain BizTalk hub processes more transactions (increased volume), the end system or partner system is not able to keep up.</span></span>  
  
 <span data-ttu-id="2261e-116">当前的困难在于如何准备峰值销售企业到企业 (B2B) 系统。</span><span class="sxs-lookup"><span data-stu-id="2261e-116">The current challenge is to prepare the business-to-business (B2B) systems for peak sales.</span></span> <span data-ttu-id="2261e-117">作为一部分的技术采用计划 (TAP)，MSCIS 浏览平台即服务 (PaaS) 使用 Microsoft Azure BizTalk 服务 (MABS)。</span><span class="sxs-lookup"><span data-stu-id="2261e-117">As part of Technology Adoption Program (TAP), MSCIS is exploring Platform as a Service (PaaS) using Microsoft Azure BizTalk Services (MABS).</span></span> <span data-ttu-id="2261e-118">MABS 提供可以解决缩放情况的关键功能。</span><span class="sxs-lookup"><span data-stu-id="2261e-118">MABS provides key capabilities that can solve the scale situation.</span></span> <span data-ttu-id="2261e-119">MSCIS 创建概念的概念 (POC) 涉及使用 Microsoft Azure BizTalk 服务 (MABS) 和 BizTalk Server 2013 的混合解决方案。</span><span class="sxs-lookup"><span data-stu-id="2261e-119">MSCIS created a Proof of Concept (POC) involving a hybrid solution that uses Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span> <span data-ttu-id="2261e-120">要求是提供完美执行从端到端复制，正常销售下包括注册峰值销售和刻度的功能。</span><span class="sxs-lookup"><span data-stu-id="2261e-120">The requirement is to provide flawless execution from end-to-end, including the ability to scale up for peak sales and scale down for normal sales.</span></span>  
  
 <span data-ttu-id="2261e-121">本白皮书讨论了使用 Microsoft Azure BizTalk 服务 (MABS) 和 BizTalk Server 2013 测试的解决方案。</span><span class="sxs-lookup"><span data-stu-id="2261e-121">This white paper discusses the solutions tested using Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span>  
  
 <span data-ttu-id="2261e-122">若要查看该文档，请下载[使用 Microsoft Azure BizTalk 服务用于供应链订单](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx)Word 文档。</span><span class="sxs-lookup"><span data-stu-id="2261e-122">To review the document, please download the [Using Microsoft Azure BizTalk Services for Supply Chain Orders](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx) Word document.</span></span>