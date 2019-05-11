---
title: 管理 TPE 的用户权限 |Microsoft Docs
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
ms.openlocfilehash: 7d88532b21d2a57a2260761ae8b4194ddc0bf5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399920"
---
# <a name="user-rights-for-managing-tpe"></a><span data-ttu-id="64d23-102">管理 TPE 的用户权限</span><span class="sxs-lookup"><span data-stu-id="64d23-102">User Rights for Managing TPE</span></span>
<span data-ttu-id="64d23-103">解决方案开发人员、 系统管理员或 IT / 操作人员必须具有管理权限才能检索或将跟踪配置文件部署到与程序集关联的数据库。</span><span class="sxs-lookup"><span data-stu-id="64d23-103">Solution developers, system administrators, or IT/Operations personnel must have administrative rights to retrieve or deploy the tracking profile into a database associated with an assembly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64d23-104">不能定义用户角色或授予或拒绝使用跟踪配置文件编辑器 (TPE) 的用户权限。</span><span class="sxs-lookup"><span data-stu-id="64d23-104">You cannot define user roles or grant or deny user permissions using Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="64d23-105">仅可以在 Microsoft SQL Server 中定义这些用户角色和关联的权限。</span><span class="sxs-lookup"><span data-stu-id="64d23-105">You can only define these user roles and associated permissions in Microsoft SQL Server.</span></span>  
  
 <span data-ttu-id="64d23-106">使用 TPE，管理员可以：</span><span class="sxs-lookup"><span data-stu-id="64d23-106">With TPE, administrators can:</span></span>  
  
-   <span data-ttu-id="64d23-107">检索与从 BizTalk 管理数据库的一个或多个程序集关联的活动的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="64d23-107">Retrieve an active tracking profile associated with one or more assemblies from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="64d23-108">修改跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="64d23-108">Modify the tracking profile</span></span>  
  
-   <span data-ttu-id="64d23-109">将新的或修改跟踪配置文件应用到 BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="64d23-109">Apply a new or modified tracking profile into the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="64d23-110">修改保存跟踪配置文件 (.btt)</span><span class="sxs-lookup"><span data-stu-id="64d23-110">Modify saved tracking profile files (.btt)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64d23-111">跟踪配置文件不是配置文件的内容上的最后一个颁发机构。</span><span class="sxs-lookup"><span data-stu-id="64d23-111">Tracking profile files are not the final authority on the contents of a profile.</span></span> <span data-ttu-id="64d23-112">TPE 可以将一个配置文件保存到文件，尽管它主要从拉取并将配置文件内容发布到 BizTalk Server 和 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="64d23-112">TPE can save a profile to a file, although it primarily pulls from and publishes the profile contents to the BizTalk Server and BAM databases.</span></span> <span data-ttu-id="64d23-113">跟踪配置文件仍可以使用编辑或更新存储的配置文件，只要该文件的内容匹配的信息存储在数据库中的功能。</span><span class="sxs-lookup"><span data-stu-id="64d23-113">Tracking profile files can still be used to edit or update the stored profile as long as the file contents match the information stored in the databases.</span></span> <span data-ttu-id="64d23-114">此外，BizTalk Server 应用程序包中打包跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="64d23-114">In addition, tracking profile files can be packaged within a BizTalk Server application package.</span></span> <span data-ttu-id="64d23-115">包含自动跟踪配置文件的应用程序包调用 BTTDeploy.exe 以应用跟踪配置文件，MSI 包导入到给定的 BizTalk Server 安装时。</span><span class="sxs-lookup"><span data-stu-id="64d23-115">Application packages that include tracking profile files automatically invoke BTTDeploy.exe to apply the tracking profile when the MSI package is imported to a given BizTalk Server installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64d23-116">在 TPE 的工作流，假设开发和部署任务被分开的因为通常情况下，负责部署应具有到该.btt 文件和关联的程序集文件的只读访问权限的人员。</span><span class="sxs-lookup"><span data-stu-id="64d23-116">In the TPE workflow, assuming the development and deployment tasks are separated, as is typically the case, the person responsible for deployment should have read-only access to the .btt file and the associated assembly file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d23-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="64d23-117">See Also</span></span>  
 <span data-ttu-id="64d23-118">[BAM 工作流](../core/bam-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="64d23-118">[BAM Workflow](../core/bam-workflow.md) </span></span>  
 [<span data-ttu-id="64d23-119">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="64d23-119">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)