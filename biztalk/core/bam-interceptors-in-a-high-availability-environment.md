---
title: "在高可用性环境中的 BAM 拦截器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a>高可用性环境中的 BAM 侦听器
本主题介绍在高可用性环境下 SQL Server 故障转移过程中 BAM WF 侦听器和 BAM WCF 侦听器的故障转移流程。  
  
## <a name="bam-wf-interceptor"></a>BAM WF 侦听器  
 BAM WF 侦听器在高可用性环境下运行时，如果在 SQL Server 故障转移过程中发生 SQL Server 连接问题，BAM WF 侦听器将重试对侦听器配置文件的检索。 不过，如果正处于 SQL Server 故障转移过程中，则该侦听器不会在将数据写入 BAM 主导入数据库时重试。 这是因为侦听器依赖于的行为**WorkflowCommitBatchService**类将数据写入到 BAM 主导入数据库时。  
  
 在下面的示例中， **DefaultWorkflowCommitWorkBatchService**添加为运行时服务与 enableRetries ="true"，以便它重试的批处理中的 App.config 文件从一个代码段所示：  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 但是，如果存在环境事务时**CommitWorkBatch**方法被调用时，立即 SQL Server 连接不可用，将会终止该工作流实例。  
  
 有关的行为的详细信息**WorkflowCommitBatchService**类在高可用性环境中，请参阅"可靠性和高可用性"一节"Introduction 到承载 Windows Workflow Foundation 中"在[http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)。  
  
## <a name="bam-wcf-interceptor"></a>BAM WCF 侦听器  
 在高可用性环境下，如果在 SQL Server 故障转移过程中 SQL Server 连接发生问题，BAM WCF 侦听器不会重试对侦听器配置文件的检索。 因此您应自定义 WCF 代码以补救此类失败，或者通过可靠的消息传送重新提交消息。  
  
## <a name="see-also"></a>另请参阅  
 [BAM WF 拦截器](../core/bam-wf-interceptor.md)