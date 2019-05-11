---
title: 使用 Siebel 业务组件上运行 SELECT 查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performing operations, selecting data using ADO.NET provider
- how to, select data in business components using ADO.NET provider
ms.assetid: 34a22c2e-6fc9-4760-90a1-131a38ae947b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae686ace4f7feea8b5084f7d4844df61ea79807
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371128"
---
# <a name="run-a-select-query-on-business-components-with-siebel"></a>使用 Siebel 业务组件上运行 SELECT 查询
本部分演示如何从使用 Siebel 业务组件中选择数据[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]。  
  
## <a name="selecting-data-from-a-siebel-business-component"></a>选择 Siebel 业务组件中的数据  
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
  
## <a name="see-also"></a>请参阅  
 [用于 Siebel eBusiness 应用程序使用.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)   
 [运行与 Siebel 业务服务上的执行操作](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)