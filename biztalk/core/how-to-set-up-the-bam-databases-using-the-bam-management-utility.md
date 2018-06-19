---
title: 如何使用 BAM 管理实用工具的 BAM 数据库设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cee3564b90b730334d2d891edd2e9abc221a367
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971307"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="3ab17-102">如何使用 BAM 管理实用工具 BAM 数据库设置</span><span class="sxs-lookup"><span data-stu-id="3ab17-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="3ab17-103">通常，管理员使用 BizTalk Server 配置实用程序来设置 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="3ab17-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="3ab17-104">您可以使用 BAM 管理实用程序 (bm.exe) 作为设置数据库的备选方法。</span><span class="sxs-lookup"><span data-stu-id="3ab17-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3ab17-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3ab17-105">Prerequisites</span></span>  
 <span data-ttu-id="3ab17-106">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="3ab17-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="3ab17-107">必须对 BAMPrimaryImport、BAMStarSchema 和 BAMArchive 数据库的宿主 SQL Server 具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="3ab17-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="3ab17-108">若要设置 SQL Notification Services 数据库，必须具有管理员权限，并且是本地管理员组的成员，而且还必须是已配置的任何其他管理员组（如 BTS Admins 组）的成员。</span><span class="sxs-lookup"><span data-stu-id="3ab17-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="3ab17-109">必须具有配置数据库所用的、其中包含 XML 数据的 BAM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="3ab17-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="3ab17-110">使用 BAM 管理实用程序设置 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="3ab17-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="3ab17-111">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3ab17-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3ab17-112">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="3ab17-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="3ab17-113">在命令行提示符下键入以下内容： **bm 安装程序数据库 ConfigFile:\<配置文件\>**，其中\<*配置文件*\>替换为你 BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3ab17-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="3ab17-114">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="3ab17-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab17-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab17-115">See Also</span></span>  
 [<span data-ttu-id="3ab17-116">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="3ab17-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)