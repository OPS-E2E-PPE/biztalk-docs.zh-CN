---
title: 在部署过程中的文件项目的状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4f9abe5de90996d883a0c104985e30782a40188
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392923"
---
# <a name="status-of-file-artifacts-during-deployment"></a><span data-ttu-id="d1b0e-102">在部署过程中的文件项目的状态</span><span class="sxs-lookup"><span data-stu-id="d1b0e-102">Status of File Artifacts During Deployment</span></span>
<span data-ttu-id="d1b0e-103">您可能需要知道当预处理或后处理脚本执行时，文件系统上存在哪些基于文件的项目。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-103">You may need to know what file-based artifacts exist on the file system when a pre- or post-processing script executes.</span></span> <span data-ttu-id="d1b0e-104">例如，你可能想后处理脚本在卸载期间运行，并从文件系统中删除某个项目文件。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-104">For example, you might want a post-processing script to run during uninstallation and delete a certain artifact file from the file system.</span></span> <span data-ttu-id="d1b0e-105">基于文件的项目是可以作为本地文件系统中，除了 BizTalk 数据库中的表示形式上的文件存在的项目。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-105">File-based artifacts are artifacts that can exist as files on the local file system, in addition to their representation in the BizTalk databases.</span></span> <span data-ttu-id="d1b0e-106">基于文件的项目的示例包括 COM 组件、.NET 程序集、 BizTalk 程序集、 BAM 项目、 特别文件、 脚本和绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-106">Examples of file-based artifacts are COM components, .NET assemblies, BizTalk assemblies, BAM artifacts, ad hoc files, scripts, and binding files.</span></span>  
  
 <span data-ttu-id="d1b0e-107">下表总结了在部署过程中每个点的项目文件的状态。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-107">The following table summarizes the status of the artifact files at each point in the deployment process.</span></span>  
  
|<span data-ttu-id="d1b0e-108">在部署过程中点</span><span class="sxs-lookup"><span data-stu-id="d1b0e-108">Point in the Deployment Process</span></span>|<span data-ttu-id="d1b0e-109">应用程序项目文件的状态</span><span class="sxs-lookup"><span data-stu-id="d1b0e-109">Status of Application Artifact Files</span></span>|  
|-------------------------------------|------------------------------------------|  
|<span data-ttu-id="d1b0e-110">预安装</span><span class="sxs-lookup"><span data-stu-id="d1b0e-110">Pre-installation</span></span>|<span data-ttu-id="d1b0e-111">只有 System.BizTalk.File 类型的文件存在于本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-111">Only files of the type System.BizTalk.File exist on the local file system.\*</span></span>|  
|<span data-ttu-id="d1b0e-112">安装后</span><span class="sxs-lookup"><span data-stu-id="d1b0e-112">Post-installation</span></span>|<span data-ttu-id="d1b0e-113">所有文件都存在于本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-113">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="d1b0e-114">卸载前</span><span class="sxs-lookup"><span data-stu-id="d1b0e-114">Pre-uninstallation</span></span>|<span data-ttu-id="d1b0e-115">所有文件都存在于本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-115">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="d1b0e-116">后卸载</span><span class="sxs-lookup"><span data-stu-id="d1b0e-116">Post-uninstallation</span></span>|<span data-ttu-id="d1b0e-117">尚未从本地文件系统中删除所有的文件。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-117">All files have been deleted from the local file system.</span></span>|  
|<span data-ttu-id="d1b0e-118">预导入</span><span class="sxs-lookup"><span data-stu-id="d1b0e-118">Pre-import</span></span>|<span data-ttu-id="d1b0e-119">除非已在本地计算机上安装应用程序，没有文件存在于本地文件系统上。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-119">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
|<span data-ttu-id="d1b0e-120">导入</span><span class="sxs-lookup"><span data-stu-id="d1b0e-120">Post-import</span></span>|<span data-ttu-id="d1b0e-121">除非已在本地计算机上安装应用程序，没有文件存在于本地文件系统上。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-121">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
  
 <span data-ttu-id="d1b0e-122">\* 本地文件系统上的文件存在，仅当文件添加到应用程序时指定了有效的目标位置。</span><span class="sxs-lookup"><span data-stu-id="d1b0e-122">\* Files exist on the local file system only if a valid destination location was specified when the file was added to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b0e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1b0e-123">See Also</span></span>  
 [<span data-ttu-id="d1b0e-124">使用预处理脚本和后期处理脚本自定义应用程序部署</span><span class="sxs-lookup"><span data-stu-id="d1b0e-124">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)