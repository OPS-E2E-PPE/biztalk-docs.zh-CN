---
title: 使用 Siebel 适配器使用 WCF 服务模型中调用业务服务方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, invoking business service methods
- business service methods, invoking by using the WCF service model
ms.assetid: b41cf944-efdc-453f-824b-70581e7143e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ac29960477d3b8d3a845699a2ecf813664b7b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371150"
---
# <a name="invoke-business-service-methods-with-the-siebel-adapter-using-the-wcf-service-model"></a>使用 Siebel 适配器使用 WCF 服务模型中调用业务服务方法
您可以创建 WCF 客户端的 Siebel 业务服务的目标方法。 然后可以使用 WCF 客户端来调用这些方法在 Siebel 系统上。 Siebel 业务服务会显示在业务服务节点下[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 在对应于该服务的节点下显示由每个业务服务公开的方法。 可以按照中的步骤[使用 Siebel 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)来生成业务服务的 WCF 客户端还可以使用它来调用服务的方法。  
  
 下面的代码使用 WCF 客户端来调用**Execute**时间戳业务服务的方法。 时间戳，这返回 Siebel 服务器的本地时间，然后写入到控制台。 在此示例 WCF 客户端初始化从配置文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 生成的配置文件的示例，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp;  
  
namespace Business_Service  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessServices_TimeStamp_OperationClient client = null;  
  
            try  
            {  
                client =  
                     new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
                client.Open();  
  
                ExecuteResponseRecord er = client.Execute();  
                Console.WriteLine(er.Time);  
  
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
  
## <a name="see-also"></a>请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)