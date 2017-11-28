---
title: "MSIT： 实际迁移情景从 Gentran 5.1 到 BizTalk 2010 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31326e2f-fb86-4b2c-88cd-b9406695038b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b742777c5e547078c2fa3fbf1a8d5bd8c466924
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="e5adb-102">MSIT： 实际迁移情景从 Gentran 5.1 到 BizTalk 2010</span><span class="sxs-lookup"><span data-stu-id="e5adb-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="e5adb-103">BizTalk 技术文章</span><span class="sxs-lookup"><span data-stu-id="e5adb-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="e5adb-104">**MSIT： 实际迁移情景从 Gentran 5.1 到 BizTalk 2010**</span><span class="sxs-lookup"><span data-stu-id="e5adb-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="e5adb-105">**作者：** Amit Kumar Dua、 Microsoft &#124; Banupriya Thirumaran Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5adb-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="e5adb-106">**审阅者：** Mandi Ohlinger、 Microsoft &#124; Nitin Mehrotra Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5adb-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="e5adb-107">**供稿人：** Nikhil Tayal，Microsoft &#124; Anil Chandra Lingam Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5adb-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="e5adb-108">**发布日期：** 2014 年 10 月</span><span class="sxs-lookup"><span data-stu-id="e5adb-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="e5adb-109">**适用于：** BizTalk Server 2010，Gentran 服务器</span><span class="sxs-lookup"><span data-stu-id="e5adb-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="e5adb-110">**摘要：** Microsoft IT (MSIT) 集成平台使用 BizTalk Server 和 Gentran。</span><span class="sxs-lookup"><span data-stu-id="e5adb-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="e5adb-111">直到最近，Microsoft IT 小组 Gentran 空间占用量良好状态。</span><span class="sxs-lookup"><span data-stu-id="e5adb-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="e5adb-112">与 BizTalk Server 中支持云计算和 AS2/EDI 功能，没有机会 Gentran 替换 Microsoft BizTalk Server 2010。</span><span class="sxs-lookup"><span data-stu-id="e5adb-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="e5adb-113">Gentran 支持 Windows Server 2003 和 SQL server 2005;它们都位于即将结束的扩展支持。</span><span class="sxs-lookup"><span data-stu-id="e5adb-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="e5adb-114">没有任何路线图 Gentran 以支持较新的平台，包括 Windows Server 2008/2012年和 SQL Server 2008/2014年。</span><span class="sxs-lookup"><span data-stu-id="e5adb-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="e5adb-115">MSIT 为这视为的机会：</span><span class="sxs-lookup"><span data-stu-id="e5adb-115">MSIT viewed this as an opportunity to:</span></span>  
  
-   <span data-ttu-id="e5adb-116">获取到较新的技术平台</span><span class="sxs-lookup"><span data-stu-id="e5adb-116">Get to the newer technology platforms</span></span>  
  
-   <span data-ttu-id="e5adb-117">删除可支持性约束</span><span class="sxs-lookup"><span data-stu-id="e5adb-117">Remove the supportability constraints</span></span>  
  
-   <span data-ttu-id="e5adb-118">简化集成平台的总体体系结构</span><span class="sxs-lookup"><span data-stu-id="e5adb-118">Simplify the overall architecture of the integration platform</span></span>  
  
-   <span data-ttu-id="e5adb-119">使集成平台，更经济高效且更可靠</span><span class="sxs-lookup"><span data-stu-id="e5adb-119">Make the integration platform more cost effective and robust</span></span>  
  
 <span data-ttu-id="e5adb-120">BizTalk Server 2010 是一个经验证的集成平台，具有许多功能和特性，并支持新的平台技术。</span><span class="sxs-lookup"><span data-stu-id="e5adb-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
 <span data-ttu-id="e5adb-121">本白皮书讨论的策略和执行将从 Gentran 5.1 迁移到 BizTalk Server 的步骤。</span><span class="sxs-lookup"><span data-stu-id="e5adb-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
 <span data-ttu-id="e5adb-122">若要查看该文档，请下载[MSIT： 如何从 Gentran 5.1 真实世界迁移情景并将其保存到 BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word 文档。</span><span class="sxs-lookup"><span data-stu-id="e5adb-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>