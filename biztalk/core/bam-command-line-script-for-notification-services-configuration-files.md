---
title: "BAM 通知的命令行脚本服务配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b22607193ed7c345388a6435e2d58c16b8986370
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a><span data-ttu-id="f6046-102">BAM 通知的命令行脚本服务配置文件</span><span class="sxs-lookup"><span data-stu-id="f6046-102">BAM Command-Line Script for Notification Services Configuration Files</span></span>
<span data-ttu-id="f6046-103">管理员使用 ProcessBamNSFiles.vbs 脚本自定义 BAM 警报的 SQL Server Notification Services 的行为。</span><span class="sxs-lookup"><span data-stu-id="f6046-103">Administrators use the ProcessBamNSFiles.vbs script to customize the behavior of SQL Server Notification Services for BAM alerts.</span></span> <span data-ttu-id="f6046-104">您可以使用该脚本获取 Notification Services 应用程序定义文件 (ADF) 和 Notification Services 配置文件。</span><span class="sxs-lookup"><span data-stu-id="f6046-104">You can use the script to obtain the Notification Services application definition file (ADF) and Notification Services configuration file.</span></span> <span data-ttu-id="f6046-105">可以对这些文件进行修改，然后使用该脚本来应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="f6046-105">These files can be modified and then the script can be used to apply the changes.</span></span>  
  
 <span data-ttu-id="f6046-106">应该从 Notification Services 命令提示符而不是常规的命令提示符来运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="f6046-106">You run the script from a Notification Services command prompt and not from a typical command prompt.</span></span> <span data-ttu-id="f6046-107">从常规的命令提示符运行该脚本将导致脚本执行错误。</span><span class="sxs-lookup"><span data-stu-id="f6046-107">Running the script from a typical command prompt will cause the script to execute incorrectly.</span></span> <span data-ttu-id="f6046-108">运行脚本时，所有参数都是必需的。</span><span class="sxs-lookup"><span data-stu-id="f6046-108">When running the script all parameters are mandatory.</span></span>  
  
## <a name="get-command"></a><span data-ttu-id="f6046-109">Get 命令</span><span class="sxs-lookup"><span data-stu-id="f6046-109">Get command</span></span>  
 <span data-ttu-id="f6046-110">**用法**</span><span class="sxs-lookup"><span data-stu-id="f6046-110">**Usage**</span></span>  
  
 <span data-ttu-id="f6046-111">**cscript ProcessBamNSFiles-获取\<配置文件路径\> \<ADF 文件路径\>\<主导入服务器\>\<主导入数据库  \>**</span><span class="sxs-lookup"><span data-stu-id="f6046-111">**cscript ProcessBamNSFiles -Get \<configuration file path\> \<ADF file path\>  \<primary import server\> \<primary import database\>**</span></span>  
  
|<span data-ttu-id="f6046-112">参数</span><span class="sxs-lookup"><span data-stu-id="f6046-112">Parameter</span></span>|<span data-ttu-id="f6046-113">Description</span><span class="sxs-lookup"><span data-stu-id="f6046-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6046-114">配置文件路径</span><span class="sxs-lookup"><span data-stu-id="f6046-114">configuration file path</span></span>|<span data-ttu-id="f6046-115">指定配置文件的名称和存储位置。</span><span class="sxs-lookup"><span data-stu-id="f6046-115">Specifies the name and location in which to store the configuration file.</span></span>|  
|<span data-ttu-id="f6046-116">ADF 文件路径</span><span class="sxs-lookup"><span data-stu-id="f6046-116">ADF file path</span></span>|<span data-ttu-id="f6046-117">指定 ADF 文件的名称和存储位置。</span><span class="sxs-lookup"><span data-stu-id="f6046-117">Specifies the name and location in which to store the ADF file.</span></span>|  
|<span data-ttu-id="f6046-118">主导入服务器</span><span class="sxs-lookup"><span data-stu-id="f6046-118">primary import server</span></span>|<span data-ttu-id="f6046-119">存储 BAM 主导入数据库的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="f6046-119">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="f6046-120">主导入数据库</span><span class="sxs-lookup"><span data-stu-id="f6046-120">primary import database</span></span>|<span data-ttu-id="f6046-121">BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f6046-121">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="f6046-122">从 BAM 主导入数据库检索 Notification Services 配置文件和应用程序定义文件，并将这些文件保存到指定路径。</span><span class="sxs-lookup"><span data-stu-id="f6046-122">Retrieves the Notification Services configuration and application definition files from the BAM Primary Import database and saves them to specified paths.</span></span>  
  
## <a name="update-command"></a><span data-ttu-id="f6046-123">Update 命令</span><span class="sxs-lookup"><span data-stu-id="f6046-123">Update command</span></span>  
 <span data-ttu-id="f6046-124">**用法**</span><span class="sxs-lookup"><span data-stu-id="f6046-124">**Usage**</span></span>  
  
 <span data-ttu-id="f6046-125">**cscript ProcessBamNSFiles-更新\<configfilepath\> \<adffilepath\>\<primaryimport 服务器\>\<主导入数据库  \>**</span><span class="sxs-lookup"><span data-stu-id="f6046-125">**cscript ProcessBamNSFiles -Update \<configfilepath\> \<adffilepath\>  \<primaryimport server\> \<primary import db\>**</span></span>  
  
|<span data-ttu-id="f6046-126">参数</span><span class="sxs-lookup"><span data-stu-id="f6046-126">Parameter</span></span>|<span data-ttu-id="f6046-127">Description</span><span class="sxs-lookup"><span data-stu-id="f6046-127">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6046-128">配置文件路径</span><span class="sxs-lookup"><span data-stu-id="f6046-128">configuration file path</span></span>|<span data-ttu-id="f6046-129">指定从其更新 Notification Services 配置信息的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="f6046-129">Specifies the name and location from which to update the Notification Services configuration information.</span></span>|  
|<span data-ttu-id="f6046-130">ADF 文件路径</span><span class="sxs-lookup"><span data-stu-id="f6046-130">ADF file path</span></span>|<span data-ttu-id="f6046-131">指定从其更新 ADF 信息的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="f6046-131">Specifies the name and location from which to update the ADF information.</span></span>|  
|<span data-ttu-id="f6046-132">主导入服务器</span><span class="sxs-lookup"><span data-stu-id="f6046-132">primary import server</span></span>|<span data-ttu-id="f6046-133">存储 BAM 主导入数据库的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="f6046-133">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="f6046-134">主导入数据库</span><span class="sxs-lookup"><span data-stu-id="f6046-134">primary import database</span></span>|<span data-ttu-id="f6046-135">BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f6046-135">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="f6046-136">调用 Notification Services，并用指定文件中的信息更新设置。</span><span class="sxs-lookup"><span data-stu-id="f6046-136">Calls Notification Services and updates the settings with the information in the specified files.</span></span> <span data-ttu-id="f6046-137">配置文件和 ADF 文件存储在 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="f6046-137">The configuration and ADF files are stored in the BAM Primary Import database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6046-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6046-138">See Also</span></span>  
 [<span data-ttu-id="f6046-139">BAM 命令行工具</span><span class="sxs-lookup"><span data-stu-id="f6046-139">BAM Command-Line Tools</span></span>](../core/bam-command-line-tools.md)