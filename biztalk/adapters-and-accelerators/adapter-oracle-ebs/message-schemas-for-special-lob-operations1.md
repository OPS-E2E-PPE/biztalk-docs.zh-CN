---
title: "特殊 LOB Operations1 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b57e329d1de4740cac230cbb1e8151697d293dc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-special-lob-operations"></a><span data-ttu-id="a1816-102">特殊 LOB 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="a1816-102">Message Schemas for Special LOB Operations</span></span>
<span data-ttu-id="a1816-103">Read_\<LOBColName\>和 Update_\<LOBColName\>操作中加以表示的表和视图包含 LOB 列，其中\<LOBColName\>是表中的 LOB 列或视图。</span><span class="sxs-lookup"><span data-stu-id="a1816-103">The Read_\<LOBColName\> and Update_\<LOBColName\> operations are surfaced for tables and views that contain LOB columns, where \<LOBColName\> is the LOB column in the table or view.</span></span> <span data-ttu-id="a1816-104">这些操作，可以读取或写入 LOB 数据作为 base64Binary 编码数据的流。</span><span class="sxs-lookup"><span data-stu-id="a1816-104">These operations enable you to read or write the LOB data as a stream of base64Binary-encoded data.</span></span> <span data-ttu-id="a1816-105">它们对单个列的单个行中的 LOB 数据的操作。</span><span class="sxs-lookup"><span data-stu-id="a1816-105">They operate on a single column of LOB data in a single row.</span></span>  
  
 <span data-ttu-id="a1816-106">有关概述 Read_\<LOBColName\>和 Update_\<LOBColName\>操作和 Oracle LOB 数据类型支持，请参阅[接口表、 界面视图、 表上的操作和包含 LOB 数据的视图](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a1816-106">For an overview of the Read_\<LOBColName\> and Update_\<LOBColName\> operations and of the Oracle LOB data types supported, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="message-structure-of-lob-data-type-operations"></a><span data-ttu-id="a1816-107">LOB 数据类型操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="a1816-107">Message Structure of LOB Data-Type Operations</span></span>  
 <span data-ttu-id="a1816-108">下表显示请求和响应消息的结构为 Read_\<LOBColName\>和 Update_\<LOBColName\>操作。</span><span class="sxs-lookup"><span data-stu-id="a1816-108">The following table shows the structure of the request and response messages for the Read_\<LOBColName\> and Update_\<LOBColName\> operations.</span></span> <span data-ttu-id="a1816-109">该操作的目标表中的消息操作指定，也会出现在目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="a1816-109">The target table for the operation is specified in the message action and also appears in the target namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1816-110">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="a1816-110">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="a1816-111">运算</span><span class="sxs-lookup"><span data-stu-id="a1816-111">Operation</span></span>|<span data-ttu-id="a1816-112">XML 消息</span><span class="sxs-lookup"><span data-stu-id="a1816-112">XML Message</span></span>|<span data-ttu-id="a1816-113">Description</span><span class="sxs-lookup"><span data-stu-id="a1816-113">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="a1816-114">Read_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="a1816-114">Read_\<LOBColName\></span></span>|`<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`|<span data-ttu-id="a1816-115">LOB 数据行相匹配的位置中返回筛选器元素中指定的子句。</span><span class="sxs-lookup"><span data-stu-id="a1816-115">The LOB data in the row that matches the where clause specified in the FILTER element is returned.</span></span> <span data-ttu-id="a1816-116">Where 子句应匹配只有一行。</span><span class="sxs-lookup"><span data-stu-id="a1816-116">The where clause should match only a single row.</span></span> <span data-ttu-id="a1816-117">如果存在多个匹配的行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。</span><span class="sxs-lookup"><span data-stu-id="a1816-117">If there is more than one matching row, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span>|  
|<span data-ttu-id="a1816-118">Read_\<LOBColName\>响应</span><span class="sxs-lookup"><span data-stu-id="a1816-118">Read_\<LOBColName\> Response</span></span>|`<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>`|<span data-ttu-id="a1816-119">LOB 数据作为 base64Binary 编码数据的流返回。</span><span class="sxs-lookup"><span data-stu-id="a1816-119">The LOB data is returned as a stream of base64Binary encoded data.</span></span>|  
|<span data-ttu-id="a1816-120">Update_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="a1816-120">Update_\<LOBColName\></span></span>|`<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`|<span data-ttu-id="a1816-121">LOB 数据中的行的匹配 where 子句的筛选器元素中指定更新中的数据\<数据\>元素。</span><span class="sxs-lookup"><span data-stu-id="a1816-121">The LOB data in the row that matches the where clause specified in the FILTER element is updated with the data in the \<DATA\> element.</span></span> <span data-ttu-id="a1816-122">Where 子句应匹配只有一行。</span><span class="sxs-lookup"><span data-stu-id="a1816-122">The where clause should match only a single row.</span></span> <span data-ttu-id="a1816-123">如果存在多个匹配的行，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]引发异常。</span><span class="sxs-lookup"><span data-stu-id="a1816-123">If there is more than one matching row, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] throws an exception.</span></span><br /><br /> <span data-ttu-id="a1816-124">**请注意**更新 BLOB 列时\<数据\>元素必须始终包含一个 base64 编码值。</span><span class="sxs-lookup"><span data-stu-id="a1816-124">**Note** While updating BLOB columns, the \<DATA\> element must always contain a base64 encoded value.</span></span> <span data-ttu-id="a1816-125">CLOB 和 NCLOB、\<数据\>元素可包含字符串值。</span><span class="sxs-lookup"><span data-stu-id="a1816-125">For CLOB and NCLOB, the \<DATA\> element can have string values.</span></span>|  
|<span data-ttu-id="a1816-126">Update_\<LOBColName\>响应</span><span class="sxs-lookup"><span data-stu-id="a1816-126">Update_\<LOBColName\> Response</span></span>|`<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`|<span data-ttu-id="a1816-127">返回一个空响应。</span><span class="sxs-lookup"><span data-stu-id="a1816-127">An empty response is returned.</span></span>|  
  
 <span data-ttu-id="a1816-128">实体说明：</span><span class="sxs-lookup"><span data-stu-id="a1816-128">Entity descriptions:</span></span>  
  
 <span data-ttu-id="a1816-129">[VERSION] = 消息版本字符串;例如，"http://schemas.microsoft.com/OracleEBS/2008/05"。</span><span class="sxs-lookup"><span data-stu-id="a1816-129">[VERSION] = The message version string; for example, "http://schemas.microsoft.com/OracleEBS/2008/05".</span></span>  
  
 <span data-ttu-id="a1816-130">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a1816-130">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a1816-131">[TABLE_NAME] = 包含目标的 LOB 列; 的表例如，客户。</span><span class="sxs-lookup"><span data-stu-id="a1816-131">[TABLE_NAME] = The table that contains the targeted LOB column; for example, CUSTOMER.</span></span>  
  
 <span data-ttu-id="a1816-132">[LOBCol_Name] = LOB 列; 的名称例如，照片。</span><span class="sxs-lookup"><span data-stu-id="a1816-132">[LOBCol_Name] = The name of a LOB column; for example, Photo.</span></span>  
  
 <span data-ttu-id="a1816-133">[WHERE_clause] = An Oracle 数据库的 SELECT 语句的 WHERE 子句，匹配单个行;例如，ID = 1。</span><span class="sxs-lookup"><span data-stu-id="a1816-133">[WHERE_clause] = An Oracle database SELECT statement WHERE clause that matches a single row; for example, ID = 1.</span></span>  
  
 <span data-ttu-id="a1816-134">[LOB_DATA] = base64Binary 类型中的 LOB 列数据。</span><span class="sxs-lookup"><span data-stu-id="a1816-134">[LOB_DATA] = The LOB column data in base64Binary type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1816-135">Read_ 消息结构\<LOBColName\>和 Update_\<LOBColName\>视图上的操作相同表只是该操作的命名空间指定视图而不是表：`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.</span><span class="sxs-lookup"><span data-stu-id="a1816-135">The message structure for the Read_\<LOBColName\> and Update_\<LOBColName\> operations on views is the same as that on tables except that the namespace for the operation specifies a view rather than a table: `<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.</span></span>  
  
