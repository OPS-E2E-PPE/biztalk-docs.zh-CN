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
ms.openlocfilehash: 6f497fa345dd643429dac7c48d43e04646fd81f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333700"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="82803-102">如何更新 BAM 配置使用 BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="82803-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="82803-103">管理员可以使用 BAM 管理实用程序来更新现有 BAM 安装。</span><span class="sxs-lookup"><span data-stu-id="82803-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82803-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="82803-104">Prerequisites</span></span>  
 <span data-ttu-id="82803-105">正在更新对 BAM 数据库，必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="82803-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="82803-106">若要更新 BAM 配置使用 BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="82803-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="82803-107">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="82803-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="82803-108">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="82803-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="82803-109">在命令行提示符下键入以下内容： **bm 更新-config-FileName:\<配置文件\>**，其中\<*配置文件*\>是替换为您的 BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="82803-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="82803-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="82803-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82803-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="82803-111">See Also</span></span>  
 [<span data-ttu-id="82803-112">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="82803-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)