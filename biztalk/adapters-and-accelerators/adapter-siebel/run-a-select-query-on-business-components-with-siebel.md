---
title: "在带有 Siebel 业务组件上运行 SELECT 查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performing operations, selecting data using ADO.NET provider
- how to, select data in business components using ADO.NET provider
ms.assetid: 34a22c2e-6fc9-4760-90a1-131a38ae947b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b9bd5645579bb66a338c05802c5016214c9b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-select-query-on-business-components-with-siebel"></a>在带有 Siebel 业务组件上运行 SELECT 查询
本部分演示如何从使用 Siebel 业务组件中选择数据[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]。  
  
## <a name="selecting-data-from-a-siebel-business-component"></a>从 Siebel 在业务组件中选择数据  
 本部分演示如何从 Siebel 存储库中的"帐户"业务组件中选择数据。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data.Common;  
using Microsoft.Adapters.SiebelDbProvider;  
  
namespace SiebelADO  
{  
 class Program  
  {  
   static void Main(string[] args)  
    {  
     try  
      {  
        SiebelProviderFactory factory = SiebelProviderFactory.Instance;  
        DbConnection connection = factory.CreateConnection();  
        connection.ConnectionString = "Username=SADMIN;Password=SADMIN;ServiceUri=172.23.115.223:2321;SiebelObjectManager=SSEObjMgr;SiebelEnterpriseServer=ent771;Language=enu;SiebelRepository=Siebel Repository";  
  
         connection.Open();  
         DbCommand command = connection.CreateCommand();  
  
         //Here is a list of sample commands. The second command shows how the Siebel ViewMode can be specified in the query.  
         //command.CommandText = "SELECT * from Account.Account where [Name] LIKE '3Com'";  
         //command.CommandText = "Select [Name] from [Account].[Account] where [Name] LIKE '3Com' OPTION ‘ViewMode 1’";  
           command.CommandText = "SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC";  
  
         DbDataReader dbReader = command.ExecuteReader();  
  
         while (dbReader.Read())  
           {  
              for (int i = 0; i < dbReader.FieldCount; i++)  
               {  
                 string name = dbReader.GetName(i);  
                 string val = dbReader[i].ToString();  
                 Console.WriteLine(name + "\t:" + val);  
                 Console.WriteLine("=========================");  
               }  
           }  
             Console.WriteLine("Press any key...");  
             Console.ReadLine();  
       }  
       catch (Exception exp) { Console.WriteLine(exp.Message); }  
       }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)   
 [使用 Siebel 运行业务服务上的执行操作](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)