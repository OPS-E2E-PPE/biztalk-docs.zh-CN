---
title: 完成对表使用 WCF 服务模型的 Oracle 数据库中的较大的数据类型的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on tables and views
- how to, invoke the ReadLOB and UpdateLOB operations
ms.assetid: 5d0e84d3-7ffa-47c7-aaf2-a1007f7a71a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ae5a616e71e27a4d6fa8cd27473665f7bc96b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215605"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="cb9f3-102">完成对表使用 WCF 服务模型的 Oracle 数据库中的较大的数据类型的操作</span><span class="sxs-lookup"><span data-stu-id="cb9f3-102">Complete operations on tables with large data types in Oracle Database using the WCF service model</span></span>
<span data-ttu-id="cb9f3-103">本部分包含有关如何以调用 WCF 服务模型中的 ReadLOB 和 UpdateLOB 操作的信息。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-103">This section contains information about how to invoke the ReadLOB and UpdateLOB operations from the WCF service model.</span></span> <span data-ttu-id="cb9f3-104">表和视图包含 LOB 列; 中加以表示的 ReadLOB 和 UpdateLOB 操作这就是用于存储 Oracle 大型对象 (LOB) 数据的列。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-104">The ReadLOB and UpdateLOB operations are surfaced for tables and views that contain LOB columns; that is columns that are used to store Oracle large object (LOB) data.</span></span> <span data-ttu-id="cb9f3-105">有关支持的 Oracle LOB 数据类型的概述[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和 ReadLOB 和 UpdateLOB 操作，请参阅[对表和视图，包含 LOB 数据 Oracle 数据库中的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-105">For an overview of the Oracle LOB data types supported by the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and of the ReadLOB and UpdateLOB operations, see [Operations on Tables and Views That Contain LOB Data in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb9f3-106">LOB 数据列可以包含大量的数据-最多 4 千兆字节 (GB)。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-106">LOB data columns can contain large amounts of data—up to 4 gigabytes (GB).</span></span> <span data-ttu-id="cb9f3-107">使用 WCF 客户端以操作的 LOB 列的一个明显的限制是 WCF 服务模型仅支持 UpdateLOB 操作 ReadLOB 操作流式处理的数据。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-107">A significant limitation of using a WCF client to operate on LOB columns is that the WCF service model only supports data streaming on the ReadLOB operation, not on the UpdateLOB operation.</span></span> <span data-ttu-id="cb9f3-108">这是因为 WCF 要求进行流式处理从服务模型，要进行流处理的参数必须是其方向中的唯一参数。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-108">This is because WCF requires that for streaming to work from service model, the parameter to be streamed must be the only parameter in its direction.</span></span> <span data-ttu-id="cb9f3-109">UpdateLOB 操作具有两个其他 IN 参数 （列名称和行筛选器） 除了 LOB 数据中;为此，流式处理不支持对其在 WCF 服务模型中。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-109">The UpdateLOB operation has two other IN parameters (a column name and row filter) in addition to the LOB data; for this reason, streaming is not supported on it in the WCF service model.</span></span> <span data-ttu-id="cb9f3-110">因此，如果你使用大量的数据进行更新 LOB 列，则你可能想要使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-110">Therefore, if you are updating a LOB column with a large amount of data, you might want to use the WCF channel model.</span></span> <span data-ttu-id="cb9f3-111">有关如何使用 WCF 通道模型进行流式处理使用 UpdateLOB 操作的 LOB 数据的详细信息，请参阅[流式处理 Oracle LOB 数据类型使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-111">For more information on how to use the WCF channel model to stream LOB data using the UpdateLOB operation, see [Streaming Oracle LOB Data Types by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="cb9f3-112">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="cb9f3-112">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="cb9f3-113">本主题中的示例使用 /SCOTT/CUSTOMER 表。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-113">The examples in this topic use the /SCOTT/CUSTOMER table.</span></span> <span data-ttu-id="cb9f3-114">此表包含一个名为照片的 BLOB 列。使用 SDK 示例提供了一个脚本来生成此表。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-114">This table contains a BLOB column named PHOTO.A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="cb9f3-115">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-115">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="cb9f3-116">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="cb9f3-116">The WCF Client Class</span></span>  
 <span data-ttu-id="cb9f3-117">下面的示例演示上 /SCOTT/CUSTOMER 表的 ReadLOB 和 UpdateLOB 操作生成的 WCF 客户端类的方法签名。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-117">The following example shows the method signatures for a WCF client class generated for the ReadLOB and UpdateLOB operations on the /SCOTT/CUSTOMER table.</span></span>  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="cb9f3-118">请注意， **ReadLOB**返回数据流，但**UpdateLOB**不对进行操作流。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-118">Note that **ReadLOB** returns a data stream, but that **UpdateLOB** does not operate on a stream.</span></span>  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a><span data-ttu-id="cb9f3-119">调用 ReadLOB 和 UpdateLOB 操作</span><span class="sxs-lookup"><span data-stu-id="cb9f3-119">Invoking the ReadLOB and UpdateLOB Operations</span></span>  
 <span data-ttu-id="cb9f3-120">这两个**ReadLOB**和**UpdateLOB**方法可以仅应用于单个数据库行中的单个 LOB 列。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-120">Both the **ReadLOB** and **UpdateLOB** methods can operate only on a single LOB column in a single database row.</span></span> <span data-ttu-id="cb9f3-121">设置以下参数来标识目标列。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-121">You set the following parameters to identify the target column/row.</span></span>  
  
|<span data-ttu-id="cb9f3-122">参数</span><span class="sxs-lookup"><span data-stu-id="cb9f3-122">Parameter</span></span>|<span data-ttu-id="cb9f3-123">定义</span><span class="sxs-lookup"><span data-stu-id="cb9f3-123">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="cb9f3-124">LOB_COLUMN</span><span class="sxs-lookup"><span data-stu-id="cb9f3-124">LOB_COLUMN</span></span>|<span data-ttu-id="cb9f3-125">标识由筛选器参数; 行中的目标列的名称例如，"照片"。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-125">The name of the target column within the row identified by the FILTER parameter; for example, "PHOTO".</span></span>|  
|<span data-ttu-id="cb9f3-126">FILTER</span><span class="sxs-lookup"><span data-stu-id="cb9f3-126">FILTER</span></span>|<span data-ttu-id="cb9f3-127">SQL SELECT 语句的 WHERE 子句，指定目标行中; 的内容例如，"名称 = 李杰"。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-127">The contents of a SQL SELECT statement WHERE clause that specifies the target row; for example, "NAME='Kim Ralls'".</span></span> <span data-ttu-id="cb9f3-128">筛选器必须指定一个且只有一个行。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-128">The filter must specify one and only one row.</span></span> <span data-ttu-id="cb9f3-129">如果在筛选器匹配多个行：</span><span class="sxs-lookup"><span data-stu-id="cb9f3-129">If the filter matches more than one row:</span></span><br /><br /> <span data-ttu-id="cb9f3-130">-   **ReadLOB**返回第一个匹配行的 LOB 数据。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-130">-   **ReadLOB** returns LOB data for the first matching row.</span></span><br /><span data-ttu-id="cb9f3-131">-   **UpdateLOB**引发异常。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-131">-   **UpdateLOB** throws an exception.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cb9f3-132">返回的流**ReadLOB**不支持**Seek**。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-132">The stream returned by **ReadLOB** does not support **Seek**.</span></span> <span data-ttu-id="cb9f3-133">这意味着，属性，如**长度**不支持，要么。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-133">This means that properties such as **Length** are not supported, either.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cb9f3-134">**UpdateLOB**必须在事务范围内执行操作。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-134">The **UpdateLOB** operation must be performed within a transaction scope.</span></span> <span data-ttu-id="cb9f3-135">此外， **UseAmbientTransaction**绑定属性必须设置为**true**之前执行**UpdateLOB**操作。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-135">Also, the **UseAmbientTransaction** binding property must be set to **true** before performing the **UpdateLOB** operation.</span></span>  
  
 <span data-ttu-id="cb9f3-136">下面的代码演示如何使用 WCF 客户端来更新 BLOB 照片表的列中 /SCOTT/CUSTOMER 从文件和读取新的列数据保存到文件。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-136">The following code shows how to use a WCF client to update the BLOB PHOTO column in the /SCOTT/CUSTOMER table from a file and read the new column data back to a file.</span></span> <span data-ttu-id="cb9f3-137">SDK 示例中，可以找到完整的示例。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-137">You can find a full sample in the SDK samples.</span></span> <span data-ttu-id="cb9f3-138">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="cb9f3-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Transaction;  
  
// Include for file streaming  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for the WCF channel model  
using System.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using CustomerTablens = microsoft.lobservices.oracledb._2007._03;  
  
namespace OracleLobOpsSnippetSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.UseAmbientTransaction = true; //set this to true for UpdateLOB operation  
  
                EndpointAddress endpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
  
                using (SCOTTTableCUSTOMERClient customerTableClient =  
                    new SCOTTTableCUSTOMERClient(binding, endpointAddress))  
                {  
                    customerTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    customerTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    // Open the client to read the LOB data back  
                    customerTableClient.Open();  
  
                    // Add a photo to the customer record    
                    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
                    {  
                        Console.WriteLine("Updating photo");  
                        int count = 0;  
                        byte[] photo = new byte[fs.Length];  
                        while ((count += fs.Read(photo, count, (int) (((fs.Length-count)>4096)? 4096:fs.Length-count))) \< fs.Length) ;  
  
                        // UpdateLOB operation must be performed within a transaction scope  
                        using(TransactionScope tx = new TransactionScope())  
                        {  
                           customerTableClient.UpdateLOB("PHOTO", "NAME='Kim Ralls'", photo);  
                           Console.WriteLine("Photo updated");  
                           tx.Complete();  
                        }  
                    }  
  
                    // Read the data back and store it to another file  
                    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
                    {  
                        Console.WriteLine("Reading photo data");  
                        Stream photoStream = customerTableClient.ReadLOB("PHOTO", "NAME='Kim Ralls'");  
                        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
                        int count;  
                        int length = 0;  
                        byte[] buffer = new byte[4096];  
                        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
                        {  
                            fs.Write(buffer, 0, count);  
                            length+=count;  
                        }  
                        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
                    }  
  
                }  
  
                Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (Exception ex)  
            {  
                // handle exception  
                Console.WriteLine("Exception caught: " + ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb9f3-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb9f3-139">See Also</span></span>  
 [<span data-ttu-id="cb9f3-140">开发 Oracle 数据库应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="cb9f3-140">Develop Oracle Database Applications Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)