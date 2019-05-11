---
title: 如何使用 BAM 管理实用程序的 BAM 数据库设置 |Microsoft Docs
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
ms.openlocfilehash: d01b84fb3e538ee81351cbcfe380d893c5f0cc7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334098"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="91323-102">如何设置 BAM 数据库使用 BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="91323-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="91323-103">管理员通常使用 BizTalk Server 配置实用工具来设置 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="91323-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="91323-104">可以使用 BAM 管理实用程序 (bm.exe) 作为替代方法，若要设置数据库。</span><span class="sxs-lookup"><span data-stu-id="91323-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91323-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="91323-105">Prerequisites</span></span>  
 <span data-ttu-id="91323-106">在本主题中执行该过程的先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="91323-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="91323-107">您必须对 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的宿主 SQL 服务器上具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="91323-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="91323-108">若要设置 SQL Notification Services 数据库，您必须具有管理员权限并且是本地管理员组的成员，以及是已配置，如 BTS Admins 组的任何其他管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="91323-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="91323-109">必须具有包含用于设置数据库的 XML 数据的 BAM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="91323-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="91323-110">若要设置使用 BAM 管理实用程序的 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="91323-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="91323-111">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91323-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="91323-112">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="91323-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="91323-113">在命令行提示符下键入以下内容： **bm 设置数据库-ConfigFile:\<配置文件\>**，其中\<*配置文件*\>替换为您的 BAM 配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="91323-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="91323-114">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="91323-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91323-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="91323-115">See Also</span></span>  
 [<span data-ttu-id="91323-116">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="91323-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)