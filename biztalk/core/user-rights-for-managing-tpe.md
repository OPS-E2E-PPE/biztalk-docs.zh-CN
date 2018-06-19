---
title: 用于管理键入的用户权限 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3319a807b1357201dade0c53d04c26146c2b1e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286925"
---
# <a name="user-rights-for-managing-tpe"></a><span data-ttu-id="fef1a-102">管理 TPE 的用户权限</span><span class="sxs-lookup"><span data-stu-id="fef1a-102">User Rights for Managing TPE</span></span>
<span data-ttu-id="fef1a-103">解决方案开发人员、 系统管理员或 IT 操作人员必须有管理员权限才能检索或将跟踪配置文件部署到与程序集关联的数据库。</span><span class="sxs-lookup"><span data-stu-id="fef1a-103">Solution developers, system administrators, or IT/Operations personnel must have administrative rights to retrieve or deploy the tracking profile into a database associated with an assembly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fef1a-104">不能定义用户角色或授予或拒绝使用跟踪配置文件编辑器 （键入） 的用户权限。</span><span class="sxs-lookup"><span data-stu-id="fef1a-104">You cannot define user roles or grant or deny user permissions using Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="fef1a-105">仅可以在 Microsoft SQL Server 中定义这些用户角色和关联的权限。</span><span class="sxs-lookup"><span data-stu-id="fef1a-105">You can only define these user roles and associated permissions in Microsoft SQL Server.</span></span>  
  
 <span data-ttu-id="fef1a-106">通过键入，管理员可以：</span><span class="sxs-lookup"><span data-stu-id="fef1a-106">With TPE, administrators can:</span></span>  
  
-   <span data-ttu-id="fef1a-107">检索与从 BizTalk 管理数据库的一个或多个程序集关联的活动的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fef1a-107">Retrieve an active tracking profile associated with one or more assemblies from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="fef1a-108">修改跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fef1a-108">Modify the tracking profile</span></span>  
  
-   <span data-ttu-id="fef1a-109">将新的或已修改的跟踪配置文件应用到 BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="fef1a-109">Apply a new or modified tracking profile into the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="fef1a-110">修改保存跟踪配置文件 (.btt)</span><span class="sxs-lookup"><span data-stu-id="fef1a-110">Modify saved tracking profile files (.btt)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fef1a-111">跟踪配置文件文件不是上一个配置文件的内容的最终颁发机构。</span><span class="sxs-lookup"><span data-stu-id="fef1a-111">Tracking profile files are not the final authority on the contents of a profile.</span></span> <span data-ttu-id="fef1a-112">键入可以保存到文件，一个配置文件，尽管它主要从提取并将配置文件内容发布到 BizTalk Server 和 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="fef1a-112">TPE can save a profile to a file, although it primarily pulls from and publishes the profile contents to the BizTalk Server and BAM databases.</span></span> <span data-ttu-id="fef1a-113">跟踪配置文件仍可用来编辑或更新存储配置文件，只要该文件的内容匹配数据库中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="fef1a-113">Tracking profile files can still be used to edit or update the stored profile as long as the file contents match the information stored in the databases.</span></span> <span data-ttu-id="fef1a-114">另外，跟踪配置文件可以打包到 BizTalk Server 应用程序包中。</span><span class="sxs-lookup"><span data-stu-id="fef1a-114">In addition, tracking profile files can be packaged within a BizTalk Server application package.</span></span> <span data-ttu-id="fef1a-115">在 MSI 包被导入给定 BizTalk Server 安装时，包含跟踪配置文件的应用程序包可自动调用 BTTDeploy.exe 以应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="fef1a-115">Application packages that include tracking profile files automatically invoke BTTDeploy.exe to apply the tracking profile when the MSI package is imported to a given BizTalk Server installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fef1a-116">在键入流中，假定开发和部署任务被隔离，因为通常是这种情况，负责部署应具有到.btt 文件和关联的程序集文件的只读访问权限的人员。</span><span class="sxs-lookup"><span data-stu-id="fef1a-116">In the TPE workflow, assuming the development and deployment tasks are separated, as is typically the case, the person responsible for deployment should have read-only access to the .btt file and the associated assembly file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef1a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef1a-117">See Also</span></span>  
 <span data-ttu-id="fef1a-118">[BAM 工作流](../core/bam-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="fef1a-118">[BAM Workflow](../core/bam-workflow.md) </span></span>  
 [<span data-ttu-id="fef1a-119">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="fef1a-119">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)