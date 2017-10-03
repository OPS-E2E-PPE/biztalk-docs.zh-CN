---
title: "如何显示管理包的替代 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-overrides-for-a-management-pack"></a><span data-ttu-id="57526-102">如何显示管理包的替代</span><span class="sxs-lookup"><span data-stu-id="57526-102">How to Display Overrides for a Management Pack</span></span>
<span data-ttu-id="57526-103">若要显示管理包的替代，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="57526-103">To display overrides for a management pack, use the following procedure.</span></span>  
  
### <a name="to-display-overrides-for-a-management-pack"></a><span data-ttu-id="57526-104">显示管理包的替代</span><span class="sxs-lookup"><span data-stu-id="57526-104">To display overrides for a management pack</span></span>  
  
1.  <span data-ttu-id="57526-105">在管理服务器中，单击**程序**，然后单击**System Center**。</span><span class="sxs-lookup"><span data-stu-id="57526-105">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="57526-106">单击**命令行界面**。</span><span class="sxs-lookup"><span data-stu-id="57526-106">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="57526-107">在命令外壳中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="57526-107">In the Command Shell, type the following command:</span></span>   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  <span data-ttu-id="57526-108">创建一个.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="57526-108">A .csv file is created.</span></span> <span data-ttu-id="57526-109">该.csv 文件可以在 Office Excel 中打开。</span><span class="sxs-lookup"><span data-stu-id="57526-109">The .csv file can be opened in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57526-110">在 Office Excel 中，你可能需要将指定的.csv 文件是一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="57526-110">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
 <span data-ttu-id="57526-111">例如，下面的命令显示某一核心管理包的替代：</span><span class="sxs-lookup"><span data-stu-id="57526-111">For example, the following command displays the overrides for one of the core management packs:</span></span>   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`