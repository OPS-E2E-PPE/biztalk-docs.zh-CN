---
title: 如何显示所有管理包规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22102080d5852ab838ce8fa3ce1d421e9a42900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253500"
---
# <a name="how-to-display-all-management-pack-rules"></a><span data-ttu-id="86d36-102">如何显示所有管理包规则</span><span class="sxs-lookup"><span data-stu-id="86d36-102">How to Display All Management Pack Rules</span></span>
<span data-ttu-id="86d36-103">使用以下过程显示已导入的管理包的规则的列表。</span><span class="sxs-lookup"><span data-stu-id="86d36-103">Use the following procedure to display a list of rules for the management packs that you imported.</span></span> <span data-ttu-id="86d36-104">可以在 Office Excel 中查看规则的列表。</span><span class="sxs-lookup"><span data-stu-id="86d36-104">The list of rules can be viewed in Office Excel.</span></span>  
  
### <a name="to-display-management-pack-rules"></a><span data-ttu-id="86d36-105">若要显示管理包规则</span><span class="sxs-lookup"><span data-stu-id="86d36-105">To display management pack rules</span></span>  
  
1.  <span data-ttu-id="86d36-106">在管理服务器中，单击**程序**，然后单击**System Center**。</span><span class="sxs-lookup"><span data-stu-id="86d36-106">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="86d36-107">单击**命令行界面**。</span><span class="sxs-lookup"><span data-stu-id="86d36-107">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="86d36-108">在命令外壳中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="86d36-108">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  <span data-ttu-id="86d36-109">创建一个.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="86d36-109">A .csv file is created.</span></span> <span data-ttu-id="86d36-110">可以在 Office Excel 中打开.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="86d36-110">You can open the .csv file in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86d36-111">在 Office Excel 中，您可能需要指定的.csv 文件是一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="86d36-111">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>