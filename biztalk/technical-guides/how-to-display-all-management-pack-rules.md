---
title: 如何显示所有管理包规则 |Microsoft 文档
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
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298213"
---
# <a name="how-to-display-all-management-pack-rules"></a><span data-ttu-id="e6e2c-102">如何显示所有管理包规则</span><span class="sxs-lookup"><span data-stu-id="e6e2c-102">How to Display All Management Pack Rules</span></span>
<span data-ttu-id="e6e2c-103">使用以下过程显示你导入的管理包的规则的列表。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-103">Use the following procedure to display a list of rules for the management packs that you imported.</span></span> <span data-ttu-id="e6e2c-104">可以在 Office Excel 中查看的规则的列表。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-104">The list of rules can be viewed in Office Excel.</span></span>  
  
### <a name="to-display-management-pack-rules"></a><span data-ttu-id="e6e2c-105">若要显示管理包规则</span><span class="sxs-lookup"><span data-stu-id="e6e2c-105">To display management pack rules</span></span>  
  
1.  <span data-ttu-id="e6e2c-106">在管理服务器中，单击**程序**，然后单击**System Center**。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-106">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="e6e2c-107">单击**命令行界面**。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-107">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="e6e2c-108">在命令外壳中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e6e2c-108">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  <span data-ttu-id="e6e2c-109">创建一个.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-109">A .csv file is created.</span></span> <span data-ttu-id="e6e2c-110">你可以在 Office Excel 中打开该.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-110">You can open the .csv file in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6e2c-111">在 Office Excel 中，你可能需要将指定的.csv 文件是一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="e6e2c-111">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>