## <a name="message-actions-for-lob-data-type-operations"></a><span data-ttu-id="a1816-136">LOB 数据类型操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="a1816-136">Message Actions for LOB Data-Type Operations</span></span>  
 <span data-ttu-id="a1816-137">下表显示使用的消息操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为 Read_\<LOBColName\>和 Update_\<LOBColName\>对表的操作。</span><span class="sxs-lookup"><span data-stu-id="a1816-137">The following table shows the message actions that are used by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] for the Read_\<LOBColName\> and Update_\<LOBColName\> operations on tables.</span></span> <span data-ttu-id="a1816-138">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用表名称和消息操作中指定的 LOB 列名称来确定目标表和 LOB 操作的列。</span><span class="sxs-lookup"><span data-stu-id="a1816-138">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the table name and the LOB column name specified in the message action to determine the target table and LOB column for the operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1816-139">在表后，请参阅实体说明。</span><span class="sxs-lookup"><span data-stu-id="a1816-139">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="a1816-140">运算</span><span class="sxs-lookup"><span data-stu-id="a1816-140">Operation</span></span>|<span data-ttu-id="a1816-141">操作</span><span class="sxs-lookup"><span data-stu-id="a1816-141">Action</span></span>|<span data-ttu-id="a1816-142">示例</span><span class="sxs-lookup"><span data-stu-id="a1816-142">Example</span></span>|  
