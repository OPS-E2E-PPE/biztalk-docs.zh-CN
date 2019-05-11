---
title: MSIT:从 Gentran 5.1 到 BizTalk 2010 的真实迁移故事 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31326e2f-fb86-4b2c-88cd-b9406695038b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b7c1342e0f7f08380c16db75bec9b8ee34b432b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320819"
---
# <a name="msit-real-world-migration-story-from-gentran-51-to-biztalk-2010"></a><span data-ttu-id="79c8e-102">MSIT:从 Gentran 5.1 到 BizTalk 2010 的真实迁移情景</span><span class="sxs-lookup"><span data-stu-id="79c8e-102">MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010</span></span>
<span data-ttu-id="79c8e-103">BizTalk 技术文章</span><span class="sxs-lookup"><span data-stu-id="79c8e-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="79c8e-104">**MSIT:从 Gentran 5.1 到 BizTalk 2010 的真实迁移情景**</span><span class="sxs-lookup"><span data-stu-id="79c8e-104">**MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010**</span></span>  
  
 <span data-ttu-id="79c8e-105">**作者：** Amit Kumar Dua，Microsoft &#124; Banupriya Thirumaran，Microsoft</span><span class="sxs-lookup"><span data-stu-id="79c8e-105">**Author:** Amit Kumar Dua, Microsoft  &#124;  Banupriya Thirumaran, Microsoft</span></span>  
  
 <span data-ttu-id="79c8e-106">**审阅者：** Mandi Ohlinger，Microsoft &#124; Nitin Mehrotra、 Microsoft</span><span class="sxs-lookup"><span data-stu-id="79c8e-106">**Reviewed By:** Mandi Ohlinger, Microsoft  &#124;  Nitin Mehrotra, Microsoft</span></span>  
  
 <span data-ttu-id="79c8e-107">**供稿人：** Nikhil Tayal，Microsoft &#124; Anil Chandra Lingam，Microsoft</span><span class="sxs-lookup"><span data-stu-id="79c8e-107">**Contributors:** Nikhil Tayal, Microsoft  &#124;  Anil Chandra Lingam, Microsoft</span></span>  
  
 <span data-ttu-id="79c8e-108">**发布日期：** 2014 年 10 月</span><span class="sxs-lookup"><span data-stu-id="79c8e-108">**Published:** October 2014</span></span>  
  
 <span data-ttu-id="79c8e-109">**适用于：** BizTalk Server 2010, Gentran Server</span><span class="sxs-lookup"><span data-stu-id="79c8e-109">**Applies To:** BizTalk Server 2010, Gentran Server</span></span>  
  
 <span data-ttu-id="79c8e-110">**摘要：** Microsoft IT (MSIT) 集成平台使用 BizTalk Server 和 Gentran。</span><span class="sxs-lookup"><span data-stu-id="79c8e-110">**Summary:** The Microsoft IT (MSIT) integration platform uses BizTalk Server and Gentran.</span></span> <span data-ttu-id="79c8e-111">直到最近，Microsoft IT 小组 Gentran 占用的良好状态。</span><span class="sxs-lookup"><span data-stu-id="79c8e-111">Until recently, Microsoft IT had a good presence of Gentran footprints.</span></span> <span data-ttu-id="79c8e-112">使用 BizTalk Server 中支持云计算和 AS2/EDI 功能，没有 Gentran 替换为 Microsoft BizTalk Server 2010 的机会。</span><span class="sxs-lookup"><span data-stu-id="79c8e-112">With BizTalk Server supporting cloud computing and AS2/EDI capabilities, there is an opportunity to replace Gentran with Microsoft BizTalk Server 2010.</span></span>  <span data-ttu-id="79c8e-113">Gentran 支持 Windows Server 2003 和 SQL server 2005;这是即将结束的延长支持。</span><span class="sxs-lookup"><span data-stu-id="79c8e-113">Gentran supports Windows Server 2003 and SQL server 2005; which are in extended support that is soon ending.</span></span> <span data-ttu-id="79c8e-114">Gentran 以支持较新的平台，包括 Windows Server 2008/2012年和 SQL Server 2008/2014年没有路线图。</span><span class="sxs-lookup"><span data-stu-id="79c8e-114">There is no roadmap for Gentran to support newer platforms, including Windows Server 2008/2012 and SQL Server 2008/2014.</span></span>  
  
 <span data-ttu-id="79c8e-115">MSIT 以的机会的形式查看此操作：</span><span class="sxs-lookup"><span data-stu-id="79c8e-115">MSIT viewed this as an opportunity to:</span></span>  
  
- <span data-ttu-id="79c8e-116">转到较新的技术平台</span><span class="sxs-lookup"><span data-stu-id="79c8e-116">Get to the newer technology platforms</span></span>  
  
- <span data-ttu-id="79c8e-117">删除可支持性约束</span><span class="sxs-lookup"><span data-stu-id="79c8e-117">Remove the supportability constraints</span></span>  
  
- <span data-ttu-id="79c8e-118">简化集成平台的整体体系结构</span><span class="sxs-lookup"><span data-stu-id="79c8e-118">Simplify the overall architecture of the integration platform</span></span>  
  
- <span data-ttu-id="79c8e-119">使集成平台，更经济高效且可靠</span><span class="sxs-lookup"><span data-stu-id="79c8e-119">Make the integration platform more cost effective and robust</span></span>  
  
  <span data-ttu-id="79c8e-120">BizTalk Server 2010 是经验证的集成平台，具有许多功能和特性，并支持新的平台技术。</span><span class="sxs-lookup"><span data-stu-id="79c8e-120">BizTalk Server 2010 is a proven integration platform, has numerous capabilities and features, and supports the new platform technologies.</span></span>  
  
  <span data-ttu-id="79c8e-121">本白皮书主要讨论的策略和执行将从 Gentran 5.1 迁移到 BizTalk Server 的步骤。</span><span class="sxs-lookup"><span data-stu-id="79c8e-121">This white paper discusses the strategy and steps taken to migrate from Gentran 5.1 to BizTalk Server.</span></span>  
  
  <span data-ttu-id="79c8e-122">若要查看该文档，请下载[MSIT:如何从 Gentran 5.1 真实世界迁移情况并将其保存到 BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word 文档。</span><span class="sxs-lookup"><span data-stu-id="79c8e-122">To review the document, please download the [MSIT: Real World Migration Story from Gentran 5.1 to BizTalk 2010](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Real%20World%20Migration%20Story%20from%20Gentran%20to%20BizTalk.docx) Word document.</span></span>