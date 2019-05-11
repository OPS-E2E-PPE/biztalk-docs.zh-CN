---
title: BAM 命令行脚本，用于通知服务配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf28ea2c1ff0defd7696b548ff86bc050259925d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528718"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a><span data-ttu-id="bf32a-102">BAM 命令行脚本，用于通知服务配置文件</span><span class="sxs-lookup"><span data-stu-id="bf32a-102">BAM Command-Line Script for Notification Services Configuration Files</span></span>
<span data-ttu-id="bf32a-103">管理员使用 ProcessBamNSFiles.vbs 脚本自定义 BAM 警报的 SQL Server Notification Services 的行为。</span><span class="sxs-lookup"><span data-stu-id="bf32a-103">Administrators use the ProcessBamNSFiles.vbs script to customize the behavior of SQL Server Notification Services for BAM alerts.</span></span> <span data-ttu-id="bf32a-104">您可以使用脚本获取 Notification Services 应用程序定义文件 (ADF) 和 Notification Services 配置文件。</span><span class="sxs-lookup"><span data-stu-id="bf32a-104">You can use the script to obtain the Notification Services application definition file (ADF) and Notification Services configuration file.</span></span> <span data-ttu-id="bf32a-105">可以修改这些文件，然后使用该脚本以应用更改。</span><span class="sxs-lookup"><span data-stu-id="bf32a-105">These files can be modified and then the script can be used to apply the changes.</span></span>  
  
 <span data-ttu-id="bf32a-106">Notification Services 命令提示符下，而不是从常规的命令提示符运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="bf32a-106">You run the script from a Notification Services command prompt and not from a typical command prompt.</span></span> <span data-ttu-id="bf32a-107">在典型的命令提示符下运行该脚本将导致脚本执行错误。</span><span class="sxs-lookup"><span data-stu-id="bf32a-107">Running the script from a typical command prompt will cause the script to execute incorrectly.</span></span> <span data-ttu-id="bf32a-108">运行脚本时所有参数都是必需的。</span><span class="sxs-lookup"><span data-stu-id="bf32a-108">When running the script all parameters are mandatory.</span></span>  
  
## <a name="get-command"></a><span data-ttu-id="bf32a-109">获取命令</span><span class="sxs-lookup"><span data-stu-id="bf32a-109">Get command</span></span>  
 <span data-ttu-id="bf32a-110">**Usage**</span><span class="sxs-lookup"><span data-stu-id="bf32a-110">**Usage**</span></span>  
  
 <span data-ttu-id="bf32a-111">**cscript ProcessBamNSFiles-Get\<配置文件路径\> \<ADF 文件路径\>\<主导入服务器\>\<主导入数据库  \>**</span><span class="sxs-lookup"><span data-stu-id="bf32a-111">**cscript ProcessBamNSFiles -Get \<configuration file path\> \<ADF file path\>  \<primary import server\> \<primary import database\>**</span></span>  
  
|<span data-ttu-id="bf32a-112">参数</span><span class="sxs-lookup"><span data-stu-id="bf32a-112">Parameter</span></span>|<span data-ttu-id="bf32a-113">Description</span><span class="sxs-lookup"><span data-stu-id="bf32a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf32a-114">配置文件路径</span><span class="sxs-lookup"><span data-stu-id="bf32a-114">configuration file path</span></span>|<span data-ttu-id="bf32a-115">指定的名称和要在其中存储配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="bf32a-115">Specifies the name and location in which to store the configuration file.</span></span>|  
|<span data-ttu-id="bf32a-116">ADF 文件路径</span><span class="sxs-lookup"><span data-stu-id="bf32a-116">ADF file path</span></span>|<span data-ttu-id="bf32a-117">指定的名称和要在其中存储该 ADF 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="bf32a-117">Specifies the name and location in which to store the ADF file.</span></span>|  
|<span data-ttu-id="bf32a-118">主导入服务器</span><span class="sxs-lookup"><span data-stu-id="bf32a-118">primary import server</span></span>|<span data-ttu-id="bf32a-119">在其中存储 BAM 主导入数据库的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="bf32a-119">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="bf32a-120">主导入数据库</span><span class="sxs-lookup"><span data-stu-id="bf32a-120">primary import database</span></span>|<span data-ttu-id="bf32a-121">BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="bf32a-121">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="bf32a-122">检索 Notification Services 配置和应用程序定义文件从 BAM 主导入数据库，并将保存到指定的路径。</span><span class="sxs-lookup"><span data-stu-id="bf32a-122">Retrieves the Notification Services configuration and application definition files from the BAM Primary Import database and saves them to specified paths.</span></span>  
  
## <a name="update-command"></a><span data-ttu-id="bf32a-123">Update 命令</span><span class="sxs-lookup"><span data-stu-id="bf32a-123">Update command</span></span>  
 <span data-ttu-id="bf32a-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="bf32a-124">**Usage**</span></span>  
  
 <span data-ttu-id="bf32a-125">**cscript ProcessBamNSFiles -Update \<configfilepath\> \<adffilepath\>  \<primaryimport server\> \<primary import db\>**</span><span class="sxs-lookup"><span data-stu-id="bf32a-125">**cscript ProcessBamNSFiles -Update \<configfilepath\> \<adffilepath\>  \<primaryimport server\> \<primary import db\>**</span></span>  
  
|<span data-ttu-id="bf32a-126">参数</span><span class="sxs-lookup"><span data-stu-id="bf32a-126">Parameter</span></span>|<span data-ttu-id="bf32a-127">Description</span><span class="sxs-lookup"><span data-stu-id="bf32a-127">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf32a-128">配置文件路径</span><span class="sxs-lookup"><span data-stu-id="bf32a-128">configuration file path</span></span>|<span data-ttu-id="bf32a-129">指定的名称和从其更新 Notification Services 配置信息的位置。</span><span class="sxs-lookup"><span data-stu-id="bf32a-129">Specifies the name and location from which to update the Notification Services configuration information.</span></span>|  
|<span data-ttu-id="bf32a-130">ADF 文件路径</span><span class="sxs-lookup"><span data-stu-id="bf32a-130">ADF file path</span></span>|<span data-ttu-id="bf32a-131">指定的名称和从其更新 ADF 信息的位置。</span><span class="sxs-lookup"><span data-stu-id="bf32a-131">Specifies the name and location from which to update the ADF information.</span></span>|  
|<span data-ttu-id="bf32a-132">主导入服务器</span><span class="sxs-lookup"><span data-stu-id="bf32a-132">primary import server</span></span>|<span data-ttu-id="bf32a-133">在其中存储 BAM 主导入数据库的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="bf32a-133">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="bf32a-134">主导入数据库</span><span class="sxs-lookup"><span data-stu-id="bf32a-134">primary import database</span></span>|<span data-ttu-id="bf32a-135">BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="bf32a-135">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="bf32a-136">调用 Notification Services，并使用指定的文件中的信息将更新的设置。</span><span class="sxs-lookup"><span data-stu-id="bf32a-136">Calls Notification Services and updates the settings with the information in the specified files.</span></span> <span data-ttu-id="bf32a-137">配置文件和 ADF 文件存储在 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="bf32a-137">The configuration and ADF files are stored in the BAM Primary Import database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf32a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf32a-138">See Also</span></span>  
 [<span data-ttu-id="bf32a-139">BAM 命令行工具</span><span class="sxs-lookup"><span data-stu-id="bf32a-139">BAM Command-Line Tools</span></span>](../core/bam-command-line-tools.md)