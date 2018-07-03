---
title: 调用 Rfc 和 Bapi 在 SAP 中使用 EXEC 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7ddd9e4d3e7d4c4d34445c7a42d83262d04f4b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988190"
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a><span data-ttu-id="00b93-102">调用 Rfc 和 Bapi 在 SAP 中使用 EXEC 命令</span><span class="sxs-lookup"><span data-stu-id="00b93-102">Invoke RFCs and BAPIs using the EXEC Command in SAP</span></span>
<span data-ttu-id="00b93-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开为 ADO.NET 数据源的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="00b93-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="00b93-104">通过使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，可以在 SAP 系统通过 EXEC 命令调用 Rfc 和 Bapi。</span><span class="sxs-lookup"><span data-stu-id="00b93-104">By using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can invoke RFCs and BAPIs on the SAP system through an EXEC command.</span></span>  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a><span data-ttu-id="00b93-105">如何在 SAP 系统上调用 Rfc 和 Bapi</span><span class="sxs-lookup"><span data-stu-id="00b93-105">How to Invoke RFCs and BAPIs on the SAP system</span></span>  
 <span data-ttu-id="00b93-106">若要调用 RFC 或 BAPI 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="00b93-106">To invoke an RFC or BAPI using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a><span data-ttu-id="00b93-107">用于调用 RFC 或 BAPI</span><span class="sxs-lookup"><span data-stu-id="00b93-107">To invoke an RFC or BAPI</span></span>  
  
1. <span data-ttu-id="00b93-108">包含的引用 (和在代码中使用语句) 到**Microsoft.Data.SAPClient**。</span><span class="sxs-lookup"><span data-stu-id="00b93-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2. <span data-ttu-id="00b93-109">创建**SAPConnection**通过数据提供程序用于 SAP 连接字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="00b93-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="00b93-110">有关连接字符串的详细信息，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="00b93-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3. <span data-ttu-id="00b93-111">打开与 SAP 系统的连接通过调用**开放**上**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="00b93-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4. <span data-ttu-id="00b93-112">创建**SAPCommand**对象从**SAPConnection**。</span><span class="sxs-lookup"><span data-stu-id="00b93-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5. <span data-ttu-id="00b93-113">指定中的 BAPI 或 RFC 调用**CommandText**的属性**SAPCommand**。</span><span class="sxs-lookup"><span data-stu-id="00b93-113">Specify the BAPI or RFC call in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="00b93-114">如果有必要，您可以使用指定参数**SAPParameter**对象。</span><span class="sxs-lookup"><span data-stu-id="00b93-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="00b93-115">有关如何指定使用 EXEC 语句的 BAPI 或 RFC 调用的详细信息，请参阅[EXEC 语句在 SAP 中的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="00b93-115">For more information about how to specify a BAPI or RFC call using an EXEC statement, see [Syntax for an EXEC Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).</span></span> <span data-ttu-id="00b93-116">有关如何指定 RFC 或 BAPI 的示例，请参阅[EXEC 语句示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="00b93-116">For examples of how to specify a BAPI or RFC, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
6. <span data-ttu-id="00b93-117">执行命令，以调用 RFC 或 BAPI 和获取中的结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="00b93-117">Execute the command to invoke the RFC or BAPI and obtain the results in a **SAPDataReader**.</span></span>  
  
7. <span data-ttu-id="00b93-118">读取从结果**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="00b93-118">Read the results from the **SAPDataReader**.</span></span>  
  
8. <span data-ttu-id="00b93-119">在完成使用它们，请关闭 （或 dispose） **SAPConnection**并**SAPDataReader**。</span><span class="sxs-lookup"><span data-stu-id="00b93-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
   <span data-ttu-id="00b93-120">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。</span><span class="sxs-lookup"><span data-stu-id="00b93-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="00b93-121">有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[与 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="00b93-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b93-122">示例</span><span class="sxs-lookup"><span data-stu-id="00b93-122">Example</span></span>  
 <span data-ttu-id="00b93-123">下面的示例调用 SD_RFC_CUSTOMER_GET 检索其名称以"AB"开头的所有客户的客户信息。</span><span class="sxs-lookup"><span data-stu-id="00b93-123">The following example invokes SD_RFC_CUSTOMER_GET to retrieve customer information for all customers whose names start with "AB".</span></span> <span data-ttu-id="00b93-124">它然后客户将记录写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="00b93-124">It then writes the customer records to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00b93-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="00b93-125">See Also</span></span>  
 <span data-ttu-id="00b93-126">[使用用于 mySAP Business Suite 的.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="00b93-126">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="00b93-127">示例</span><span class="sxs-lookup"><span data-stu-id="00b93-127">Samples</span></span>](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)