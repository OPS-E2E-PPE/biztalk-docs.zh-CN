---
title: 示例供应链方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- examples, supply chains
ms.assetid: 1837a2c8-b1d4-4e1f-a196-a48b13b22662
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b338a2dea65c9d1ccd86cf46daa736d2c4044a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282117"
---
# <a name="sample-supply-chain-scenario"></a>供应链方案示例
在高科技供应链中的最基本进程之一是采购订单请求和响应消息的交换。 买方发出采购订单，并确认供应商，在行级别、 是否接受或拒绝订单，或顺序是否处于挂起状态。  
  
 本主题介绍两个贸易合作伙伴交换采购订单消息的示例方案，并说明集成和自动化如何改进过程。  
  
## <a name="the-players"></a>播放机  
 此示例方案中的买方是大型高科技设备制造商。 他们当前用于自动的数据交换基于 EDI 的系统。 与不使用 EDI 的供应商，它们依赖电话、 传真、 电子邮件使用电子表格和 Web 应用程序。 即使有这些供应商使用 EDI 的它们具有与后端 ERP 系统集成其贸易合作伙伴的通信的能力有限。 接收订单和通过 EDI 的信息后，它们必须手动重新键入这些订单到其 ERP 系统。 他们想要通过自动化需求，提高其现有的供应链流程库存、 采购和报告与贸易合作伙伴。 他们需要能够连接到其供应商和客户通过 Internet 程序直接使用其现有的业务线 (LOB) 应用程序集成的系统。  
  
 卖方是中等规模的高性能集成电路 (Ic) 供应商。 它们当前通信与贸易合作伙伴使用电话、 传真、 电子邮件与附加 Microsoft[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格、 FTP 和 Web 应用程序。 它们不使用 EDI。 与每个贸易合作伙伴的交互是不同的具体取决于客户和他们自身的技术需求。 他们想要提高业务流程的效率，以降低事务成本、 提高客户满意度并获得竞争优势。  
  
## <a name="the-present-business-process"></a>当前的业务流程  
 如果没有集成的解决方案，制造商和供应商的采购订单过程的工作原理，如下所示：  
  
1. 高科技设备制造商的客户通过网站向制造商发送订单。  
  
2. 在对原始订单的响应，制造商的职员创建中其 LOB ERP 应用程序针对 IC 供应商的采购订单请求。  
  
3. 采购订单请求将遍历生产公司中的各个参与方需要记录、 处理，查看，并授权采购订单请求。 此处理和路由是自动化的过程来 ERP 系统中的用户和手动过程，如电子邮件，带有一个附加的组合[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格。  
  
4. 员工在电子邮件，创建一个采购订单请求，并将其发送给供应商。 通过电子邮件、 传真或 EDI 与其他供应商进行通信的其他员工的大量重复此过程。 不同的部门使用不同的过程。 与这些供应商使用 EDI，制造商的职员必须创建一条消息手动从 ERP 系统。  
  
5. 员工，供应商接收的消息，然后手动密钥它到其 ERP 系统中，更改数据的格式。 通过电子邮件，员工会通知请求的其他员工。  
  
6. 其他员工分析该请求。 如果需要，他们通知其自己的有关部件需求的部件供应商。 具体取决于供应商，它们使用电话、 传真、 电子邮件或 FTP 进行通知。  
  
7. 与部门和供应商交换意见后, 每个雇员接受或拒绝每个采购订单产品系列项目，然后确认或拒绝采购订单，并指示它处于挂起状态。 他们在 ERP 系统中执行这些任务。  
  
8. 供应商的员工在电子邮件，确认或拒绝该请求，每个行项中创建采购订单响应，还是创建消息表明采购订单处于挂起状态。 供应商职员将响应消息发送到制造商。 如果挂起行项，它们将更高版本创建另一条消息，指示是否接受或拒绝挂起的项。  
  
9. 制造商的职员收到采购订单响应。 他们重新输入到他们的后端 ERP 系统的顺序。  
  
10. 另一个员工分析采购订单确认，，然后创建针对原始客户，确认订单的响应。 他们发送此响应通过电子邮件。  
  
## <a name="the-rosettanet-solution"></a>RosettaNet 解决方案  
 Microsoft BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]的自动化和标准化的采购订单请求和响应过程。 使用集成的系统的手动干预，文件处理以及使用电话和传真机量降至最低。 大多数流程都是集成的服务器计算机之间自动的处理。 当员工必须手动执行操作时，通常他们会在后端 ERP 系统上。 下图显示了一个集成的系统。  
  
 ![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-integrated-supply-chain-scenario.gif "RN3_Integrated_Supply_Chain_Scenario")  
  
 在此方案中，集成的系统改变了以下流程：  
  
- RosettaNet 实现框架 (RNIF) 连接代替常规的人工交互制造商和 IC 供应商之间。 系统自动发送和接收消息、 将数据路由到后端系统，并确认和响应消息。 制造商和供应商使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实现 RNIF 连接。  
  
- RNIF 连接代替了制造商、 IC 供应商与其他贸易合作伙伴之间的 EDI 连接。 这允许自动向贸易合作伙伴的后端系统的集成系统路由数据。 有些贸易合作伙伴使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实现 RNIF 连接; 其他人使用不同的 RosettaNet 兼容解决方案。  
  
- 对于这些没有 RosettaNet 兼容解决方案的小型合作伙伴，制造商和 IC 供应商创建合作伙伴可以访问的 Web 服务的 Web 浏览器。 Web 服务使用标准的 RNIF 连接与通信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]制造商或 IC 供应商的系统。  
  
