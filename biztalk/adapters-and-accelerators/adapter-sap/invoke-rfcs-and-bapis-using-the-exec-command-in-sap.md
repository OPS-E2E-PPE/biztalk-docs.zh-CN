---
title: 调用 Rfc 和在 SAP 中使用 EXEC 命令的 BAPIs |Microsoft 文档
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
ms.openlocfilehash: 500e0f932a8245f76954aa7a8785dbec012321e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217213"
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a>调用 Rfc 和 BAPIs 在 SAP 中使用 EXEC 命令
[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]公开与 ADO.NET 数据源 SAP 系统。 通过使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，你可以调用 Rfc 和 BAPIs EXEC 命令通过 SAP 系统上。  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a>如何在 SAP 系统上调用 Rfc 和 BAPIs  
 若要调用 RFC 或 BAPI 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，执行以下步骤：  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a>若要调用的 RFC 或 BAPI  
  
1.  包含的引用 (和使用程序代码中的语句) 到**Microsoft.Data.SAPClient**。  
  
2.  创建**SAPConnection** SAP 连接字符串中使用数据访问接口的对象。 有关连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
3.  打开与 SAP 系统的连接通过调用**打开**上**SAPConnection**。  
  
4.  创建**SAPCommand**对象**SAPConnection**。  
  
5.  指定中的 BAPI 或 RFC 调用**CommandText**属性**SAPCommand**。 如果有必要，你可以指定参数使用**SAPParameter**对象。 有关如何指定 BAPI 或 RFC 调用使用 EXEC 语句的详细信息，请参阅[中 SAP 的 EXEC 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)。 有关如何指定 BAPI 或 RFC 的示例，请参阅[EXEC 语句的示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。  
  
6.  执行命令以调用 RFC 或 BAPI 并获得的结果中**SAPDataReader**。  
  
7.  读取从结果**SAPDataReader**。  
  
8.  在完成使用它们，请关闭 （或释放） **SAPConnection**和**SAPDataReader**。  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]还公开**SAPClientFactory**类，该类可用于创建**SAPConnection**， **SAPCommand**和**SAPConnection**对象。 有关 ADO.NET 类扩展的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 适配器具有扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)。  
  
## <a name="example"></a>示例  
 下面的示例调用 SD_RFC_CUSTOMER_GET 要检索其名称以"AB"开头的所有客户的客户信息。 它然后客户将记录写入到控制台。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)   
 [示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)