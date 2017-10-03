---
title: "调用 Rfc 和在 SAP 中使用 EXEC 命令的 BAPIs |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500e0f932a8245f76954aa7a8785dbec012321e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a><span data-ttu-id="fe736-102">调用 Rfc 和 BAPIs 在 SAP 中使用 EXEC 命令</span><span class="sxs-lookup"><span data-stu-id="fe736-102">Invoke RFCs and BAPIs using the EXEC Command in SAP</span></span>
<span data-ttu-id="fe736-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开与 ADO.NET 数据源 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="fe736-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="fe736-104">通过使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，你可以调用 Rfc 和 BAPIs EXEC 命令通过 SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="fe736-104">By using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can invoke RFCs and BAPIs on the SAP system through an EXEC command.</span></span>  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a><span data-ttu-id="fe736-105">如何在 SAP 系统上调用 Rfc 和 BAPIs</span><span class="sxs-lookup"><span data-stu-id="fe736-105">How to Invoke RFCs and BAPIs on the SAP system</span></span>  
 <span data-ttu-id="fe736-106">若要调用 RFC 或 BAPI 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fe736-106">To invoke an RFC or BAPI using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a><span data-ttu-id="fe736-107">若要调用的 RFC 或 BAPI</span><span class="sxs-lookup"><span data-stu-id="fe736-107">To invoke an RFC or BAPI</span></span>  
  
1.  <span data-ttu-id="fe736-108">包含的引用 (和使用程序代码中的语句) 到**Microsoft.Data.SAPClient**。</span><span class="sxs-lookup"><span data-stu-id="fe736-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="fe736-109">创建**SAPConnection** SAP 连接字符串中使用数据访问接口的对象。</span><span class="sxs-lookup"><span data-stu-id="fe736-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="fe736-110">有关连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="fe736-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="fe736-111">打开与 SAP 系统的连接通过调用**打开**上**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="fe736-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="fe736-112">创建**SAPCommand**对象**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="fe736-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="fe736-113">指定中的 BAPI 或 RFC 调用**CommandText**属性**SAPCommand**。</span><span class="sxs-lookup"><span data-stu-id="fe736-113">Specify the BAPI or RFC call in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="fe736-114">如果有必要，你可以指定参数使用**SAPParameter**对象。</span><span class="sxs-lookup"><span data-stu-id="fe736-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="fe736-115">有关如何指定 BAPI 或 RFC 调用使用 EXEC 语句的详细信息，请参阅[中 SAP 的 EXEC 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="fe736-115">For more information about how to specify a BAPI or RFC call using an EXEC statement, see [Syntax for an EXEC Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).</span></span> <span data-ttu-id="fe736-116">有关如何指定 BAPI 或 RFC 的示例，请参阅[EXEC 语句的示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="fe736-116">For examples of how to specify a BAPI or RFC, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
6.  <span data-ttu-id="fe736-117">执行命令以调用 RFC 或 BAPI 并获得的结果中**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="fe736-117">Execute the command to invoke the RFC or BAPI and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="fe736-118">读取从结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="fe736-118">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="fe736-119">在完成使用它们，请关闭 （或释放） **SAPConnection**和**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="fe736-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="fe736-120">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。</span><span class="sxs-lookup"><span data-stu-id="fe736-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="fe736-121">有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 适配器具有扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fe736-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe736-122">示例</span><span class="sxs-lookup"><span data-stu-id="fe736-122">Example</span></span>  
 <span data-ttu-id="fe736-123">下面的示例调用 SD_RFC_CUSTOMER_GET 要检索其名称以"AB"开头的所有客户的客户信息。</span><span class="sxs-lookup"><span data-stu-id="fe736-123">The following example invokes SD_RFC_CUSTOMER_GET to retrieve customer information for all customers whose names start with "AB".</span></span> <span data-ttu-id="fe736-124">它然后客户将记录写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="fe736-124">It then writes the customer records to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExec  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string connstr = "TYPE=A; ASHOST=YourSAPHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
            using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "exec sd_rfc_customer_get @name1='AB*' ";  
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
                                    b.Append(dr[i].ToString() + " ");  
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
  
## <a name="see-also"></a><span data-ttu-id="fe736-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe736-125">See Also</span></span>  
 <span data-ttu-id="fe736-126">[使用.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="fe736-126">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="fe736-127">示例</span><span class="sxs-lookup"><span data-stu-id="fe736-127">Samples</span></span>](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)