- 消息交换的制造商和供应商遵循的架构符合标准的 RosettaNet 合作伙伴接口流程 (Pip)。 这些架构代替了 EDI 和 FTP 中使用的格式。 所有贸易合作伙伴都使用相同的架构;它们不需要映射消息数据。  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 会自动验证所有消息的架构，不良数据错误的风险。  
  
- 管理员可以对用户进行干预[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]服务器使用的管理软件工具。 客户端计算机上的业务决策者可以使用 Microsoft 基于 Office 的应用程序或工具中托管的业务监视工具。 这些是高效有效地发挥作用的系统的流程，详细了解如何同时系统 — 以及如何业务-正在运行。  
  
### <a name="message-flow"></a>消息流  
 业务流程中现在包含以下步骤：  
  
1. 高科技设备制造商的客户通过网站向制造商发送订单。  
  
2. 在对原始订单的响应，制造商的职员将生成在公司的订单和库存管理系统的采购订单请求。 该 LOB 应用程序是一个基于 Web 的用户界面的 ERP 系统。  
  
3. 系统仍以 ERP 系统的本机格式发送采购订单请求开始、 到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 自动生成符合 RosettaNet 组织定义的 3A4 PIP 的采购订单请求消息。 此采购订单请求的 XML 格式。 PIP 定义消息的内容。  
  
   > [!NOTE]
   >  3A4 PIP 确保所有采购订单请求和响应都将在窗体中相同。 此 PIP 是 RosettaNet 定义的 Pip 形成一个完整的相互关联的消息传送系统的一系列的一部分。 例如，然后再发送 3A4 消息，买方可能会查询价格和可用性 (PIP 3A2)，请求报价 (PIP 3A1) 或传输购物车 (PIP 3A3)。 后发送采购订单请求，买方可能更改采购订单 (PIP 3A8)、 取消采购订单 (PIP 3A9)、 查询采购订单状态 (PIP 3A5)，或分配采购订单状态 (PIP 3A6)。 RosettaNet 组织进行了标准化所有这些消息。  
  
5. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用允许的 RNIF 头包装请求消息 （称为服务内容）[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到另一个在 Internet 上传输消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]在供应商站点的计算机。 RNIF 定义合作伙伴通过 Internet 交换消息的方式。  
  
6. 制造商[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统将采购订单请求发送到 IC 供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统。  
  
7. 供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统接收采购订单请求。 如果这是单操作请求 （无对应的响应一个） 供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统将返回信号消息，确认收到的消息。 但是，由于这是双操作消息，供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统会返回确认回执信号消息跟响应消息。  
  
8. 供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统从采购订单请求消息中删除 RNIF 头，处理该消息的服务内容，然后将请求路由到供应商的 ERP 系统。  
  
9. 员工供应商的 ERP 系统中处理订单中工作。 如果他们必须将消息发送到其自己的部件供应商，他们将此，使用相同的 BizTalk 和[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统。 IT 部门可以自定义系统以自动响应制造商。  
  
10. 员工使用供应商的 ERP 系统生成采购订单响应消息，并随后将响应消息路由到供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统。  
  
11. 供应商[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统生成 PIP 3A4 采购订单响应消息，RNIF 头包装响应消息的服务内容，然后发送到制造商的采购订单响应[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统。  
  
12. 制造商[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统接收采购订单响应，并再将确认回执消息发送到供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。 供应商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]系统将确认路由到供应商的 ERP 系统。  
  
13. 制造商的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]从响应消息中删除 RNIF 头，处理服务内容，然后将路由到制造商的 ERP 应用程序的采购订单响应。  
  
14. 制造商的职员分析所有采购订单确认消息，然后创建针对原始客户，确认订单的响应。 然后，职员将此响应通过电子邮件。  
  
## <a name="advantages-of-the-btarn-solution"></a>BTARN 解决方案的优点  
 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]自动执行采购订单请求和响应过程的大多数方面。 它们执行此操作不仅制造商和 IC 供应商，还适用于所有其他贸易合作伙伴已采用 RosettaNet 兼容解决方案作为供应链管理的一部分。  
  
 集成系统最大程度减少人工干预和书面文件处理的数量。 大多数流程都涉及集成的服务器计算机之间的自动的交互。 制造商和 IC 供应商具有高度的控制力和可见性，他们的流程。 它们会自动接收确认消息，并可保持的不可否认的证明。  
  
 自动的系统使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，制造商和供应商可以执行以下操作：  
  
-   缩短订单执行周期时间  
  
-   减少不确定性的过程中，并提高过程的可靠性  
  
-   缩短执行时间和报价响应时间  
  
-   减少所用的时间手动重复处理信息、 获得缺失信息或更正错误  
  
-   提供可见性，并启用过程的监视和跟踪的消息  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [需贸易合作伙伴集成](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [供应链挑战](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [供应链解决方案](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [基于中心的方案示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)