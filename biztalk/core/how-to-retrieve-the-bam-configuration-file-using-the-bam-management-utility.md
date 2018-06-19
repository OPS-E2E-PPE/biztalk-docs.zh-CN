---
title: 如何检索使用 BAM 管理实用工具对 BAM 配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef0f4802aa44a042f39adbdc9f169b11a16796d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972275"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="ad61c-102">如何检索 BAM 配置文件使用 BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="ad61c-102">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>
<span data-ttu-id="ad61c-103">管理员和开发人员可以使用 BAM 管理实用程序来检索 BAM 基础结构的当前配置。</span><span class="sxs-lookup"><span data-stu-id="ad61c-103">Administrators and developers can use the BAM Management utility to retrieve the current configuration of the BAM infrastructure.</span></span> <span data-ttu-id="ad61c-104">检索的配置可以用来将 BAM 安装迁移到新的服务器，也可以对该配置进行修改并用于更新现有的 BAM 安装。</span><span class="sxs-lookup"><span data-stu-id="ad61c-104">The retrieved configuration can be used to migrate a BAM installation to a new server or it can be modified and used to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ad61c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="ad61c-105">Prerequisites</span></span>  
 <span data-ttu-id="ad61c-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="ad61c-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="ad61c-107">已配置的 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="ad61c-107">Configured BAM databases</span></span>  
  
-   <span data-ttu-id="ad61c-108">读取 BAM 主导入数据库的权限</span><span class="sxs-lookup"><span data-stu-id="ad61c-108">Permissions to read the BAM Primary Import database</span></span>  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="ad61c-109">使用 BAM 管理实用程序检索 BAM 配置文件</span><span class="sxs-lookup"><span data-stu-id="ad61c-109">To retrieve the BAM configuration file using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="ad61c-110">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ad61c-110">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ad61c-111">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="ad61c-111">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="ad61c-112">在命令行提示符下键入以下内容： **bm get-config FileName:\<输出文件\>**，其中\<*输出文件*\>替换为BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ad61c-112">Type the following at the command line prompt: **bm get-config -FileName:\<output file\>**, where \<*output file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="ad61c-113">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="ad61c-113">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad61c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad61c-114">See Also</span></span>  
 [<span data-ttu-id="ad61c-115">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="ad61c-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)