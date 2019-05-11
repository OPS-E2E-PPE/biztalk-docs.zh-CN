---
title: 消息架构的轮询 Operations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c572c4ec-0a3f-42b8-bebd-40eb584438ad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0475c94ef6838e02e4f81f27df7ee9b2df70bfc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375994"
---
# <a name="message-schemas-for-the-polling-operations"></a><span data-ttu-id="8d7db-102">轮询操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="8d7db-102">Message Schemas for the Polling Operations</span></span>
<span data-ttu-id="8d7db-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]轮询，具体取决于 Oracle E-business Suite 中的目标对象与相关的各种入站的操作的图面。</span><span class="sxs-lookup"><span data-stu-id="8d7db-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces various inbound operations related to polling depending on the target object in Oracle E-Business Suite.</span></span> <span data-ttu-id="8d7db-104">界面表、 界面视图、 表和视图，而可以具有的 PL/SQL Api、 函数和存储的过程的多个自定义轮询操作显示一次轮询操作。</span><span class="sxs-lookup"><span data-stu-id="8d7db-104">For interface tables, interface views, tables, and views, a single Poll operation is surfaced whereas you can have multiple custom polling operations for PL/SQL APIs, functions, and stored procedures.</span></span>  
  
 <span data-ttu-id="8d7db-105">通过设置绑定属性来配置轮询操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8d7db-105">You configure the polling operations by setting binding properties in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="8d7db-106">有关这些绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7db-106">For more information about these binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="8d7db-107">您设置**PollingStatement**绑定属性来指定 SQL 语句、 存储的过程、 函数或轮询查询的包中的过程。</span><span class="sxs-lookup"><span data-stu-id="8d7db-107">You set the **PollingStatement** binding property to specify a SQL statement, stored procedure, function or a procedure within a package for the polling query.</span></span> <span data-ttu-id="8d7db-108">此查询的结果集作为数据返回到轮询操作中的代码。</span><span class="sxs-lookup"><span data-stu-id="8d7db-108">The result set of this query is returned as data to your code in the polling operation.</span></span>  
  
## <a name="message-structure-for-the-polling-operations"></a><span data-ttu-id="8d7db-109">轮询操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="8d7db-109">Message Structure for the Polling Operations</span></span>  
 <span data-ttu-id="8d7db-110">下表显示了各种轮询操作的 XML 消息结构。</span><span class="sxs-lookup"><span data-stu-id="8d7db-110">The following table shows the XML message structure for the various polling operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d7db-111">实体说明表后进行查看。</span><span class="sxs-lookup"><span data-stu-id="8d7db-111">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="8d7db-112">操作</span><span class="sxs-lookup"><span data-stu-id="8d7db-112">Operation</span></span>|<span data-ttu-id="8d7db-113">目标对象</span><span class="sxs-lookup"><span data-stu-id="8d7db-113">Target Object</span></span>|<span data-ttu-id="8d7db-114">XML 消息</span><span class="sxs-lookup"><span data-stu-id="8d7db-114">XML Message</span></span>|<span data-ttu-id="8d7db-115">Description</span><span class="sxs-lookup"><span data-stu-id="8d7db-115">Description</span></span>|  
|---------------|-------------------|-----------------|-----------------|  
|<span data-ttu-id="8d7db-116">轮询</span><span class="sxs-lookup"><span data-stu-id="8d7db-116">Poll</span></span>|<span data-ttu-id="8d7db-117">-接口表</span><span class="sxs-lookup"><span data-stu-id="8d7db-117">- Interface Tables</span></span><br /><br /> <span data-ttu-id="8d7db-118">界面视图</span><span class="sxs-lookup"><span data-stu-id="8d7db-118">- Interface Views</span></span><br /><br /> <span data-ttu-id="8d7db-119">-表</span><span class="sxs-lookup"><span data-stu-id="8d7db-119">- Tables</span></span><br /><br /> <span data-ttu-id="8d7db-120">视图</span><span class="sxs-lookup"><span data-stu-id="8d7db-120">- Views</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|<span data-ttu-id="8d7db-121">例如，接口表上的轮询操作的 XML 消息将如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d7db-121">For example, the XML message for the Poll operation on Interface Tables will be as follows:</span></span><br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|<span data-ttu-id="8d7db-122">[CustomPollingOperation]</span><span class="sxs-lookup"><span data-stu-id="8d7db-122">[CustomPollingOperation]</span></span>|<span data-ttu-id="8d7db-123">-PL/SQL Api</span><span class="sxs-lookup"><span data-stu-id="8d7db-123">- PL/SQL APIs</span></span><br /><br /> <span data-ttu-id="8d7db-124">-存储过程</span><span class="sxs-lookup"><span data-stu-id="8d7db-124">- Stored Procedures</span></span><br /><br /> <span data-ttu-id="8d7db-125">-函数</span><span class="sxs-lookup"><span data-stu-id="8d7db-125">- Functions</span></span>|<span data-ttu-id="8d7db-126">**PL/SQL Api**</span><span class="sxs-lookup"><span data-stu-id="8d7db-126">**PL/SQL APIs**</span></span><br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> <span data-ttu-id="8d7db-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="8d7db-127">**Functions**</span></span><br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> <span data-ttu-id="8d7db-128">**存储过程**</span><span class="sxs-lookup"><span data-stu-id="8d7db-128">**Stored Procedures**</span></span><br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|<span data-ttu-id="8d7db-129">轮询操作中的结果集的结构取决于目标对象中的元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="8d7db-129">The structure of the result set in the polling operation is determined by the data type of the elements in the target object.</span></span>|  
  
 <span data-ttu-id="8d7db-130">实体说明：</span><span class="sxs-lookup"><span data-stu-id="8d7db-130">Entity descriptions:</span></span>  
  
 <span data-ttu-id="8d7db-131">[Version] = http://schemas.microsoft.com/OracleEBS/2008/05。</span><span class="sxs-lookup"><span data-stu-id="8d7db-131">[Version] = http://schemas.microsoft.com/OracleEBS/2008/05.</span></span>  
  
 <span data-ttu-id="8d7db-132">[CustomPollingOperation] = 自定义轮询操作的名称。</span><span class="sxs-lookup"><span data-stu-id="8d7db-132">[CustomPollingOperation] = Name of the custom polling operation.</span></span>  
  
 <span data-ttu-id="8d7db-133">[架构] = Oracle 架构的名称。</span><span class="sxs-lookup"><span data-stu-id="8d7db-133">[Schema] = Name of the Oracle schema.</span></span> <span data-ttu-id="8d7db-134">例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="8d7db-134">For example, SCOTT.</span></span>  
  
 <span data-ttu-id="8d7db-135">[PL/SQL API] = PL/SQL API 对其执行自定义轮询操作的名称。</span><span class="sxs-lookup"><span data-stu-id="8d7db-135">[PL/SQL API] = Name of the PL/SQL API on which a custom polling operation is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d7db-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d7db-136">See Also</span></span>  
 [<span data-ttu-id="8d7db-137">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="8d7db-137">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)