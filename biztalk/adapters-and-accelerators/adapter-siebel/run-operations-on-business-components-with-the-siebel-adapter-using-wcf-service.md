---
title: "使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations on business components
- how to, perform operations using the proxy
- business components, performing operations by using the WCF service model
- performing operations, using the proxy
ms.assetid: 7a5fdc95-6159-4f43-aac5-4e2f84e9138b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ac40efda9ed8c27fb5ac5fedfbe782b9a4f645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-the-siebel-adapter-using-the-wcf-service-model"></a>使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作
你可以创建面向 Siebel 在业务组件的 WCF 客户端。 WCF 客户端然后可以用于 Siebel 系统上执行插入、 更新、 查询、 删除、 关联、 取消关联和在业务组件上的子记录的查询操作。 Siebel 业务对象下的业务对象节点中加以表示[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 在对应于该对象的节点下中加以表示业务组件构成每个业务对象。 你可以按照中的步骤[与 Siebel 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)来生成 WCF 客户端程序针对特定操作的业务组件，并使用客户端以调用这些操作对业务组件。  
  
> [!NOTE]
>  本主题提供有关执行基本操作 （插入、 更新，查询中，删除） 在业务组件上的信息。 有关执行取消关联和子记录的查询操作相关联的详细信息，请参阅[与使用 WCF 服务模型的 MVG 字段的业务组件上运行的操作](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)  
  
 下面的代码使用 WCF 客户端的帐户业务对象的帐户业务组件中执行上一条记录的插入、 更新和删除操作。 每个操作之间执行查询操作以验证结果。 WCF 客户端在此示例中初始化从配置文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 生成的配置文件的示例，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessObjects;  
using microsoft.lobservices.siebel._2007._03;  
  
namespace Business_Component_Operations  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessObjects_Account_Account_OperationClient client = null;  
  
            try  
            {  
  
                client = new BusinessObjects_Account_Account_OperationClient("SiebelBinding_BusinessObjects_Account_Account_Operation");  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening connection to " + client.Endpoint.Address.Uri.Host);  
                client.Open();  
                AccountInsertRecord[] air = new AccountInsertRecord[1];  
                air[0] = new AccountInsertRecord();  
                Random r = new Random();  
                int count = r.Next();  
  
                air[0].Name = "Anil" + count.ToString();  
                Console.WriteLine("Inserting " + air[0].Name + " ...");  
                client.Insert(air);  
  
                //Query for the record.  
                Console.WriteLine("Querying to check inserted record ...");  
                AccountQueryInputRecord aqir = new AccountQueryInputRecord();  
                short viewmode = new short(); viewmode = 3;  
                string[] fields = new string[2];  
                fields[0] = "Name";  
                fields[1] = "Id";  
                aqir.QueryFields = fields;  
                aqir.SearchExpr = "[Name] LIKE \"Anil*\"";  
                AccountQueryRecord[] aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                string[] ids = new string[1];  
                AccountUpdateRecord[] aur = new AccountUpdateRecord[1];  
                aur[0] = new AccountUpdateRecord();  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                    ids[0] = rec.Id;  
                    aur[0].Name = rec.Name;  
                    aur[0].Id = rec.Id;  
                }  
  
                //Update it.  
  
                aur[0].Name = "Anil" + count.ToString() + "modified";  
                Console.WriteLine("Update the record to " + aur[0].Name + " ...");  
                client.Update(viewmode, aur);  
                //query again  
                aqr = client.Query(viewmode, aqir);  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine("Name: " + rec.Name);  
                    Console.WriteLine("Id: " + rec.Id);  
                    Console.WriteLine("");  
                }  
  
                //Delete it.  
                Console.WriteLine("Deleting record ...");  
                client.Delete(viewmode, ids, "");  
  
                //Check again.  
                Console.WriteLine("Check that " + aur[0].Name + " is not present");  
                aqr = client.Query(viewmode, aqir);  
  
                Console.WriteLine(aqr.Length + " records returned");  
                foreach (AccountQueryRecord rec in aqr)  
                {  
                    Console.WriteLine(rec.Name);  
                    Console.WriteLine(rec.Id);  
  
                }  
  
                // Wait for <RETURN> to end sample.  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine(e.Message);  
            }  
            finally  
            {  
                // Close the client.  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)