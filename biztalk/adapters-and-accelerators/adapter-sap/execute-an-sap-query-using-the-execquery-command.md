---
title: 执行使用 EXECQUERY 命令 SAP 查询 |Microsoft 文档
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
ms.openlocfilehash: 86159a03858ae5aa31bb37da56b6e5ea68dac3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217205"
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a>执行 SAP 查询使用 EXECQUERY 命令
[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开与 ADO.NET 数据源 SAP 系统。 与[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，您可以通过执行 EXECQUERY 语句执行 SAP 系统中预定义的查询。  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a>如何使用 EXECQUERY 命令执行查询  
 若要执行预定义的 SAP 查询使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：  
  
#### <a name="to-perform-a-query"></a>执行查询  
  
1.  包含的引用 (和使用程序代码中的语句) 到**Microsoft.Data.SAPClient**。  
  
2.  创建**SAPConnection** SAP 连接字符串中使用数据访问接口的对象。 有关连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
3.  打开与 SAP 系统的连接通过调用**打开**上**SAPConnection**。  
  
4.  创建**SAPCommand**对象**SAPConnection**。  
  
5.  指定在 EXECQUERY 语句**CommandText**属性**SAPCommand**。 如果有必要，你可以指定参数使用**SAPParameter**对象。 有关如何执行在使用 EXECQUERY 语句 SAP 系统中定义的查询的详细信息，请参阅[SAP 中 EXECQUERY 语句语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。  
  
6.  执行命令来执行查询并获取中的结果**SAPDataReader**。  
  
7.  读取从结果**SAPDataReader**。  
  
8.  在完成使用它们，请关闭 （或释放） **SAPConnection**和**SAPDataReader**。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。 有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 适配器具有扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。  
  
## <a name="example"></a>示例  
 下面的示例将查询，ZTEST1 的结果写入控制台。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)