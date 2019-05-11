---
title: 对包含 BFILE 数据类型在 Oracle 数据库中的表的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028e560dc7a536dd99b8a9461211dd3e712a361a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376306"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a><span data-ttu-id="376c6-102">对包含 BFILE 数据类型在 Oracle 数据库中的表的操作</span><span class="sxs-lookup"><span data-stu-id="376c6-102">Operations on Tables With BFILE Data Types in Oracle Database</span></span>
<span data-ttu-id="376c6-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表和存储的过程中支持 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="376c6-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the BFILE data type in tables and stored procedures.</span></span> <span data-ttu-id="376c6-104">下表总结了由适配器基于执行的操作公开的 BFILE 数据类型和访问 LOB 项目 （表/过程）：</span><span class="sxs-lookup"><span data-stu-id="376c6-104">The following table summarizes the BFILE data type exposed by the adapter based on the operation performed and the LOB artifact (table/procedure) accessed:</span></span>  
  
|<span data-ttu-id="376c6-105">项目</span><span class="sxs-lookup"><span data-stu-id="376c6-105">Artifact</span></span>|<span data-ttu-id="376c6-106">操作</span><span class="sxs-lookup"><span data-stu-id="376c6-106">Operation</span></span>|<span data-ttu-id="376c6-107">BFILE col/param 公开的数据类型</span><span class="sxs-lookup"><span data-stu-id="376c6-107">Data type exposed for BFILE col/param</span></span>|<span data-ttu-id="376c6-108">注释</span><span class="sxs-lookup"><span data-stu-id="376c6-108">Comments</span></span>|  
|--------------|---------------|--------------------------------------------|--------------|  
|<span data-ttu-id="376c6-109">TABLE</span><span class="sxs-lookup"><span data-stu-id="376c6-109">TABLE</span></span>|<span data-ttu-id="376c6-110">Insert</span><span class="sxs-lookup"><span data-stu-id="376c6-110">INSERT</span></span>|<span data-ttu-id="376c6-111">String</span><span class="sxs-lookup"><span data-stu-id="376c6-111">String</span></span>|<span data-ttu-id="376c6-112">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="376c6-112">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="376c6-113">例如</span><span class="sxs-lookup"><span data-stu-id="376c6-113">E.g.</span></span> <span data-ttu-id="376c6-114">MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="376c6-114">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="376c6-115">TABLE</span><span class="sxs-lookup"><span data-stu-id="376c6-115">TABLE</span></span>|<span data-ttu-id="376c6-116">UPDATE</span><span class="sxs-lookup"><span data-stu-id="376c6-116">UPDATE</span></span>|<span data-ttu-id="376c6-117">String</span><span class="sxs-lookup"><span data-stu-id="376c6-117">String</span></span>|<span data-ttu-id="376c6-118">表示要更新到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="376c6-118">Represents the logical Oracle directory path to the file to be updated into the BFILE column</span></span>|  
|<span data-ttu-id="376c6-119">TABLE</span><span class="sxs-lookup"><span data-stu-id="376c6-119">TABLE</span></span>|<span data-ttu-id="376c6-120">SELECT</span><span class="sxs-lookup"><span data-stu-id="376c6-120">SELECT</span></span>|<span data-ttu-id="376c6-121">byte[]</span><span class="sxs-lookup"><span data-stu-id="376c6-121">byte[]</span></span>|<span data-ttu-id="376c6-122">表示二进制数据构成 BFILE</span><span class="sxs-lookup"><span data-stu-id="376c6-122">Represents the binary data constituting the BFILE</span></span>|  
|<span data-ttu-id="376c6-123">存储的过程</span><span class="sxs-lookup"><span data-stu-id="376c6-123">STORED PROC</span></span>|<span data-ttu-id="376c6-124">在参数中</span><span class="sxs-lookup"><span data-stu-id="376c6-124">IN PARAM</span></span>|<span data-ttu-id="376c6-125">String</span><span class="sxs-lookup"><span data-stu-id="376c6-125">String</span></span>|<span data-ttu-id="376c6-126">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="376c6-126">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="376c6-127">例如</span><span class="sxs-lookup"><span data-stu-id="376c6-127">E.g.</span></span> <span data-ttu-id="376c6-128">MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="376c6-128">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="376c6-129">存储的过程</span><span class="sxs-lookup"><span data-stu-id="376c6-129">STORED PROC</span></span>|<span data-ttu-id="376c6-130">OUT 参数</span><span class="sxs-lookup"><span data-stu-id="376c6-130">OUT PARAM</span></span>|<span data-ttu-id="376c6-131">String</span><span class="sxs-lookup"><span data-stu-id="376c6-131">String</span></span>|<span data-ttu-id="376c6-132">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="376c6-132">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="376c6-133">例如</span><span class="sxs-lookup"><span data-stu-id="376c6-133">E.g.</span></span> <span data-ttu-id="376c6-134">MYDIR/screen.jpg MYDIR 其中是 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="376c6-134">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="376c6-135">存储的过程</span><span class="sxs-lookup"><span data-stu-id="376c6-135">STORED PROC</span></span>|<span data-ttu-id="376c6-136">INOUT 参数</span><span class="sxs-lookup"><span data-stu-id="376c6-136">INOUT PARAM</span></span>|<span data-ttu-id="376c6-137">不支持</span><span class="sxs-lookup"><span data-stu-id="376c6-137">Not Supported</span></span>|-|  
  
 <span data-ttu-id="376c6-138">在包含 BFILE 数据类型的表上还支持特殊操作 ReadLOB。</span><span class="sxs-lookup"><span data-stu-id="376c6-138">The special operation ReadLOB is also supported on tables with BFILE data type.</span></span> <span data-ttu-id="376c6-139">不支持 UpdateLOB 操作。</span><span class="sxs-lookup"><span data-stu-id="376c6-139">The UpdateLOB operation is not supported.</span></span> <span data-ttu-id="376c6-140">适配器客户端或者可以使用更新操作。</span><span class="sxs-lookup"><span data-stu-id="376c6-140">Adapter clients can alternately use the UPDATE operation.</span></span>  
  
 <span data-ttu-id="376c6-141">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="376c6-141">For more information about:</span></span>  
  
- <span data-ttu-id="376c6-142">对包含 BFILE 数据类型使用的表执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[包含 BFILE 数据类型在 Oracle 数据库中使用 BizTalk Server 运行操作表](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="376c6-142">Performing operations on tables containing BFILE data types by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run operations on Tables with BFILE Data Types in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="376c6-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="376c6-143">See Also</span></span>  
 <span data-ttu-id="376c6-144">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="376c6-144">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>