---
title: "在部署过程中的文件项目的状态 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="status-of-file-artifacts-during-deployment"></a><span data-ttu-id="9b810-102">在部署过程中的文件项目的状态</span><span class="sxs-lookup"><span data-stu-id="9b810-102">Status of File Artifacts During Deployment</span></span>
<span data-ttu-id="9b810-103">您可能需要知道，在执行预处理和后处理脚本时，文件系统上存在哪些基于文件的项目。</span><span class="sxs-lookup"><span data-stu-id="9b810-103">You may need to know what file-based artifacts exist on the file system when a pre- or post-processing script executes.</span></span> <span data-ttu-id="9b810-104">例如，您可能需要后处理脚本在卸载期间运行，并从文件系统中删除某个项目文件。</span><span class="sxs-lookup"><span data-stu-id="9b810-104">For example, you might want a post-processing script to run during uninstallation and delete a certain artifact file from the file system.</span></span> <span data-ttu-id="9b810-105">基于文件的项目是除了 BizTalk 数据库中的表示形式，还可以作为本地文件系统上的文件存在的项目。</span><span class="sxs-lookup"><span data-stu-id="9b810-105">File-based artifacts are artifacts that can exist as files on the local file system, in addition to their representation in the BizTalk databases.</span></span> <span data-ttu-id="9b810-106">基于文件的项目的示例包括：COM 组件、.NET 程序集、BizTalk 程序集、BAM 项目、特别文件、脚本和绑定文件。</span><span class="sxs-lookup"><span data-stu-id="9b810-106">Examples of file-based artifacts are COM components, .NET assemblies, BizTalk assemblies, BAM artifacts, ad hoc files, scripts, and binding files.</span></span>  
  
 <span data-ttu-id="9b810-107">下表概括了部署过程中的每个点的项目文件的状态。</span><span class="sxs-lookup"><span data-stu-id="9b810-107">The following table summarizes the status of the artifact files at each point in the deployment process.</span></span>  
  
|<span data-ttu-id="9b810-108">部署过程中的点</span><span class="sxs-lookup"><span data-stu-id="9b810-108">Point in the Deployment Process</span></span>|<span data-ttu-id="9b810-109">应用程序项目文件的状态</span><span class="sxs-lookup"><span data-stu-id="9b810-109">Status of Application Artifact Files</span></span>|  
|-------------------------------------|------------------------------------------|  
|<span data-ttu-id="9b810-110">安装前</span><span class="sxs-lookup"><span data-stu-id="9b810-110">Pre-installation</span></span>|<span data-ttu-id="9b810-111">只有 System.BizTalk.File 类型的文件在本地文件系统上存在。*</span><span class="sxs-lookup"><span data-stu-id="9b810-111">Only files of the type System.BizTalk.File exist on the local file system.*</span></span>|  
|<span data-ttu-id="9b810-112">安装后</span><span class="sxs-lookup"><span data-stu-id="9b810-112">Post-installation</span></span>|<span data-ttu-id="9b810-113">所有文件均在本地文件系统上存在。*</span><span class="sxs-lookup"><span data-stu-id="9b810-113">All files exist on the local file system.*</span></span>|  
|<span data-ttu-id="9b810-114">卸载前</span><span class="sxs-lookup"><span data-stu-id="9b810-114">Pre-uninstallation</span></span>|<span data-ttu-id="9b810-115">所有文件均在本地文件系统上存在。*</span><span class="sxs-lookup"><span data-stu-id="9b810-115">All files exist on the local file system.*</span></span>|  
|<span data-ttu-id="9b810-116">后卸载</span><span class="sxs-lookup"><span data-stu-id="9b810-116">Post-uninstallation</span></span>|<span data-ttu-id="9b810-117">所有文件已从本地文件系统中删除。</span><span class="sxs-lookup"><span data-stu-id="9b810-117">All files have been deleted from the local file system.</span></span>|  
|<span data-ttu-id="9b810-118">导入前</span><span class="sxs-lookup"><span data-stu-id="9b810-118">Pre-import</span></span>|<span data-ttu-id="9b810-119">直到在本地计算机上安装应用程序之后，本地文件系统上才存在文件。</span><span class="sxs-lookup"><span data-stu-id="9b810-119">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
|<span data-ttu-id="9b810-120">导入后</span><span class="sxs-lookup"><span data-stu-id="9b810-120">Post-import</span></span>|<span data-ttu-id="9b810-121">直到在本地计算机上安装应用程序之后，本地文件系统上才存在文件。</span><span class="sxs-lookup"><span data-stu-id="9b810-121">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
  
 <span data-ttu-id="9b810-122">\*仅当该文件添加到应用程序时指定了有效的目标位置，本地文件系统上存在文件。</span><span class="sxs-lookup"><span data-stu-id="9b810-122">\* Files exist on the local file system only if a valid destination location was specified when the file was added to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b810-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b810-123">See Also</span></span>  
 [<span data-ttu-id="9b810-124">前期和后期处理脚本用于自定义应用程序部署</span><span class="sxs-lookup"><span data-stu-id="9b810-124">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)