---
title: 完成对表使用 WCF 服务模型的 Oracle 数据库中的大型数据类型的操作 |Microsoft Docs
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
ms.openlocfilehash: 7af4542dae7dc2370058dfc715d455ec571f776e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528933"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-database-using-the-wcf-service-model"></a>完成对表使用 WCF 服务模型的 Oracle 数据库中的大型数据类型的操作
本部分包含有关如何调用 WCF 服务模型从 ReadLOB 和 UpdateLOB 操作的信息。 ReadLOB 和 UpdateLOB 操作提供的表和视图包含 LOB 列;这是用于存储 Oracle 大型对象 (LOB) 数据的列。 有关支持的 Oracle LOB 数据类型的概述[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和 ReadLOB 和 UpdateLOB 操作，请参阅[对表和视图，包含 LOB 数据在 Oracle 数据库中操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)。  
  
> [!IMPORTANT]
>  LOB 数据列可以包含大量数据，最多 4 千兆字节 (GB)。 使用 WCF 客户端对 LOB 列的一个明显的限制是 WCF 服务模型仅支持 UpdateLOB 操作 ReadLOB 操作流式处理的数据。 这是因为 WCF 需要，对于流式处理从服务模型的操作，要进行流处理的参数必须是其方向中的唯一参数。 UpdateLOB 操作有两个其他 IN 参数 （列名称和行筛选器） 除了 LOB 数据;出于此原因，流式处理不支持对其在 WCF 服务模型中。 因此，如果您正在更新 LOB 列包含大量的数据，你可能想要使用的 WCF 通道模型。 有关如何使用 WCF 通道模型进行流式处理使用 UpdateLOB 操作的 LOB 数据的详细信息，请参阅[流式处理 Oracle LOB 数据类型使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例使用 /SCOTT/CUSTOMER 表。 此表包含一个名为照片的 BLOB 列。使用 SDK 示例提供了一个脚本来生成此表。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 下面的示例演示对 /SCOTT/CUSTOMER 表的 ReadLOB 和 UpdateLOB 操作生成的 WCF 客户端类的方法签名。  
  
```  
public partial class SCOTTTableCUSTOMERClient : System.ServiceModel.ClientBase<SCOTTTableCUSTOMER>,   
                                                SCOTTTableCUSTOMER   
{  
    public System.IO.Stream ReadLOB(string LOB_COLUMN, string FILTER);   
  
    public void UpdateLOB(string LOB_COLUMN, string FILTER, byte[] Stream);  
}  
```  
  
> [!NOTE]
>  请注意， **ReadLOB**返回数据流，但这**UpdateLOB**不能运行在流上。  
  
## <a name="invoking-the-readlob-and-updatelob-operations"></a>调用 ReadLOB 和 UpdateLOB 操作  
 这两个**ReadLOB**并**UpdateLOB**方法只能对单个数据库行中的单个 LOB 列进行操作。 设置以下参数来标识目标列/行。  
  
|参数|定义|  
|---------------|----------------|  
|LOB_COLUMN|标识由筛选器参数; 在行中的目标列的名称例如，"照片"。|  
|FILTER|SQL SELECT 语句的 WHERE 子句，指定目标行; 的内容例如，"名称 = Kim Ralls'"。 筛选器必须指定一个且只有一个行。 如果在筛选器匹配多个行：<br /><br /> -   **ReadLOB**返回 LOB 数据的第一个匹配行。<br />-   **UpdateLOB**将引发异常。|  
  
> [!NOTE]
>  返回的流**ReadLOB**不支持**Seek**。 这意味着，属性，如**长度**不支持，要么。  
  
> [!CAUTION]
>  **UpdateLOB**必须在事务范围内执行操作。 此外， **UseAmbientTransaction**绑定属性必须设置为**true**才能执行**UpdateLOB**操作。  
  
 以下代码演示如何使用 WCF 客户端来更新 BLOB PHOTO 列 /SCOTT/CUSTOMER 表从一个文件中的和读取新的列数据保存到文件。 SDK 示例中，可以找到完整示例。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
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
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)