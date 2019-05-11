---
title: 如何显示管理包的监视器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d98cca640b7fa818ad49d3b9c95c3e3bdcbf5c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253477"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a><span data-ttu-id="a2a8c-102">如何显示管理包的监视器</span><span class="sxs-lookup"><span data-stu-id="a2a8c-102">How to Display Monitors for a Management Pack</span></span>
<span data-ttu-id="a2a8c-103">若要管理包的监视器和替代使用命令行界面中显示的输出列表，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="a2a8c-103">To display a list of outputs for a management pack's monitors and overrides using the Command Shell, use the following procedure.</span></span>  
  
### <a name="to-display-monitors-for-a-management-pack"></a><span data-ttu-id="a2a8c-104">若要显示管理包的监视器</span><span class="sxs-lookup"><span data-stu-id="a2a8c-104">To display monitors for a management pack</span></span>  
  
1. <span data-ttu-id="a2a8c-105">在管理服务器中，单击**程序**，然后单击**System Center。**</span><span class="sxs-lookup"><span data-stu-id="a2a8c-105">In your management server, click **Programs**, and then click **System Center.**</span></span>  
  
2. <span data-ttu-id="a2a8c-106">单击**命令行界面**。</span><span class="sxs-lookup"><span data-stu-id="a2a8c-106">Click **Command Shell**.</span></span>  
  
3. <span data-ttu-id="a2a8c-107">在命令外壳中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2a8c-107">In the Command Shell, type the following command:</span></span>   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. <span data-ttu-id="a2a8c-108">创建一个.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="a2a8c-108">A .csv file is created.</span></span> <span data-ttu-id="a2a8c-109">可以在 Microsoft Office Excel 中打开.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="a2a8c-109">The .csv file can be opened in Microsoft Office Excel.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="a2a8c-110">在 Excel 中，您可能需要指定的.csv 文件是一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="a2a8c-110">In Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
   <span data-ttu-id="a2a8c-111">例如，以下命令将检索数据与某一核心管理包关联的监视器：</span><span class="sxs-lookup"><span data-stu-id="a2a8c-111">For example, the following command retrieves data for the monitors associated with one of the core management packs:</span></span>   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`