---
title: 在高可用性环境中的 BAM 拦截器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230733"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a><span data-ttu-id="e3672-102">高可用性环境中的 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="e3672-102">BAM Interceptors in a High Availability Environment</span></span>
<span data-ttu-id="e3672-103">本主题介绍在高可用性环境下 SQL Server 故障转移过程中 BAM WF 侦听器和 BAM WCF 侦听器的故障转移流程。</span><span class="sxs-lookup"><span data-stu-id="e3672-103">This topic describes the failover processes for the BAM WF interceptor and the BAM WCF interceptor in a high availability environment during a SQL Server failover.</span></span>  
  
## <a name="bam-wf-interceptor"></a><span data-ttu-id="e3672-104">BAM WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="e3672-104">BAM WF Interceptor</span></span>  
 <span data-ttu-id="e3672-105">BAM WF 侦听器在高可用性环境下运行时，如果在 SQL Server 故障转移过程中发生 SQL Server 连接问题，BAM WF 侦听器将重试对侦听器配置文件的检索。</span><span class="sxs-lookup"><span data-stu-id="e3672-105">When operating in a high availability environment, the BAM WF interceptor will retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="e3672-106">不过，如果正处于 SQL Server 故障转移过程中，则该侦听器不会在将数据写入 BAM 主导入数据库时重试。</span><span class="sxs-lookup"><span data-stu-id="e3672-106">However, the interceptor will not retry when writing data to the BAM Primary Import database when a SQL Server failover is in process.</span></span> <span data-ttu-id="e3672-107">这是因为侦听器依赖于的行为**WorkflowCommitBatchService**类将数据写入到 BAM 主导入数据库时。</span><span class="sxs-lookup"><span data-stu-id="e3672-107">This is because the interceptor relies on the behavior of the **WorkflowCommitBatchService** class when writing data to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="e3672-108">在下面的示例中， **DefaultWorkflowCommitWorkBatchService**添加为运行时服务与 enableRetries ="true"，以便它重试的批处理中的 App.config 文件从一个代码段所示：</span><span class="sxs-lookup"><span data-stu-id="e3672-108">In the following example, **DefaultWorkflowCommitWorkBatchService** is added as a run-time service with enableRetries="true" so that it retries the batch as shown in a snippet from an App.config file:</span></span>  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 <span data-ttu-id="e3672-109">但是，如果存在环境事务时**CommitWorkBatch**方法被调用时，立即 SQL Server 连接不可用，将会终止该工作流实例。</span><span class="sxs-lookup"><span data-stu-id="e3672-109">However, if there are existing ambient transactions when the **CommitWorkBatch** method is called, the workflow instance is terminated immediately when a SQL Server connection is not available.</span></span>  
  
 <span data-ttu-id="e3672-110">有关的行为的详细信息**WorkflowCommitBatchService**类在高可用性环境中，请参阅"可靠性和高可用性"一节"Introduction 到承载 Windows Workflow Foundation 中"在[http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)。</span><span class="sxs-lookup"><span data-stu-id="e3672-110">For more information about the behavior of the **WorkflowCommitBatchService** class in a high availability environment, see the "Reliability and High Availability" section in "Introduction to Hosting Windows Workflow Foundation" at [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span></span>  
  
## <a name="bam-wcf-interceptor"></a><span data-ttu-id="e3672-111">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="e3672-111">BAM WCF Interceptor</span></span>  
 <span data-ttu-id="e3672-112">在高可用性环境下，如果在 SQL Server 故障转移过程中 SQL Server 连接发生问题，BAM WCF 侦听器不会重试对侦听器配置文件的检索。</span><span class="sxs-lookup"><span data-stu-id="e3672-112">In a high availability environment, the BAM WCF interceptor does not retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="e3672-113">因此您应自定义 WCF 代码以补救此类失败，或者通过可靠的消息传送重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="e3672-113">You should therefore customize the WCF code to compensate for failure or use reliable messaging to resubmit messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3672-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3672-114">See Also</span></span>  
 [<span data-ttu-id="e3672-115">BAM WF 拦截器</span><span class="sxs-lookup"><span data-stu-id="e3672-115">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)