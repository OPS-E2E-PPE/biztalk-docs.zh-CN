---
title: 如何列出所有引用数据库 |Microsoft 文档
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
ms.openlocfilehash: 69c6411378311892f85821a3e86d65a85f909d0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253765"
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="19e05-102">如何列出所有引用数据库</span><span class="sxs-lookup"><span data-stu-id="19e05-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="19e05-103">管理员使用**get 引用**命令来列出所有已被授予对本地 BAM 主导入数据库的引用其他 BizTalk 服务器上的 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="19e05-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="19e05-104">列出所有引用的数据库</span><span class="sxs-lookup"><span data-stu-id="19e05-104">To list all referenced databases</span></span>  
  
1.  <span data-ttu-id="19e05-105">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="19e05-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="19e05-106">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="19e05-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="19e05-107">在命令行提示符下键入以下内容： **bm.exe get 引用**。</span><span class="sxs-lookup"><span data-stu-id="19e05-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="19e05-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="19e05-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e05-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19e05-109">See Also</span></span>  
 [<span data-ttu-id="19e05-110">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="19e05-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)