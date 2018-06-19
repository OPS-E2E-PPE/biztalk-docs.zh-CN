---
title: 在 SAP 中使用 SELECT 命令运行查询 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT command, performing a query
- query, performing by using the SELECT command
ms.assetid: 6f03243c-ef50-4a4a-8fe6-4e525bd7efe3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e03ac093e0fb7b2b8f95d770661bd702d988f01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217797"
---
# <a name="run-a-query-using-the-select-command-in-sap"></a><span data-ttu-id="4af78-102">在 SAP 中使用 SELECT 命令运行查询</span><span class="sxs-lookup"><span data-stu-id="4af78-102">Run a Query Using the SELECT Command in SAP</span></span>
<span data-ttu-id="4af78-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开与 ADO.NET 数据源 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="4af78-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="4af78-104">与[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，你可以通过执行 SELECT 语句查询的 SAP 项目。</span><span class="sxs-lookup"><span data-stu-id="4af78-104">With the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can query SAP artifacts by executing a SELECT statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-select-command"></a><span data-ttu-id="4af78-105">如何通过使用 SELECT 命令执行查询</span><span class="sxs-lookup"><span data-stu-id="4af78-105">How to Perform a Query by Using the SELECT Command</span></span>  
 <span data-ttu-id="4af78-106">对查询使用的 SAP 项目[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4af78-106">To query SAP artifacts using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="4af78-107">执行查询</span><span class="sxs-lookup"><span data-stu-id="4af78-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="4af78-108">包含的引用 (和使用程序代码中的语句) 到**Microsoft.Data.SAPClient**。</span><span class="sxs-lookup"><span data-stu-id="4af78-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="4af78-109">创建**SAPConnection** SAP 连接字符串中使用数据访问接口的对象。</span><span class="sxs-lookup"><span data-stu-id="4af78-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="4af78-110">有关连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="4af78-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="4af78-111">打开与 SAP 系统的连接通过调用**打开**上**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="4af78-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="4af78-112">创建**SAPCommand**对象**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="4af78-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="4af78-113">指定中的 SELECT 语句**CommandText**属性**SAPCommand**。</span><span class="sxs-lookup"><span data-stu-id="4af78-113">Specify the SELECT statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="4af78-114">如果有必要，你可以指定参数使用**SAPParameter**对象。</span><span class="sxs-lookup"><span data-stu-id="4af78-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="4af78-115">有关如何查询使用 SELECT 语句的 SAP 项目的详细信息，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="4af78-115">For more information about how to query SAP artifacts using a SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="4af78-116">有关如何指定 BAPI 或 RFC 的示例，请参阅[SELECT 语句示例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4af78-116">For examples of how to specify a BAPI or RFC, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
6.  <span data-ttu-id="4af78-117">执行命令来执行查询并获取中的结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="4af78-117">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="4af78-118">读取从结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="4af78-118">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="4af78-119">在完成使用它们，请关闭 （或释放） **SAPConnection**和**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="4af78-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="4af78-120">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。</span><span class="sxs-lookup"><span data-stu-id="4af78-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="4af78-121">有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 适配器具有扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4af78-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af78-122">示例</span><span class="sxs-lookup"><span data-stu-id="4af78-122">Example</span></span>  
 <span data-ttu-id="4af78-123">下面的示例将选择的结果写入到控制台的参数化的内部联接语句上。</span><span class="sxs-lookup"><span data-stu-id="4af78-123">The following example writes the results of a select on a parameterized inner join statement to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoSelect  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        /// <summary>  
        /// select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid  
        /// </summary>  
  
        string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid";  
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
  
## <a name="see-also"></a><span data-ttu-id="4af78-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4af78-124">See Also</span></span>  
 <span data-ttu-id="4af78-125">[使用.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="4af78-125">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="4af78-126">示例</span><span class="sxs-lookup"><span data-stu-id="4af78-126">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)