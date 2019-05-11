---
title: 高可用性环境中的 BAM 侦听器 |Microsoft Docs
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
ms.openlocfilehash: eb2784fe37e115e4ad409b67cf052c2a16d7116b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528785"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a><span data-ttu-id="ada87-102">高可用性环境中的 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="ada87-102">BAM Interceptors in a High Availability Environment</span></span>
<span data-ttu-id="ada87-103">本主题介绍在 SQL Server 故障转移期间 BAM WF 侦听器和高可用性环境中的 BAM WCF 侦听器的故障转移流程。</span><span class="sxs-lookup"><span data-stu-id="ada87-103">This topic describes the failover processes for the BAM WF interceptor and the BAM WCF interceptor in a high availability environment during a SQL Server failover.</span></span>  
  
## <a name="bam-wf-interceptor"></a><span data-ttu-id="ada87-104">BAM WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="ada87-104">BAM WF Interceptor</span></span>  
 <span data-ttu-id="ada87-105">在高可用性环境操作时，BAM WF 侦听器将重试对侦听器配置文件的检索，在 SQL Server 故障转移期间 SQL Server 连接问题时。</span><span class="sxs-lookup"><span data-stu-id="ada87-105">When operating in a high availability environment, the BAM WF interceptor will retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="ada87-106">但是，该侦听器将重试过程中 SQL Server 故障转移时将数据写入 BAM 主导入数据库时。</span><span class="sxs-lookup"><span data-stu-id="ada87-106">However, the interceptor will not retry when writing data to the BAM Primary Import database when a SQL Server failover is in process.</span></span> <span data-ttu-id="ada87-107">这是因为该侦听器依赖的行为**WorkflowCommitBatchService**类数据写入 BAM 主导入数据库时。</span><span class="sxs-lookup"><span data-stu-id="ada87-107">This is because the interceptor relies on the behavior of the **WorkflowCommitBatchService** class when writing data to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="ada87-108">在以下示例中， **DefaultWorkflowCommitWorkBatchService**添加为运行时服务与 enableRetries ="true"，以便它重试的批处理的 App.config 文件的代码段中所示：</span><span class="sxs-lookup"><span data-stu-id="ada87-108">In the following example, **DefaultWorkflowCommitWorkBatchService** is added as a run-time service with enableRetries="true" so that it retries the batch as shown in a snippet from an App.config file:</span></span>  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 <span data-ttu-id="ada87-109">但是，如果已存在环境事务时**CommitWorkBatch**方法调用时，会立即 SQL Server 连接不可用时终止工作流实例。</span><span class="sxs-lookup"><span data-stu-id="ada87-109">However, if there are existing ambient transactions when the **CommitWorkBatch** method is called, the workflow instance is terminated immediately when a SQL Server connection is not available.</span></span>  
  
 <span data-ttu-id="ada87-110">有关行为的详细信息**WorkflowCommitBatchService**类在高可用性环境中，请参阅"简介到承载 Windows Workflow Foundation"中的"可靠性和高可用性"部分在[ http://go.microsoft.com/fwlink/?LinkId=88068 ](http://go.microsoft.com/fwlink/?LinkId=88068)。</span><span class="sxs-lookup"><span data-stu-id="ada87-110">For more information about the behavior of the **WorkflowCommitBatchService** class in a high availability environment, see the "Reliability and High Availability" section in "Introduction to Hosting Windows Workflow Foundation" at [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span></span>  
  
## <a name="bam-wcf-interceptor"></a><span data-ttu-id="ada87-111">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="ada87-111">BAM WCF Interceptor</span></span>  
 <span data-ttu-id="ada87-112">在高可用性环境中，BAM WCF 侦听器不重试对侦听器配置文件的检索 SQL Server 故障转移期间 SQL Server 连接问题时。</span><span class="sxs-lookup"><span data-stu-id="ada87-112">In a high availability environment, the BAM WCF interceptor does not retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="ada87-113">因此应自定义 WCF 代码以补救此类失败，或者使用可靠的消息传送重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="ada87-113">You should therefore customize the WCF code to compensate for failure or use reliable messaging to resubmit messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada87-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ada87-114">See Also</span></span>  
 [<span data-ttu-id="ada87-115">BAM WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="ada87-115">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)