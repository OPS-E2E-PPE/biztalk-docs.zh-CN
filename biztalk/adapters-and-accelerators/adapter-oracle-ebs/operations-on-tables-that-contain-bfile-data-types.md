---
title: 对包含 BFILE 数据类型的表的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5096539b86512e51756d3a872ff566872ff520f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960995"
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a><span data-ttu-id="88428-102">对包含 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="88428-102">Operations on Tables That Contain BFILE Data Types</span></span>
<span data-ttu-id="88428-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]表和存储的过程中支持 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="88428-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the BFILE data type in tables and stored procedures.</span></span> 

## <a name="bfile-data-types"></a><span data-ttu-id="88428-104">BFILE 数据类型</span><span class="sxs-lookup"><span data-stu-id="88428-104">BFILE data types</span></span>
<span data-ttu-id="88428-105">下表总结了 BFILE 数据类型公开的执行的操作所基于的适配器和 LOB 项目 （表/过程） 访问：</span><span class="sxs-lookup"><span data-stu-id="88428-105">The following table summarizes the BFILE data type exposed by the adapter based on the operation performed and the LOB artifact (table/procedure) accessed:</span></span>  
  
|<span data-ttu-id="88428-106">项目</span><span class="sxs-lookup"><span data-stu-id="88428-106">Artifact</span></span>|<span data-ttu-id="88428-107">运算</span><span class="sxs-lookup"><span data-stu-id="88428-107">Operation</span></span>|<span data-ttu-id="88428-108">BFILE 列/param 的公开的数据类型</span><span class="sxs-lookup"><span data-stu-id="88428-108">Data type exposed for BFILE col/param</span></span>|<span data-ttu-id="88428-109">注释</span><span class="sxs-lookup"><span data-stu-id="88428-109">Comments</span></span>|  
|--------------|---------------|--------------------------------------------|--------------|  
|<span data-ttu-id="88428-110">TABLE</span><span class="sxs-lookup"><span data-stu-id="88428-110">TABLE</span></span>|<span data-ttu-id="88428-111">Insert</span><span class="sxs-lookup"><span data-stu-id="88428-111">INSERT</span></span>|<span data-ttu-id="88428-112">字符串</span><span class="sxs-lookup"><span data-stu-id="88428-112">String</span></span>|<span data-ttu-id="88428-113">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="88428-113">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="88428-114">例如</span><span class="sxs-lookup"><span data-stu-id="88428-114">E.g.</span></span> <span data-ttu-id="88428-115">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="88428-115">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="88428-116">TABLE</span><span class="sxs-lookup"><span data-stu-id="88428-116">TABLE</span></span>|<span data-ttu-id="88428-117">UPDATE</span><span class="sxs-lookup"><span data-stu-id="88428-117">UPDATE</span></span>|<span data-ttu-id="88428-118">字符串</span><span class="sxs-lookup"><span data-stu-id="88428-118">String</span></span>|<span data-ttu-id="88428-119">表示要插入 BFILE 列更新的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="88428-119">Represents the logical Oracle directory path to the file to be updated into the BFILE column</span></span>|  
|<span data-ttu-id="88428-120">TABLE</span><span class="sxs-lookup"><span data-stu-id="88428-120">TABLE</span></span>|<span data-ttu-id="88428-121">SELECT</span><span class="sxs-lookup"><span data-stu-id="88428-121">SELECT</span></span>|<span data-ttu-id="88428-122">byte[]</span><span class="sxs-lookup"><span data-stu-id="88428-122">byte[]</span></span>|<span data-ttu-id="88428-123">表示构成 BFILE 的二进制数据</span><span class="sxs-lookup"><span data-stu-id="88428-123">Represents the binary data constituting the BFILE</span></span>|  
|<span data-ttu-id="88428-124">存储的过程</span><span class="sxs-lookup"><span data-stu-id="88428-124">STORED PROC</span></span>|<span data-ttu-id="88428-125">PARAM 中</span><span class="sxs-lookup"><span data-stu-id="88428-125">IN PARAM</span></span>|<span data-ttu-id="88428-126">字符串</span><span class="sxs-lookup"><span data-stu-id="88428-126">String</span></span>|<span data-ttu-id="88428-127">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="88428-127">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="88428-128">例如</span><span class="sxs-lookup"><span data-stu-id="88428-128">E.g.</span></span> <span data-ttu-id="88428-129">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="88428-129">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="88428-130">存储的过程</span><span class="sxs-lookup"><span data-stu-id="88428-130">STORED PROC</span></span>|<span data-ttu-id="88428-131">OUT 参数</span><span class="sxs-lookup"><span data-stu-id="88428-131">OUT PARAM</span></span>|<span data-ttu-id="88428-132">字符串</span><span class="sxs-lookup"><span data-stu-id="88428-132">String</span></span>|<span data-ttu-id="88428-133">表示要插入到 BFILE 列的文件的逻辑的 Oracle 目录路径</span><span class="sxs-lookup"><span data-stu-id="88428-133">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="88428-134">例如</span><span class="sxs-lookup"><span data-stu-id="88428-134">E.g.</span></span> <span data-ttu-id="88428-135">MYDIR/screen.jpg MYDIR 所在 Oracle 中的逻辑目录</span><span class="sxs-lookup"><span data-stu-id="88428-135">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="88428-136">存储的过程</span><span class="sxs-lookup"><span data-stu-id="88428-136">STORED PROC</span></span>|<span data-ttu-id="88428-137">INOUT PARAM</span><span class="sxs-lookup"><span data-stu-id="88428-137">INOUT PARAM</span></span>|<span data-ttu-id="88428-138">不支持</span><span class="sxs-lookup"><span data-stu-id="88428-138">Not Supported</span></span>|-|  
  
 <span data-ttu-id="88428-139">特殊操作`Read_<LOBColName>`BFILE 数据类型的表中还支持其中\<LOBColName\>是 LOB 列的名称表中。</span><span class="sxs-lookup"><span data-stu-id="88428-139">The special operation `Read_<LOBColName>` is also supported on tables with BFILE data type, where \<LOBColName\> is the LOB column name in the table.</span></span> <span data-ttu-id="88428-140">`Update_<LOBColName>` BFILE 数据类型不支持操作。</span><span class="sxs-lookup"><span data-stu-id="88428-140">The `Update_<LOBColName>` operation is not supported for BFILE data type.</span></span> <span data-ttu-id="88428-141">适配器客户端或者可以使用更新操作。</span><span class="sxs-lookup"><span data-stu-id="88428-141">Adapter clients can alternately use the Update operation.</span></span>  
  
## <a name="more-good-info"></a><span data-ttu-id="88428-142">良好的详细信息</span><span class="sxs-lookup"><span data-stu-id="88428-142">More good info</span></span>  
  
-   <span data-ttu-id="88428-143">`Read_<LOBColName>`和`Update_<LOBColName>`操作，请参阅[接口表、 界面视图、 表和包含 LOB 数据的视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="88428-143">The `Read_<LOBColName>` and `Update_<LOBColName>` operations, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88428-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88428-144">See Also</span></span>  
 <span data-ttu-id="88428-145">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="88428-145">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>