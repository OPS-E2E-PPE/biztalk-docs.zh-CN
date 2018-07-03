---
title: 如何更新 BAM 配置使用 BAM 管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 952c163e809ceff8f084e661b542752d30f18096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019908"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="2b3d4-102">如何使用 BAM 管理实用程序更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="2b3d4-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="2b3d4-103">管理员可以使用 BAM 管理实用程序更新安装的现有 BAM。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b3d4-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="2b3d4-104">Prerequisites</span></span>  
 <span data-ttu-id="2b3d4-105">您必须具有要更新的 BAM 数据库的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="2b3d4-106">使用 BAM 管理实用程序更新 BAM 配置</span><span class="sxs-lookup"><span data-stu-id="2b3d4-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="2b3d4-107">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="2b3d4-108">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="2b3d4-109">在命令行提示符下键入以下内容： **bm 更新-config-FileName:\<配置文件\>**，其中\<*配置文件*\>是替换为您的 BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="2b3d4-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="2b3d4-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3d4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b3d4-111">See Also</span></span>  
 [<span data-ttu-id="2b3d4-112">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="2b3d4-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)