---
title: 如何部署 BAM 定义 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58d2711ee5bdf9e280ad32610031d5720d8d2c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385276"
---
# <a name="how-to-deploy-bam-definitions"></a><span data-ttu-id="7615d-102">如何部署 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="7615d-102">How to Deploy BAM Definitions</span></span>
<span data-ttu-id="7615d-103">管理员使用**部署所有**从工作簿导出 BAM 管理实用程序命令以部署 BAM 定义从 Excel 工作簿或 XML 定义文件。</span><span class="sxs-lookup"><span data-stu-id="7615d-103">Administrators use the **deploy-all** BAM Management utility command to deploy a BAM definition from the Excel workbook or the XML definitions file exported from the workbook.</span></span> <span data-ttu-id="7615d-104">当你执行的完整安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，配置向导将自动配置 BAM 配置 XML。</span><span class="sxs-lookup"><span data-stu-id="7615d-104">When you perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the Configuration Wizard automatically configures the BAM Configuration XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7615d-105">如果多个用户正在用于 Excel 的 BAM 外接程序，我们建议，它们具有相同版本的 Microsoft 数据访问组件 (MDAC)。</span><span class="sxs-lookup"><span data-stu-id="7615d-105">If multiple users are working with the BAM Add-In for Excel, we recommend that they have the same version of Microsoft Data Access Components (MDAC).</span></span> <span data-ttu-id="7615d-106">否则，可能会出现兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="7615d-106">Otherwise, compatibility issues may arise.</span></span> <span data-ttu-id="7615d-107">具体而言，如果使用较新版本的 MDAC 的计算机上创建一个模板，然后尝试使用旧版本的 MDAC 的计算机上打开它，将发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="7615d-107">Specifically, if you create a template on a computer with a newer version of MDAC and then attempt to open it on a computer with an older version of MDAC, a compiler error will occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7615d-108">可以使用每个数据维度 （例如，位置） 的仅一个数据项 （例如，城市）。</span><span class="sxs-lookup"><span data-stu-id="7615d-108">You can use only one data item (for example, City) per data dimension (for example, Location).</span></span> <span data-ttu-id="7615d-109">不能在另一个数据维度，例如，地区中再次使用城市。</span><span class="sxs-lookup"><span data-stu-id="7615d-109">You cannot use City again in another data dimension, such as Region.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7615d-110">我们建议在部署它们之前验证 BAM Excel 工作簿 (.xls) 的安全性。</span><span class="sxs-lookup"><span data-stu-id="7615d-110">We recommend that you verify the security of BAM Excel workbooks (.xls) before you deploy them.</span></span> <span data-ttu-id="7615d-111">在管理计算机上使用 Excel 来验证 BAM Excel 工作簿的安全性。</span><span class="sxs-lookup"><span data-stu-id="7615d-111">You use Excel on the administration computer to verify the security of BAM Excel workbooks.</span></span> <span data-ttu-id="7615d-112">在部署某一工作簿之前，将其打开，并确保宏安全性设置为高，不会出现任何警告。</span><span class="sxs-lookup"><span data-stu-id="7615d-112">Before you deploy a workbook, open it and ensure the macro security is set to high, and that there are no warnings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7615d-113">在 BAM 数据库中，"BAM_\<...\>"命名约定保留的所有 SQL 实体 (表、 索引、 存储的过程、 角色等。...)。*不这样做*使用此命名约定创建任何 SQL 实体; 此类使用可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="7615d-113">In BAM databases, the “BAM_\<...\>” naming convention is reserved for all SQL entities (tables, indexes, stored procedures, roles, etc...). *Do not* use this naming convention to create any SQL entities; such a usage might result in an undefined behavior.</span></span>  
  
 <span data-ttu-id="7615d-114">部署 BAM 定义 XML 文件之前，必须确保用于创建此文件的区域设置与要在其部署它的计算机的区域设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="7615d-114">Before you can deploy a BAM definition XML file, you must ensure that the locale used to create this file matches the locale of the computer on which you are deploying it.</span></span> <span data-ttu-id="7615d-115">例如，如果您创建运行 Microsoft Windows 的日语版本的计算机上的文件，在部署该文件的计算机必须设置为日文区域设置。</span><span class="sxs-lookup"><span data-stu-id="7615d-115">For example, if you create the file on a computer running a Japanese version of Microsoft Windows, the computer you deploy the file on must be set to the Japanese locale.</span></span> <span data-ttu-id="7615d-116">如果该文件和计算机设置不匹配，必须切换用于运行 BAM 管理实用程序到正确的区域设置的计算机和您必须重新启动它之前运行此实用程序。</span><span class="sxs-lookup"><span data-stu-id="7615d-116">If the file and the computer settings do not match, you must switch the computer you use to run the BAM Management utility to the correct locale and you must restart it before running the utility.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7615d-117">BAM 定义 XML 文件不能包含多个语言的文本，除非所有语言都使用同一代码页，或只有两种语言都包括在内并且其中一种是英语。</span><span class="sxs-lookup"><span data-stu-id="7615d-117">The BAM definition XML file cannot contain text in multiple languages unless the languages all use the same codepage, or only two languages are included and one of them is English.</span></span>  
  
 <span data-ttu-id="7615d-118">有关更改您的计算机上的区域设置的信息，请参阅您的操作系统的帮助。</span><span class="sxs-lookup"><span data-stu-id="7615d-118">For information about changing locale settings on your computer, see the Help for your operating system.</span></span>  
  
### <a name="to-deploy-a-bam-definition"></a><span data-ttu-id="7615d-119">若要部署的 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="7615d-119">To deploy a BAM definition</span></span>  
  
1.  <span data-ttu-id="7615d-120">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7615d-120">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7615d-121">通过键入导航到跟踪文件夹**C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking**在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="7615d-121">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking** at the command prompt.</span></span> <span data-ttu-id="7615d-122">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="7615d-122">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="7615d-123">类型**bm 部署全部-DefinitionFile:\<BAM 定义文件\>**。</span><span class="sxs-lookup"><span data-stu-id="7615d-123">Type **bm deploy-all -DefinitionFile:\<BAM definition file\>**.</span></span>  
  
4.  <span data-ttu-id="7615d-124">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="7615d-124">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7615d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7615d-125">See Also</span></span>  
 <span data-ttu-id="7615d-126">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="7615d-126">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="7615d-127">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7615d-127">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="7615d-128">BAM 安全建议</span><span class="sxs-lookup"><span data-stu-id="7615d-128">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)