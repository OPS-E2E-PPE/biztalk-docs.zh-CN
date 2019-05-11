---
title: MSCIT:提供从 BizTalk Server 2009 中心到 BizTalk Server 2013 R2 虚拟化中心的链迁移 |Microsoft Docs
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
ms.openlocfilehash: 8973c25923ede8b1dbaa060843129f931d300c3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395818"
---
# <a name="mscit-supply-chain-migration-from-biztalk-server-2009-hub-to-biztalk-server-2013-r2-virtualized-hub"></a><span data-ttu-id="13eb5-102">MSCIT:提供从 BizTalk Server 2009 中心的链迁移到 BizTalk Server 2013 R2 虚拟化中心</span><span class="sxs-lookup"><span data-stu-id="13eb5-102">MSCIT: Supply Chain migration from BizTalk Server 2009 hub to BizTalk Server 2013 R2 virtualized hub</span></span>
<span data-ttu-id="13eb5-103">应用程序迁移为 BizTalk Server 2010 到 BizTalk Server 2013 R2。</span><span class="sxs-lookup"><span data-stu-id="13eb5-103">Application migration from BizTalk Server 2010 to BizTalk Server 2013 R2.</span></span>  
  
 <span data-ttu-id="13eb5-104">**作者**:Arvind Chaudhary, Microsoft &#124; Piyush Prasad, Microsoft</span><span class="sxs-lookup"><span data-stu-id="13eb5-104">**Author**: Arvind Chaudhary, Microsoft &#124; Piyush Prasad, Microsoft</span></span>  
  
 <span data-ttu-id="13eb5-105">**发布**:2015 年 9 月</span><span class="sxs-lookup"><span data-stu-id="13eb5-105">**Published**: September 2015</span></span>  
  
 <span data-ttu-id="13eb5-106">**适用对象**：BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="13eb5-106">**Applies to**: BizTalk Server 2013 R2</span></span>  
  
 <span data-ttu-id="13eb5-107">**摘要**:描述和迁移过程将从 BizTalk Server 2009 和 2010年的应用程序迁移到 BizTalk Server 2013 R2 Microsoft IT 所用的原因。</span><span class="sxs-lookup"><span data-stu-id="13eb5-107">**Summary**:  Describes the reasons and the  migration process taken by Microsoft IT to migrate applications from BizTalk Server 2009 and 2010 to BizTalk Server 2013 R2.</span></span> <span data-ttu-id="13eb5-108">MSIT 标识消息流、 转换的 BizTalk 项目在 Visual Studio 中，移动贸易合作伙伴管理参与方和协议，并更新应用程序绑定。</span><span class="sxs-lookup"><span data-stu-id="13eb5-108">MSIT identified message streams, converted the BizTalk projects in Visual Studio, moved trading partner management parties and agreements, and updated the application bindings.</span></span>  
  
 <span data-ttu-id="13eb5-109">您还可以阅读有关 MSIT 所面临的难题和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="13eb5-109">You can also read about the challenges MSIT faced and the best practices used.</span></span>  
  
 <span data-ttu-id="13eb5-110">下载[MSIT 迁移情景从 BizTalk Server 2009/2010年到 BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx)白皮书。</span><span class="sxs-lookup"><span data-stu-id="13eb5-110">Download the [MSIT Migration story from BizTalk Server 2009/2010 to BizTalk Server 2013 R2](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/MSIT-Whitepaper%20Migration%20Story%20BizTalk%202013%20R2.docx) whitepaper.</span></span>