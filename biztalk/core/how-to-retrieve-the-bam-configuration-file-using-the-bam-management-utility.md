---
title: 如何检索 BAM 配置文件使用 BAM 管理实用程序 |Microsoft Docs
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
ms.openlocfilehash: 4277e6b088ed136021b898e26204a63dc782a895
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008510"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="3e5d5-102">如何检索 BAM 配置文件使用 BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="3e5d5-102">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>
<span data-ttu-id="3e5d5-103">管理员和开发人员可以使用 BAM 管理实用程序来检索 BAM 基础结构的当前配置。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-103">Administrators and developers can use the BAM Management utility to retrieve the current configuration of the BAM infrastructure.</span></span> <span data-ttu-id="3e5d5-104">检索的配置可以用来将 BAM 安装迁移到新的服务器，也可以对该配置进行修改并用于更新现有的 BAM 安装。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-104">The retrieved configuration can be used to migrate a BAM installation to a new server or it can be modified and used to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e5d5-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="3e5d5-105">Prerequisites</span></span>  
 <span data-ttu-id="3e5d5-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="3e5d5-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="3e5d5-107">已配置的 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="3e5d5-107">Configured BAM databases</span></span>  
  
-   <span data-ttu-id="3e5d5-108">读取 BAM 主导入数据库的权限</span><span class="sxs-lookup"><span data-stu-id="3e5d5-108">Permissions to read the BAM Primary Import database</span></span>  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="3e5d5-109">使用 BAM 管理实用程序检索 BAM 配置文件</span><span class="sxs-lookup"><span data-stu-id="3e5d5-109">To retrieve the BAM configuration file using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="3e5d5-110">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-110">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="3e5d5-111">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-111">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="3e5d5-112">在命令行提示符下键入以下内容： **bm 获取配置-FileName:\<输出文件\>**，其中\<*输出文件*\>将替换为BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-112">Type the following at the command line prompt: **bm get-config -FileName:\<output file\>**, where \<*output file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="3e5d5-113">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="3e5d5-113">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5d5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e5d5-114">See Also</span></span>  
 [<span data-ttu-id="3e5d5-115">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="3e5d5-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)