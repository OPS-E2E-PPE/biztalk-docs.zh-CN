---
title: "执行使用 EXECQUERY 命令 SAP 查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86159a03858ae5aa31bb37da56b6e5ea68dac3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a><span data-ttu-id="dfb69-102">执行 SAP 查询使用 EXECQUERY 命令</span><span class="sxs-lookup"><span data-stu-id="dfb69-102">Execute an SAP Query Using the EXECQUERY Command</span></span>
<span data-ttu-id="dfb69-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开与 ADO.NET 数据源 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="dfb69-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="dfb69-104">与[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，您可以通过执行 EXECQUERY 语句执行 SAP 系统中预定义的查询。</span><span class="sxs-lookup"><span data-stu-id="dfb69-104">With the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], you can execute pre-defined queries in the SAP system by executing an EXECQUERY statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a><span data-ttu-id="dfb69-105">如何使用 EXECQUERY 命令执行查询</span><span class="sxs-lookup"><span data-stu-id="dfb69-105">How to Perform a Query by Using the EXECQUERY Command</span></span>  
 <span data-ttu-id="dfb69-106">若要执行预定义的 SAP 查询使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dfb69-106">To execute pre-defined SAP queries using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="dfb69-107">执行查询</span><span class="sxs-lookup"><span data-stu-id="dfb69-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="dfb69-108">包含的引用 (和使用程序代码中的语句) 到**Microsoft.Data.SAPClient**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="dfb69-109">创建**SAPConnection** SAP 连接字符串中使用数据访问接口的对象。</span><span class="sxs-lookup"><span data-stu-id="dfb69-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="dfb69-110">有关连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb69-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="dfb69-111">打开与 SAP 系统的连接通过调用**打开**上**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="dfb69-112">创建**SAPCommand**对象**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="dfb69-113">指定在 EXECQUERY 语句**CommandText**属性**SAPCommand**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-113">Specify the EXECQUERY statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="dfb69-114">如果有必要，你可以指定参数使用**SAPParameter**对象。</span><span class="sxs-lookup"><span data-stu-id="dfb69-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="dfb69-115">有关如何执行在使用 EXECQUERY 语句 SAP 系统中定义的查询的详细信息，请参阅[SAP 中 EXECQUERY 语句语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb69-115">For more information about how to execute queries defined in an SAP system using an EXECQUERY statement, see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
6.  <span data-ttu-id="dfb69-116">执行命令来执行查询并获取中的结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-116">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="dfb69-117">读取从结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-117">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="dfb69-118">在完成使用它们，请关闭 （或释放） **SAPConnection**和**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="dfb69-118">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="dfb69-119">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。</span><span class="sxs-lookup"><span data-stu-id="dfb69-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="dfb69-120">有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 适配器具有扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb69-120">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb69-121">示例</span><span class="sxs-lookup"><span data-stu-id="dfb69-121">Example</span></span>  
 <span data-ttu-id="dfb69-122">下面的示例将查询，ZTEST1 的结果写入控制台。</span><span class="sxs-lookup"><span data-stu-id="dfb69-122">The following example writes the results of a query, ZTEST1, to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExecQuery  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
           string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "EXECQUERY ZTEST1 @userGRoup='SYSTQV000024',@P1='0000001390',@P2='0000080150'";  
                    cmd.Parameters.Add(new SAPParameter("@connid", 17));                      
                    using (SAPDataReader dr = cmd.ExecuteReader())  
                    {  
                        do  
                        {  
                            int rows = 0;  
                            while (dr.Read())  
                            {  
                                rows++;  
                                StringBuilder b = new StringBuilder();  
                                for (int i = 0; i < dr.FieldCount; i++)  
                                {  
                                    b.Append(dr[i].ToString()+" ");  
                                }  
                                Console.WriteLine("row {0}: {1} ", rows, b.ToString());  
                            }  
                            Console.WriteLine("Number of rows:{0}", rows);  
                        } while (dr.NextResult());  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfb69-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfb69-123">See Also</span></span>  
 [<span data-ttu-id="dfb69-124">使用.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="dfb69-124">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [<span data-ttu-id="dfb69-125">示例</span><span class="sxs-lookup"><span data-stu-id="dfb69-125">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)