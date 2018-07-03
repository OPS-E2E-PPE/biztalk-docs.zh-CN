---
title: 对界面表、 界面视图、 表和包含 LOB 数据的视图的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f1336c1d6f5fb6ea7c0b68e4c7670616f141583
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967686"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a><span data-ttu-id="a89e0-102">对界面表、 界面视图、 表和包含 LOB 数据的视图的操作</span><span class="sxs-lookup"><span data-stu-id="a89e0-102">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>
<span data-ttu-id="a89e0-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]对 Oracle 大型对象 (LOB) 数据类型提供支持：</span><span class="sxs-lookup"><span data-stu-id="a89e0-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
- <span data-ttu-id="a89e0-104">二进制大型对象 (BLOB)</span><span class="sxs-lookup"><span data-stu-id="a89e0-104">Binary large object (BLOB)</span></span>  
  
- <span data-ttu-id="a89e0-105">字符大型对象 (CLOB)</span><span class="sxs-lookup"><span data-stu-id="a89e0-105">Character large object (CLOB)</span></span>  
  
- <span data-ttu-id="a89e0-106">国家/地区字符大型对象 (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="a89e0-106">National character large object (NCLOB)</span></span>  
  
- <span data-ttu-id="a89e0-107">二进制文件 (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-107">Binary file (BFILE).</span></span> <span data-ttu-id="a89e0-108">有关详细信息，请参阅[表，包含 BFILE 数据类型操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-108">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
  <span data-ttu-id="a89e0-109">LOB 数据类型用于存储大量数据，在基础的 Oracle 数据库中，最多 4 千兆字节 (GB)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-109">In the underlying Oracle database, LOB data types are used to store large amounts of data, up to 4 gigabytes (GB).</span></span> <span data-ttu-id="a89e0-110">BFILE 数据类型，除了 LOB 数据类型支持输入和输出流。</span><span class="sxs-lookup"><span data-stu-id="a89e0-110">Except for the BFILE data type, LOB data types support both input and output streaming.</span></span>  

## <a name="operations-for-tables-and-views"></a><span data-ttu-id="a89e0-111">用于表和视图的操作</span><span class="sxs-lookup"><span data-stu-id="a89e0-111">Operations for tables and views</span></span>  
 <span data-ttu-id="a89e0-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示接口表、 界面视图、 表和包含 LOB 列的视图的以下操作：</span><span class="sxs-lookup"><span data-stu-id="a89e0-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces the following operations for interface tables, interface views, tables and views that contain LOB columns:</span></span>  
  
- <span data-ttu-id="a89e0-113">**Read_\<LOBColName\>**:`Read_<LOBColName>`操作提供的接口表、 界面视图、 表和视图包含 BLOB、 CLOB、 NCLOB、 和 BFILE 列，其中\<LOBColName\>是类型为 BLOB、 CLOB、 NCLOB 或 BFILE 列的名称。</span><span class="sxs-lookup"><span data-stu-id="a89e0-113">**Read_\<LOBColName\>**: The `Read_<LOBColName>` operation is surfaced for interface tables, interface views, tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns, where \<LOBColName\> is the name of the column of type BLOB, CLOB, NCLOB or BFILE.</span></span> <span data-ttu-id="a89e0-114">通过使用 Read_\<LOBColName\>操作，适配器客户端可以读取数据流形式的 LOB 列中的值。</span><span class="sxs-lookup"><span data-stu-id="a89e0-114">By using the Read_\<LOBColName\> operation, adapter clients can read values in an LOB column as a data stream.</span></span> <span data-ttu-id="a89e0-115">此操作将作为参数的筛选器字符串。</span><span class="sxs-lookup"><span data-stu-id="a89e0-115">This operation takes a filter string as parameter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="a89e0-116">`Read_<LOBColName>`操作设计为支持的 WCF 服务模型中的 LOB 数据的输入流。</span><span class="sxs-lookup"><span data-stu-id="a89e0-116">The `Read_<LOBColName>` operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="a89e0-117">应使用的表选择操作来读取 WCF 通道模型中的 LOB 数据或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="a89e0-117">You should use a table Select operation to read LOB data from a WCF channel model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="a89e0-118">**Update_\<LOBColName\>**:`Update_<LOBColName>`操作提供的接口表和表仅包含 BLOB 和 CLOB、 NCLOB 列，其中\<LOBColName\>的名称列的类型 BLOB、 CLOB、 和 NCLOB。</span><span class="sxs-lookup"><span data-stu-id="a89e0-118">**Update_\<LOBColName\>**: The `Update_<LOBColName>` operation is surfaced for interface tables and tables only that contain BLOB, CLOB, and NCLOB columns, where \<LOBColName\> is the name of the column of type BLOB, CLOB, and NCLOB.</span></span> <span data-ttu-id="a89e0-119">通过使用 Update_\<LOBColName\>操作，适配器客户端可以更新 LOB 列中的值。</span><span class="sxs-lookup"><span data-stu-id="a89e0-119">By using the Update_\<LOBColName\> operation, adapter clients can update values in an LOB column.</span></span> <span data-ttu-id="a89e0-120">对于 BLOB 数据类型，此操作将 base64binary 编码数据作为参数，而对于 CLOB 和 NCLOB 数据类型，此操作需要字符串筛选器作为参数。</span><span class="sxs-lookup"><span data-stu-id="a89e0-120">For the BLOB data type, this operation takes base64binary encoded data as the parameter, whereas for the CLOB and NCLOB data types, this operation takes a string filter as the parameter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="a89e0-121">`Update_<LOBColName>`操作：</span><span class="sxs-lookup"><span data-stu-id="a89e0-121">The `Update_<LOBColName>` operation:</span></span>  
  > 
  > - <span data-ttu-id="a89e0-122">BFILE 数据类型不支持。</span><span class="sxs-lookup"><span data-stu-id="a89e0-122">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="a89e0-123">适配器客户端或者可以使用更新操作。</span><span class="sxs-lookup"><span data-stu-id="a89e0-123">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="a89e0-124">有关详细信息，请参阅[表，包含 BFILE 数据类型操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-124">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  >   -   <span data-ttu-id="a89e0-125">不公开的接口视图和视图。</span><span class="sxs-lookup"><span data-stu-id="a89e0-125">Is not exposed for interface views and views.</span></span>  
  >   -   <span data-ttu-id="a89e0-126">必须为事务的一部分执行。</span><span class="sxs-lookup"><span data-stu-id="a89e0-126">Must be performed as part of a transaction.</span></span> <span data-ttu-id="a89e0-127">若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a89e0-127">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="a89e0-128">璝惠**UseAmbientTransaction**绑定属性，请参阅[Rad 有关用于 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-128">For information about the **UseAmbientTransaction** binding property, see [Rad about the  BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a89e0-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]图面`Read_<LOBColName>`和`Update_<LOBColName>`表中每个 LOB 列的操作。</span><span class="sxs-lookup"><span data-stu-id="a89e0-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces a `Read_<LOBColName>` and an `Update_<LOBColName>` operation for each LOB column in a table.</span></span> <span data-ttu-id="a89e0-130">因此，如果表 （LOBCol1 和 LOBCol2） 中有两个 LOB 列，则有两个`Read_<LOBColName>`操作 （Read_LOBCol1 和 Read_LOBCol2） 和两个`Update_<LOBColName>`操作 （Update_LOBCol1 和 Update_LOBCol2）。</span><span class="sxs-lookup"><span data-stu-id="a89e0-130">So, if there are two LOB columns in a table (LOBCol1 and LOBCol2), you have two `Read_<LOBColName>` operations (Read_LOBCol1 and Read_LOBCol2) and two `Update_<LOBColName>` operations (Update_LOBCol1 and Update_LOBCol2).</span></span>  
  
## <a name="more-good-info"></a><span data-ttu-id="a89e0-131">更多有用信息</span><span class="sxs-lookup"><span data-stu-id="a89e0-131">More good info</span></span>  
  
- <span data-ttu-id="a89e0-132">调用`Read_<LOBColName>`并`Update_<LOBColName>`基础数据库中使用 Oracle E-business Suite 中的表操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[表与大型数据类型使用 BizTalk Server 上运行操作](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-132">Invoking the `Read_<LOBColName>` and `Update_<LOBColName>` operations on a table in the underlying database in Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Operations on Tables with Large Data Types Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="a89e0-133">消息结构和 SOAP 操作的执行`Read_<LOBColName>`并`Update_<LOBColName>`操作，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)。</span><span class="sxs-lookup"><span data-stu-id="a89e0-133">Message structure and SOAP actions for performing `Read_<LOBColName>` and `Update_<LOBColName>` operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89e0-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a89e0-134">See Also</span></span>  
 <span data-ttu-id="a89e0-135">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a89e0-135">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>