---
title: 对 Oracle 数据库中的 BFILE 数据类型的表的操作 |Microsoft 文档
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
ms.openlocfilehash: c236651e6c44248ea8f6cf0f73f0c9bc17e46ac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214309"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a><span data-ttu-id="d589b-102">对 Oracle 数据库中的 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="d589b-102">Operations on Tables With BFILE Data Types in Oracle Database</span></span>
<span data-ttu-id="d589b-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表和存储的过程中支持 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="d589b-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the BFILE data type in tables and stored procedures.</span></span> <span data-ttu-id="d589b-104">下表总结了 BFILE 数据类型公开的执行的操作所基于的适配器和 LOB 项目 （表/过程） 访问：</span><span class="sxs-lookup"><span data-stu-id="d589b-104">The following table summarizes the BFILE data type exposed by the adapter based on the operation performed and the LOB artifact (table/procedure) accessed:</span></span>  
  
|<span data-ttu-id="d589b-105">项目</span><span class="sxs-lookup"><span data-stu-id="d589b-105">Artifact</span></span>|<span data-ttu-id="d589b-106">运算</span><span class="sxs-lookup"><span data-stu-id="d589b-106">Operation</span></span>|<span data-ttu-id="d589b-107">BFILE 列/param 的公开的数据类型</span><span class="sxs-lookup"><span data-stu-id="d589b-107">Data type exposed for BFILE col/param</span></span>|<span data-ttu-id="d589b-108">注释</span><span class="sxs-lookup"><span data-stu-id="d589b-108">Comments</span></span>|  
|--------------|---------------|--------------------------------------------|--------------|  
|<span data-ttu-id="d589b-109">TABLE</span><span class="sxs-lookup"><span data-stu-id="d589b-109">TABLE</span></span>|<span data-ttu-id="d589b-110">Insert</span><span class="sxs-lookup"><span data-stu-id="d589b-110">INSERT</span></span>|<span data-ttu-id="d589b-111">字符串</span><span class="sxs-lookup"><span data-stu-id="d589b-111">String</span></span>|<span data-ttu-id="d589b-112">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="d589b-112">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="d589b-113">例如</span><span class="sxs-lookup"><span data-stu-id="d589b-113">E.g.</span></span> <span data-ttu-id="d589b-114">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="d589b-114">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="d589b-115">TABLE</span><span class="sxs-lookup"><span data-stu-id="d589b-115">TABLE</span></span>|<span data-ttu-id="d589b-116">UPDATE</span><span class="sxs-lookup"><span data-stu-id="d589b-116">UPDATE</span></span>|<span data-ttu-id="d589b-117">字符串</span><span class="sxs-lookup"><span data-stu-id="d589b-117">String</span></span>|<span data-ttu-id="d589b-118">表示要插入 BFILE 列更新的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="d589b-118">Represents the logical Oracle directory path to the file to be updated into the BFILE column</span></span>|  
|<span data-ttu-id="d589b-119">TABLE</span><span class="sxs-lookup"><span data-stu-id="d589b-119">TABLE</span></span>|<span data-ttu-id="d589b-120">SELECT</span><span class="sxs-lookup"><span data-stu-id="d589b-120">SELECT</span></span>|<span data-ttu-id="d589b-121">byte[]</span><span class="sxs-lookup"><span data-stu-id="d589b-121">byte[]</span></span>|<span data-ttu-id="d589b-122">表示构成 BFILE 的二进制数据</span><span class="sxs-lookup"><span data-stu-id="d589b-122">Represents the binary data constituting the BFILE</span></span>|  
|<span data-ttu-id="d589b-123">存储的过程</span><span class="sxs-lookup"><span data-stu-id="d589b-123">STORED PROC</span></span>|<span data-ttu-id="d589b-124">PARAM 中</span><span class="sxs-lookup"><span data-stu-id="d589b-124">IN PARAM</span></span>|<span data-ttu-id="d589b-125">字符串</span><span class="sxs-lookup"><span data-stu-id="d589b-125">String</span></span>|<span data-ttu-id="d589b-126">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="d589b-126">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="d589b-127">例如</span><span class="sxs-lookup"><span data-stu-id="d589b-127">E.g.</span></span> <span data-ttu-id="d589b-128">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="d589b-128">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="d589b-129">存储的过程</span><span class="sxs-lookup"><span data-stu-id="d589b-129">STORED PROC</span></span>|<span data-ttu-id="d589b-130">OUT 参数</span><span class="sxs-lookup"><span data-stu-id="d589b-130">OUT PARAM</span></span>|<span data-ttu-id="d589b-131">字符串</span><span class="sxs-lookup"><span data-stu-id="d589b-131">String</span></span>|<span data-ttu-id="d589b-132">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="d589b-132">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="d589b-133">例如</span><span class="sxs-lookup"><span data-stu-id="d589b-133">E.g.</span></span> <span data-ttu-id="d589b-134">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="d589b-134">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="d589b-135">存储的过程</span><span class="sxs-lookup"><span data-stu-id="d589b-135">STORED PROC</span></span>|<span data-ttu-id="d589b-136">INOUT PARAM</span><span class="sxs-lookup"><span data-stu-id="d589b-136">INOUT PARAM</span></span>|<span data-ttu-id="d589b-137">不支持</span><span class="sxs-lookup"><span data-stu-id="d589b-137">Not Supported</span></span>|-|  
  
 <span data-ttu-id="d589b-138">BFILE 数据类型的表上还支持特殊操作 ReadLOB。</span><span class="sxs-lookup"><span data-stu-id="d589b-138">The special operation ReadLOB is also supported on tables with BFILE data type.</span></span> <span data-ttu-id="d589b-139">不支持 UpdateLOB 操作。</span><span class="sxs-lookup"><span data-stu-id="d589b-139">The UpdateLOB operation is not supported.</span></span> <span data-ttu-id="d589b-140">适配器客户端或者可以使用更新操作。</span><span class="sxs-lookup"><span data-stu-id="d589b-140">Adapter clients can alternately use the UPDATE operation.</span></span>  
  
 <span data-ttu-id="d589b-141">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="d589b-141">For more information about:</span></span>  
  
-   <span data-ttu-id="d589b-142">在通过使用包含 BFILE 数据类型的表上执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[BFILE 数据类型，使用 BizTalk Server 的 Oracle 数据库中使用运行对表的操作](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="d589b-142">Performing operations on tables containing BFILE data types by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run operations on Tables with BFILE Data Types in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d589b-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d589b-143">See Also</span></span>  
 <span data-ttu-id="d589b-144">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="d589b-144">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>