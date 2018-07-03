---
title: 执行 SAP 查询使用 EXECQUERY 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f250befed19f285baefc1c192f25b335701fa6ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972158"
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a>执行 SAP 查询使用 EXECQUERY 命令
[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开为 ADO.NET 数据源的 SAP 系统。 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，可以在 SAP 系统中执行预定义的查询，通过执行 EXECQUERY 语句。  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a>如何通过使用 EXECQUERY 命令执行查询  
 若要执行预定义的 SAP 查询使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：  
  
#### <a name="to-perform-a-query"></a>若要执行查询  
  
1. 包含的引用 (和在代码中使用语句) 到**Microsoft.Data.SAPClient**。  
  
2. 创建**SAPConnection**通过数据提供程序用于 SAP 连接字符串的对象。 有关连接字符串的详细信息，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
3. 打开与 SAP 系统的连接通过调用**开放**上**SAPConnection**。  
  
4. 创建**SAPCommand**对象从**SAPConnection**。  
  
5. 指定在 EXECQUERY 语句**CommandText**的属性**SAPCommand**。 如果有必要，您可以使用指定参数**SAPParameter**对象。 有关如何执行 SAP 系统使用 EXECQUERY 语句中定义的查询的详细信息，请参阅[SAP 中的 EXECQUERY 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。  
  
6. 执行命令，以执行查询并获取中的结果**SAPDataReader**。  
  
7. 读取从结果**SAPDataReader**。  
  
8. 在完成使用它们，请关闭 （或 dispose） **SAPConnection**并**SAPDataReader**。  
  
   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。 有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[与 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。  
  
## <a name="example"></a>示例  
 下面的示例将 ZTEST1，查询的结果写入到控制台。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)