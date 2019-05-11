---
title: 在 BizTalk Server 中 proactivity |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b924ddae-0e7f-4058-b308-7ea9537fb45f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d232d7dec46c4de7ebb523bfaa7543db258009d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65252942"
---
# <a name="proactivity-in-biztalk-server"></a><span data-ttu-id="69839-102">BizTalk Server 中的主动性</span><span class="sxs-lookup"><span data-stu-id="69839-102">Proactivity in BizTalk Server</span></span>
<span data-ttu-id="69839-103">BizTalk 技术文章</span><span class="sxs-lookup"><span data-stu-id="69839-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="69839-104">**BizTalk Server 中的主动性**</span><span class="sxs-lookup"><span data-stu-id="69839-104">**Proactivity in BizTalk Server**</span></span>  
  
 <span data-ttu-id="69839-105">**编写器：** Tord 很高兴 Nordahl (布韦 AS)</span><span class="sxs-lookup"><span data-stu-id="69839-105">**Writer:** Tord Glad Nordahl (Bouvet AS)</span></span>  
  
 <span data-ttu-id="69839-106">**技术审阅人员：** Sandro Pereira (Devscope)、 Erik Thue （布韦作为）、 Jan Wiggers (Motion10)、 Alexander Thue （布韦作为）、 Saravana Kumar (BizTalk360) Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="69839-106">**Technical Reviewers:** Sandro Pereira (Devscope), Steef-Jan Wiggers (Motion10), Erik Thue (Bouvet AS), Alexander Thue (Bouvet AS), Saravana Kumar  (BizTalk360), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="69839-107">**发布日期：** 2013 年 7 月</span><span class="sxs-lookup"><span data-stu-id="69839-107">**Published:** July 2013</span></span>  
  
 <span data-ttu-id="69839-108">**适用于：** BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="69839-108">**Applies To:** BizTalk Server</span></span>  
  
 <span data-ttu-id="69839-109">**摘要：** 白皮书从 BizTalk Server 2004 适用于 BizTalk Server 2013 环境。</span><span class="sxs-lookup"><span data-stu-id="69839-109">**Summary:** The white paper applies from BizTalk Server 2004 to BizTalk Server 2013 environments.</span></span>  <span data-ttu-id="69839-110">目标是提供了如何主动和解决，或避免潜在问题发生之前将其一些见解。</span><span class="sxs-lookup"><span data-stu-id="69839-110">The goal is to provide some insight of how to be proactive and resolve, or avoid, potential problems before they occur.</span></span> <span data-ttu-id="69839-111">它适用于所有类型的 BizTalk 用户，包括架构师、 开发人员和管理员。</span><span class="sxs-lookup"><span data-stu-id="69839-111">It applies to all types of BizTalk users, including architects, developers, and administrators.</span></span> <span data-ttu-id="69839-112">并非所有所述的方案可能是您的环境中并不在本白皮书中所述的某些情况下会出现。</span><span class="sxs-lookup"><span data-stu-id="69839-112">Not all scenarios described may occur in your environment and some scenarios not mentioned in this white paper can occur.</span></span>  
  
 <span data-ttu-id="69839-113">由于的性质和 BizTalk Server 的重要性，设置和最佳实践可能因环境中;其中包括网络设置、 体系结构设计、 版本、 消息流和资源。</span><span class="sxs-lookup"><span data-stu-id="69839-113">Due to the nature and importance of BizTalk Server, settings and best practices can vary by environment; including network settings, architecture design, versions, message flow, and resources.</span></span> <span data-ttu-id="69839-114">本白皮书讨论常见的安装程序，并建议值。</span><span class="sxs-lookup"><span data-stu-id="69839-114">This white paper discussed the common setup and recommended values.</span></span>  
  
 <span data-ttu-id="69839-115">若要查看该文档，请下载[BizTalk Server 中的主动性](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx)Word 文档。</span><span class="sxs-lookup"><span data-stu-id="69839-115">To review the document, please download the [Proactivity in BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) Word document.</span></span>