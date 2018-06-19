---
title: 如何使用业务规则在业务流程中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions, business rules
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- orchestrations, business rules
ms.assetid: d20473c2-267f-4a44-93c3-df6ef655020c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346582f90cada01b2350fae227885a9e9cd71712
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255565"
---
# <a name="how-to-use-business-rules-in-orchestrations"></a><span data-ttu-id="34dcc-102">如何在业务流程中使用业务规则</span><span class="sxs-lookup"><span data-stu-id="34dcc-102">How to Use Business Rules in Orchestrations</span></span>
<span data-ttu-id="34dcc-103">您可以创建业务规则策略的实例并在业务流程中执行该实例。</span><span class="sxs-lookup"><span data-stu-id="34dcc-103">You can create an instance of a Business Rules policy and execute it in your orchestration.</span></span> <span data-ttu-id="34dcc-104">为此，请在原子事务作用域内添加调用规则形状，并对其配置策略。</span><span class="sxs-lookup"><span data-stu-id="34dcc-104">To do this, add a Call Rules shape inside an atomic transaction scope, and configure a policy on it.</span></span>  
  
## <a name="examples-of-using-business-rules"></a><span data-ttu-id="34dcc-105">使用业务规则的示例</span><span class="sxs-lookup"><span data-stu-id="34dcc-105">Examples of Using Business Rules</span></span>  
  
-   [<span data-ttu-id="34dcc-106">业务规则 Hello World1 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="34dcc-106">Business Rules Hello World1 (BizTalk Server Sample)</span></span>](../core/business-rules-hello-world1-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="34dcc-107">业务规则 Hello World2 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="34dcc-107">Business Rules Hello World2 (BizTalk Server Sample)</span></span>](../core/business-rules-hello-world2-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="34dcc-108">贷款处理使用业务规则 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="34dcc-108">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>](../core/loans-processing-using-business-rules-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="34dcc-109">医疗声明处理和测试策略 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="34dcc-109">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>](../core/medical-claims-processing-and-testing-policies-biztalk-server-sample.md)  
  
-   <span data-ttu-id="34dcc-110">从下载"链式策略"SDK 示例[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="34dcc-110">Download the SDK sample "Policy Chaining" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dcc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34dcc-111">See Also</span></span>  
 [<span data-ttu-id="34dcc-112">创建和使用业务规则</span><span class="sxs-lookup"><span data-stu-id="34dcc-112">Creating and Using Business Rules</span></span>](../core/creating-and-using-business-rules.md)