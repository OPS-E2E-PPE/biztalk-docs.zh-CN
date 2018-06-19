---
title: MSCIT： 从 BizTalk Server 2009 中心供应链迁移到 BizTalk Server 2013 R2 虚拟化中心 |Microsoft 文档
ms.custom: ''
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7366ffc2-d1f6-44df-b1f8-f07b99cf5d11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3cc49424ead924bdb98dd196f7792806d2702f
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22299005"
---
# <a name="mscit-supply-chain-migration-from-biztalk-server-2009-hub-to-biztalk-server-2013-r2-virtualized-hub"></a><span data-ttu-id="00c34-102">从 BizTalk Server 2009 中心的 MSCIT： 供应链迁移到 BizTalk Server 2013 R2 虚拟化中心</span><span class="sxs-lookup"><span data-stu-id="00c34-102">MSCIT: Supply Chain migration from BizTalk Server 2009 hub to BizTalk Server 2013 R2 virtualized hub</span></span>
<span data-ttu-id="00c34-103">从 BizTalk Server 2010 到 BizTalk Server 2013 R2 应用程序迁移。</span><span class="sxs-lookup"><span data-stu-id="00c34-103">Application migration from BizTalk Server 2010 to BizTalk Server 2013 R2.</span></span>  
  
 <span data-ttu-id="00c34-104">**作者**: Arvind Chaudhary、 Microsoft &#124; Piyush Prasad、 Microsoft</span><span class="sxs-lookup"><span data-stu-id="00c34-104">**Author**: Arvind Chaudhary, Microsoft &#124; Piyush Prasad, Microsoft</span></span>  
  
 <span data-ttu-id="00c34-105">**发布**: 2015 年 9 月</span><span class="sxs-lookup"><span data-stu-id="00c34-105">**Published**: September 2015</span></span>  
  
 <span data-ttu-id="00c34-106">**适用于**: BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="00c34-106">**Applies to**: BizTalk Server 2013 R2</span></span>  
  
 <span data-ttu-id="00c34-107">**摘要**： 介绍原因以及 Microsoft IT 应用程序从 BizTalk Server 2009 和 2010年迁移到 BizTalk Server 2013 R2 所用的迁移过程。</span><span class="sxs-lookup"><span data-stu-id="00c34-107">**Summary**:  Describes the reasons and the  migration process taken by Microsoft IT to migrate applications from BizTalk Server 2009 and 2010 to BizTalk Server 2013 R2.</span></span> <span data-ttu-id="00c34-108">MSIT 标识消息流，转换在 Visual Studio 中的 BizTalk 项目，移动贸易合作伙伴管理方和协议，并更新应用程序绑定。</span><span class="sxs-lookup"><span data-stu-id="00c34-108">MSIT identified message streams, converted the BizTalk projects in Visual Studio, moved trading partner management parties and agreements, and updated the application bindings.</span></span>  
  
 <span data-ttu-id="00c34-109">您还可以阅读有关 MSIT 所面临的挑战和使用的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="00c34-109">You can also read about the challenges MSIT faced and the best practices used.</span></span>  
  
 <span data-ttu-id="00c34-110">下载[MSIT 迁移情景从 BizTalk Server 2009/2010年到 BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx)白皮书。</span><span class="sxs-lookup"><span data-stu-id="00c34-110">Download the [MSIT Migration story from BizTalk Server 2009/2010 to BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx) whitepaper.</span></span>