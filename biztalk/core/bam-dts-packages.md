---
title: "BAM DTS 包 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 105d1b42848b73505d9a82df07693111708ce802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-dts-packages"></a><span data-ttu-id="d3466-102">BAM DTS 包</span><span class="sxs-lookup"><span data-stu-id="d3466-102">BAM DTS Packages</span></span>
<span data-ttu-id="d3466-103">管理员可以更新以下 BAM DTS 包的参数：</span><span class="sxs-lookup"><span data-stu-id="d3466-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
-   <span data-ttu-id="d3466-104">**CubeUpdate**数据转换服务 (DTS) 包始终位于星型架构数据库所在的同一服务器上。</span><span class="sxs-lookup"><span data-stu-id="d3466-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
-   <span data-ttu-id="d3466-105">**DataMaintenance** DTS 包始终位于与主导入数据库相同的服务器上。</span><span class="sxs-lookup"><span data-stu-id="d3466-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
 <span data-ttu-id="d3466-106">DTS 包使用 BAMConfiguration.xml 文件中的以下参数。</span><span class="sxs-lookup"><span data-stu-id="d3466-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="d3466-107">参数</span><span class="sxs-lookup"><span data-stu-id="d3466-107">Parameter</span></span>|<span data-ttu-id="d3466-108">Description</span><span class="sxs-lookup"><span data-stu-id="d3466-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3466-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="d3466-109">ConnectionTimeOut</span></span>|<span data-ttu-id="d3466-110">DTS 连接超时值（以秒为单位）是一个整数。</span><span class="sxs-lookup"><span data-stu-id="d3466-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="d3466-111">如果省略 ConnectionTimeOut 参数，则该配置文件使用默认值 60 秒。</span><span class="sxs-lookup"><span data-stu-id="d3466-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="d3466-112">加密</span><span class="sxs-lookup"><span data-stu-id="d3466-112">Encryption</span></span>|<span data-ttu-id="d3466-113">默认情况下，DTS 包在转换数据时不加密数据（即 Encryption 值为 0）。</span><span class="sxs-lookup"><span data-stu-id="d3466-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="d3466-114">将 Encryption 设置为 1 可以在转换时进行加密。</span><span class="sxs-lookup"><span data-stu-id="d3466-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="d3466-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="d3466-115">OwnerPassword</span></span>|<span data-ttu-id="d3466-116">DTS 包所有者的密码。</span><span class="sxs-lookup"><span data-stu-id="d3466-116">The password for the DTS package owner.</span></span> <span data-ttu-id="d3466-117">DTS 包所有者可以打开和修改 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="d3466-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="d3466-118">有关 DTS 包所有者的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d3466-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="d3466-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="d3466-119">UserPassword</span></span>|<span data-ttu-id="d3466-120">DTS 用户的密码。</span><span class="sxs-lookup"><span data-stu-id="d3466-120">The password for the DTS user.</span></span> <span data-ttu-id="d3466-121">DTS 包的用户可以运行 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="d3466-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="d3466-122">有关 DTS 包的用户的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="d3466-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="d3466-123">在 BAMConfiguration.xml 文件中，DTS 包使用以下命名约定：</span><span class="sxs-lookup"><span data-stu-id="d3466-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
-   <span data-ttu-id="d3466-124">**CubeUpdate** DTS 包</span><span class="sxs-lookup"><span data-stu-id="d3466-124">**CubeUpdate** DTS package</span></span>  
  
     <span data-ttu-id="d3466-125">**bam_AN_\<** </span><span class="sxs-lookup"><span data-stu-id="d3466-125">**bam_AN_\<** </span></span>  
     <span data-ttu-id="d3466-126">***多维数据集名称* >**，其中多维数据集名称是该多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="d3466-126">***CubeName* >**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="d3466-127">BAM 工作簿从视图名称生成该多维数据集名称。</span><span class="sxs-lookup"><span data-stu-id="d3466-127">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="d3466-128">如果在 BAM 配置 XML 文档中修改该多维数据集名称，则将在 DTS 包名称中使用新的多维数据集名称。</span><span class="sxs-lookup"><span data-stu-id="d3466-128">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
-   <span data-ttu-id="d3466-129">**DataMaintenance** DTS 包</span><span class="sxs-lookup"><span data-stu-id="d3466-129">**DataMaintenance** DTS package</span></span>  
  
     <span data-ttu-id="d3466-130">**bam_DM_\<** </span><span class="sxs-lookup"><span data-stu-id="d3466-130">**bam_DM_\<** </span></span>  
     <span data-ttu-id="d3466-131">***ActivityName* >**，其中 ActivityName 是活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d3466-131">***ActivityName* >**, where ActivityName is the name of the activity.</span></span>  
  
 <span data-ttu-id="d3466-132">您可以运行 CubeUpdate DTS 包来聚合计划的聚合。</span><span class="sxs-lookup"><span data-stu-id="d3466-132">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="d3466-133">在下一部分中，您可以为实时数据聚合指定时段。</span><span class="sxs-lookup"><span data-stu-id="d3466-133">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3466-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3466-134">See Also</span></span>  
 <span data-ttu-id="d3466-135">[BAM 配置架构](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="d3466-135">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="d3466-136">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="d3466-136">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="d3466-137">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="d3466-137">Managing BAM</span></span>](../core/managing-bam.md)