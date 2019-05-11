---
title: 如何列出所有引用的数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40677d08d41bfd913427aa18e8f63aef1b6ebaee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384824"
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="49537-102">如何列出所有引用的数据库</span><span class="sxs-lookup"><span data-stu-id="49537-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="49537-103">管理员使用**get 引用**命令以列出所有已被授予对本地 BAM 主导入数据库的引用其他 BizTalk 服务器上的 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="49537-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="49537-104">若要列出所有引用的数据库</span><span class="sxs-lookup"><span data-stu-id="49537-104">To list all referenced databases</span></span>  
  
1. <span data-ttu-id="49537-105">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49537-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="49537-106">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="49537-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="49537-107">在命令行提示符下键入以下内容： **bm.exe get 引用**。</span><span class="sxs-lookup"><span data-stu-id="49537-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="49537-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="49537-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49537-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="49537-109">See Also</span></span>  
 [<span data-ttu-id="49537-110">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="49537-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)