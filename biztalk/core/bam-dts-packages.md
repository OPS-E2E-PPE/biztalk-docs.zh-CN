---
title: BAM DTS 包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30cbcb583f1e175f5d65565c2108361ec9121721
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528887"
---
# <a name="bam-dts-packages"></a><span data-ttu-id="b28be-102">BAM DTS 包</span><span class="sxs-lookup"><span data-stu-id="b28be-102">BAM DTS Packages</span></span>
<span data-ttu-id="b28be-103">管理员可以更新以下 BAM DTS 包的参数：</span><span class="sxs-lookup"><span data-stu-id="b28be-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
- <span data-ttu-id="b28be-104">**CubeUpdate** Data Transformation Services (DTS) 包始终位于星型架构数据库所在的同一服务器上。</span><span class="sxs-lookup"><span data-stu-id="b28be-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
- <span data-ttu-id="b28be-105">**DataMaintenance** DTS 包始终位于主导入数据库所在的同一服务器上。</span><span class="sxs-lookup"><span data-stu-id="b28be-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
  <span data-ttu-id="b28be-106">DTS 包使用 BAMConfiguration.xml 文件中的以下参数。</span><span class="sxs-lookup"><span data-stu-id="b28be-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="b28be-107">参数</span><span class="sxs-lookup"><span data-stu-id="b28be-107">Parameter</span></span>|<span data-ttu-id="b28be-108">Description</span><span class="sxs-lookup"><span data-stu-id="b28be-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b28be-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="b28be-109">ConnectionTimeOut</span></span>|<span data-ttu-id="b28be-110">DTS 连接超时值 （以秒为单位） 是一个整数。</span><span class="sxs-lookup"><span data-stu-id="b28be-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="b28be-111">如果省略 ConnectionTimeOut 参数，该配置文件使用 60 秒，默认值。</span><span class="sxs-lookup"><span data-stu-id="b28be-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="b28be-112">加密</span><span class="sxs-lookup"><span data-stu-id="b28be-112">Encryption</span></span>|<span data-ttu-id="b28be-113">默认情况下，DTS 包执行数据时不加密这些转换数据 （加密值为 0）。</span><span class="sxs-lookup"><span data-stu-id="b28be-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="b28be-114">将加密设置为 1，以便在转换期间加密数据。</span><span class="sxs-lookup"><span data-stu-id="b28be-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="b28be-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="b28be-115">OwnerPassword</span></span>|<span data-ttu-id="b28be-116">DTS 包所有者密码。</span><span class="sxs-lookup"><span data-stu-id="b28be-116">The password for the DTS package owner.</span></span> <span data-ttu-id="b28be-117">DTS 包所有者可以打开和修改 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="b28be-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="b28be-118">有关 DTS 包所有者的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="b28be-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="b28be-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="b28be-119">UserPassword</span></span>|<span data-ttu-id="b28be-120">DTS 用户的密码。</span><span class="sxs-lookup"><span data-stu-id="b28be-120">The password for the DTS user.</span></span> <span data-ttu-id="b28be-121">DTS 包的用户可以运行 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="b28be-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="b28be-122">有关 DTS 包的用户的信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="b28be-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="b28be-123">DTS 包使用 BAMConfiguration.xml 文件中的以下命名约定：</span><span class="sxs-lookup"><span data-stu-id="b28be-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
- <span data-ttu-id="b28be-124">**CubeUpdate** DTS 包</span><span class="sxs-lookup"><span data-stu-id="b28be-124">**CubeUpdate** DTS package</span></span>  
  
   <span data-ttu-id="b28be-125">**bam_AN_\<**  ***多维数据集名称* \>** ，其中 CubeName 是多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="b28be-125">**bam_AN_\<** ***CubeName* \>**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="b28be-126">BAM 工作簿从视图名称生成多维数据集名称。</span><span class="sxs-lookup"><span data-stu-id="b28be-126">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="b28be-127">如果您修改 BAM 配置 XML 文档中的多维数据集名称，DTS 包名称中使用新的多维数据集名称。</span><span class="sxs-lookup"><span data-stu-id="b28be-127">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
- <span data-ttu-id="b28be-128">**DataMaintenance** DTS 包</span><span class="sxs-lookup"><span data-stu-id="b28be-128">**DataMaintenance** DTS package</span></span>  
  
   <span data-ttu-id="b28be-129">**bam_DM_\<**  ***ActivityName* \>**，其中 ActivityName 是活动的名称。</span><span class="sxs-lookup"><span data-stu-id="b28be-129">**bam_DM_\<** ***ActivityName* \>**, where ActivityName is the name of the activity.</span></span>  
  
  <span data-ttu-id="b28be-130">运行 CubeUpdate DTS 包来聚合计划的聚合。</span><span class="sxs-lookup"><span data-stu-id="b28be-130">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="b28be-131">在下一部分中，可以指定实时数据聚合的时间窗口。</span><span class="sxs-lookup"><span data-stu-id="b28be-131">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28be-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b28be-132">See Also</span></span>  
 <span data-ttu-id="b28be-133">[BAM 配置架构](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="b28be-133">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="b28be-134">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="b28be-134">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="b28be-135">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="b28be-135">Managing BAM</span></span>](../core/managing-bam.md)