|---------------|------------|-------------|  
|<span data-ttu-id="a1816-143">Read_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="a1816-143">Read_\<LOBColName\></span></span>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|<span data-ttu-id="a1816-144">Read_\<LOBColName\>响应</span><span class="sxs-lookup"><span data-stu-id="a1816-144">Read_\<LOBColName\> Response</span></span>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|<span data-ttu-id="a1816-145">Update_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="a1816-145">Update_\<LOBColName\></span></span>|<span data-ttu-id="a1816-146">**为 BLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-146">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> <span data-ttu-id="a1816-147">**CLOB 和 NCLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-147">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|<span data-ttu-id="a1816-148">**为 BLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-148">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> <span data-ttu-id="a1816-149">**CLOB 和 NCLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-149">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|<span data-ttu-id="a1816-150">Update_\<LOBColName\>响应</span><span class="sxs-lookup"><span data-stu-id="a1816-150">Update_\<LOBColName\> Response</span></span>|<span data-ttu-id="a1816-151">**为 BLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-151">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> <span data-ttu-id="a1816-152">**CLOB 和 NCLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-152">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|<span data-ttu-id="a1816-153">**为 BLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-153">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> <span data-ttu-id="a1816-154">**CLOB 和 NCLOB**:</span><span class="sxs-lookup"><span data-stu-id="a1816-154">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 <span data-ttu-id="a1816-155">实体说明：</span><span class="sxs-lookup"><span data-stu-id="a1816-155">Entity descriptions:</span></span>  
  
 <span data-ttu-id="a1816-156">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="a1816-156">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="a1816-157">[TABLE_NAME] = 包含目标的 LOB 列; 的表例如，客户。</span><span class="sxs-lookup"><span data-stu-id="a1816-157">[TABLE_NAME] = The table that contains the targeted LOB column; for example, CUSTOMER.</span></span> <span data-ttu-id="a1816-158">(SCOTT。CUSTOMER 表是由安装这些示例中包含的 SQL 脚本。）</span><span class="sxs-lookup"><span data-stu-id="a1816-158">(The SCOTT.CUSTOMER table is installed by a SQL script included in the samples.)</span></span>  
  
 <span data-ttu-id="a1816-159">[LOBCol_Name] = LOB 列; 的名称例如，照片。</span><span class="sxs-lookup"><span data-stu-id="a1816-159">[LOBCol_Name] = The name of a LOB column; for example, Photo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1816-160">Read_ 的消息操作\<LOBColName\>和 Update_\<LOBColName\>视图上的操作类似于用于表，只是操作的操作指定了一个视图，而不是表： `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.</span><span class="sxs-lookup"><span data-stu-id="a1816-160">The message action for Read_\<LOBColName\> and Update_\<LOBColName\> operations on views is similar to that used for tables, except that action for the operation specifies a view rather than a table: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1816-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1816-161">See Also</span></span>  
 [<span data-ttu-id="a1816-162">用于 Oracle E-Business Suite 的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="a1816-162">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)