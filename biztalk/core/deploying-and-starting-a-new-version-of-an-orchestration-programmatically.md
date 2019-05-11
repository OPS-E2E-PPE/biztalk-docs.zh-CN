---
title: 部署和启动业务流程的新版本以编程方式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f90025ec-3641-49ef-8918-88238d6ad420
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2398fbbfce73637d8c9cc3607c1fc5c82c1e0f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389608"
---
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a>部署和以编程方式启动业务流程的新版本
本主题中的代码演示如何快速部署和启动新版本的业务流程。 手动操作可能要花费几秒钟来执行，因为手动取消登记业务流程，然后启动它的新版本可能导致挂起或重复的消息。 本主题中说明的编程方法，可更快速地执行这些操作，以便如果一个操作失败，这两个业务流程会保留在减少的挂起和重复消息 – 并作为单个事务的可能性相同状态如同它们是在开始。  
  
> [!NOTE]
>  在极少数情况下，当您正在更新包含新版本的业务流程在高负载下运行时某些消息也会挂起即使取消登记和登记业务流程以编程方式。  我们建议执行这些操作之后, 你检查挂起的消息队列并恢复任何挂起的消息。  
  
 下面的代码示例说明了如何使用资源管理器 OM API 取消登记现有的业务流程并启动新版本的业务流程。  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
#endregion  
namespace OrchestrationBinding  
{  
class OrchestrationBinding  
{  
static void Main(string[] args)  
{  
            UpdateOrchestration();  
}  
        static public void UpdateOrchestration()  
        {  
            // Create the root object and set the connection string  
            BtsCatalogExplorer catalog = new BtsCatalogExplorer();  
            catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI";  
            string orchestrationAssemblyV1 = "HelloWorld, Version=1.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationAssemblyV2 = "HelloWorld, Version=2.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationName = "Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule";  
            try  
            {  
                BtsAssembly assemblyV1 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV1);  
                BtsAssembly assemblyV2 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV2);  
                BtsOrchestration orchestrationV1 = assemblyV1.Orchestrations[orchestrationName];  
                BtsOrchestration orchestrationV2 = assemblyV2.Orchestrations[orchestrationName];  
                orchestrationV1.Status = OrchestrationStatus.Unenlisted;  
                orchestrationV2.Status = OrchestrationStatus.Started;  
                // Commit the accumulated changes transactionally  
                catalog.SaveChanges();  
            }  
            catch (Exception e)  
            {  
                catalog.DiscardChanges();  
                throw;  
            }  
        }  
        static BtsAssembly FindAssemblyByFullName(BtsAssemblyCollection assemblies, string fullName)  
        {  
            foreach (BtsAssembly assembly in assemblies)  
            {  
                if (assembly.DisplayName == fullName)  
                    return assembly;  
            }  
            return null;  
        }  
}  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)   
 [如何登记业务流程](../core/how-to-enlist-an-orchestration.md)   
 [如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)