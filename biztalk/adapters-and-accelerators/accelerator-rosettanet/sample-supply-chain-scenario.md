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
ms.openlocfilehash: 2f242da434e2f9c6a99ed1f3b27745885188d23e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973502"
---
# <a name="sample-supply-chain-scenario"></a>供应链方案示例
在高科技供应链中，最基本的流程之一便是采购订单请求与响应消息之间的交换。 买方发出采购订单，供应商通过一系列操作确认是否接受或拒绝订单，还是将订单挂起。  
  
 本主题讲述两个贸易合作伙伴交换采购订单消息的示例方案，并说明集成和自动化如何改进这一流程。  
  
## <a name="the-players"></a>播放机  
 本示例方案中的买方是一家大型高科技设备制造商。 目前他们使用基于 EDI 的系统进行自动数据交换。 如果供应商不使用 EDI，那么他们就要依赖电话、传真、带有电子表格的电子邮件和 Web 应用程序。 不过，即使与那些使用 EDI 的供应商打交道，他们将和贸易合作伙伴的通信与其后端 ERP 系统集成的能力也是有限的。 通过 EDI 接收订单和信息后，他们必须将这些订单手动重新键入其 ERP 系统。 他们希望将其与贸易合作伙伴之间的需求分析、库存、采购和报告等流程自动化，从而改进现有的供应链流程。 他们需要一个系统以便通过 Internet 连接其供应商和客户，并直接与他们现有的业务线 (LOB) 应用程序集成。  
  
 卖方是一家中型高性能集成电路 (IC) 供应商。 它们当前通信与贸易合作伙伴使用电话、 传真、 电子邮件与附加 Microsoft[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格、 FTP 和 Web 应用程序。 他们不使用 EDI。 他们与各个贸易合作伙伴之间的交互方式是不同的，视客户的需要以及他们自身的技术而定。 他们希望提高业务流程的效率，以降低交易成本、提高客户满意度，从而赢得竞争优势。  
  
## <a name="the-present-business-process"></a>当前业务流程  
 在没有集成的解决方案的情况下，制造商和供应商之间的采购订单处理流程如下所示：  
  
1. 高科技设备制造商的客户通过网站向制造商发送订单。  
  
2. 作为对原始订单的响应，制造商的一名职员将使用 LOB ERP 应用程序针对 IC 供应商创建一份采购订单请求。  
  
3. 采购订单请求将在制造公司的不同人员手中传递，他们负责对该采购订单请求进行记录、处理、审核和批准。 此处理和传送过程将 ERP 系统用户的自动流程与使用附带 [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] 电子表格的电子邮件之类的手动流程结合在一起。  
  
4. 职员以电子邮件的形式创建采购订单请求，并将其发送给供应商。 通过电子邮件、传真或 EDI 与其他供应商进行通信的其他职员都重复上述流程。 不同部门使用不同的流程。 即使供应商使用 EDI，制造商的职员仍须从 ERP 系统中手动创建消息。  
  
5. 供应商的职员收到该消息，然后将其手动键入他们的 ERP 系统，更改数据格式。 该职员通过电子邮件向其他职员发送有关该订单请求的通知。  
  
6. 其他职员会对该请求进行分析。 如果有必要，他们会向自己的部件供应商发送有关部件需求的通知。 根据供应商的情况，他们将使用电话、传真、电子邮件或 FTP 进行通知。  
  
7. 与部门和供应商交换意见后，各职员将接受或拒绝每个采购订单的产品系列项目，然后将确认或拒绝采购订单，或指示挂起订单。 他们在 ERP 系统中执行这些任务。  
  
8. 供应商职员以电子邮件的形式创建采购订单响应，确认或拒绝请求的各个系列项目，或者创建消息表明采购订单处于挂起状态。 供应商职员将响应消息发送给制造商。 如果挂起某个系列项目，那么日后他们将创建另一个消息，显示接受或拒绝挂起的项目。  
  
9. 制造商职员收到采购订单响应。 他们将订单重新输入其后端 ERP 系统。  
  
10. 另一名职员将分析采购订单的确认信息，然后创建针对原始客户的响应，确认订单。 他们通过电子邮件发送此响应。  
  
## <a name="the-rosettanet-solution"></a>RosettaNet 解决方案  
 Microsoft BizTalk Server 和 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 可以实现采购订单请求与响应过程的自动化和标准化。 使用集成系统可以最大程度地减少人工干预、书面文件处理以及电话和传真机的使用。 大多数流程都是在集成服务器计算机之间自动处理的。 如果职员必须手动执行某项操作，通常他们会在后端 ERP 系统中执行。 下图显示了一个集成的系统。  
  
 ![&#60;不更改&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-integrated-supply-chain-scenario.gif "RN3_Integrated_Supply_Chain_Scenario")  
  
 在此方案中，集成的系统改变了以下流程：  
  
- RosettaNet 实现框架 (RNIF) 连接代替了制造商与 IC 供应商间常规的人工交互。 系统自动发送和接收消息、将数据路由到后端系统以及确认和响应消息。 制造商和供应商均使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 实现 RNIF 连接。  
  
- RNIF 连接代替了制造商、IC 供应商及其他贸易合作伙伴之间的 EDI 连接。 这就使得集成系统可以将数据自动路由至贸易合作伙伴的后端系统。 有些贸易合作伙伴使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 实现 RNIF 连接，而有些贸易合作伙伴则使用其他与 RosettaNet 兼容的解决方案。  
  
- 对于那些不使用与 RosettaNet 兼容的解决方案的小型合作伙伴，制造商和 IC 供应商创建了 Web Services，合作伙伴可以通过 Web 浏览器访问这些 Web Services。 Web Services 使用标准的 RNIF 连接与制造商或 IC 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统进行通信。  
  
- 制造商和供应商间的消息交换所遵循的架构符合标准的 RosettaNet 合作伙伴接口流程 (PIP)。 这些架构代替了 EDI 和 FTP 中使用的格式。 所有贸易合作伙伴都使用相同的架构，从而不必映射消息数据。  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 根据架构自动验证所有的消息，从而降低数据出错的危险。  
  
- 管理员可以使用管理软件工具在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 服务器上进行干预。 客户端计算机一方的业务决策人员可以使用业务监视工具，这些业务监视工具驻留在基于 Microsoft Office 的应用程序或工具中。 这两个流程都颇为有效，既可以保持系统高效运转，又可以使工作人员更好地洞悉系统和业务的运转状况。  
  
### <a name="message-flow"></a>消息流  
 目前业务流程包括以下步骤：  
  
1. 高科技设备制造商的客户通过网站向制造商发送订单。  
  
2. 作为对原始订单的响应，制造商的职员将在公司的订单与库存管理系统上生成采购订单请求。 该 LOB 应用程序是一个使用 Web 用户界面的 ERP 系统。  
  
3. 该系统仍以 ERP 系统提供的格式向 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送采购订单请求。  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 根据 RosettaNet 组织定义的 3A4 PIP 自动生成采购订单请求消息。 该采购订单请求为 XML 格式。 PIP 定义消息的内容。  
  
   > [!NOTE]
   >  3A4 PIP 确保所有的采购订单请求与响应具有统一的形式。 此 PIP 是 RosettaNet 定义的 PIP 集合的一部分，这一集合构成了一个完整的互连的消息系统。 例如，在发送 3A4 消息前，买方可能会查询价格和可用性 (PIP 3A2)，请求报价 (PIP 3A1)，或传输购物车 (PIP 3A3)。 发送采购订单请求后，买方可能更改采购订单 (PIP 3A8)、取消采购订单 (PIP 3A9)、查询采购订单状态 (PIP 3A5)，或分配采购订单状态 (PIP 3A6)。 RosettaNet 组织已将所有这些消息标准化。  
  
5. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用 RNIF 头对请求消息（称为服务内容）进行包装，这样 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 便可以通过 Internet 将消息传输到供应商站点的另一台 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 计算机上。 RNIF 定义合作伙伴通过 Internet 交换消息的方式。  
  
6. 制造商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统将采购订单请求发送到 IC 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统。  
  
7. 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统接收采购订单请求。 如果这是单操作请求（无对应的响应），那么供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统将返回信号消息，确认消息已收到。 但是，因为这是双操作消息，所以供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统将返回确认回执信号消息，并在之后也返回响应消息。  
  
8. 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统从采购订单请求消息中删除 RNIF 头，处理消息的服务内容，然后将请求路由到供应商的 ERP 系统。  
  
9. 供应商的职员在 ERP 系统中处理订单。 如果必须向他们自己的部件供应商发送消息，则他们将使用相同的 BizTalk 和 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统完成此任务。 IT 部门可以自定义此系统以自动响应制造商。  
  
10. 职员使用供应商的 ERP 系统生成采购订单响应消息，然后将其路由到供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统。  
  
11. 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统生成 PIP 3A4 采购订单响应消息，并使用 RNIF 头包装此响应消息的服务内容，然后，将采购订单响应发送至制造商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统。  
  
12. 制造商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统收到采购订单响应，然后向供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送确认回执消息。 供应商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 系统将此确认消息路由到供应商的 ERP 系统。  
  
13. 制造商的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 从响应消息中删除 RNIF 头，并处理服务内容，然后将采购订单响应路由到制造商的 ERP 应用程序。  
  
14. 制造商的职员分析所有的采购订单确认消息，然后针对原始客户创建响应，确认订单。 然后，职员将此响应通过电子邮件发送出去。  
  
## <a name="advantages-of-the-btarn-solution"></a>BTARN 解决方案的优点  
 BizTalk Server 和 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 使采购订单请求与响应流程的诸多方面实现了自动化。 这样做的受益者不仅包括制造商和 IC 供应商，还包括其他所有采用 RosettaNet 兼容解决方案作为供应链管理的一部分的贸易合作伙伴。  
  
 集成系统将人工干预和书面文件处理量减小到最少。 大多数流程都涉及集成服务器计算机之间的自动交互。 制造商和 IC 供应商对各个流程都拥有高度的控制力及洞悉能力。 他们可以自动接收确认消息，并可保留不可否认性凭证。  
  
 使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的自动化系统可使制造商和供应商实现以下方面的改进：  
  
-   缩短订单执行的周期  
  
-   减少流程中的不确定性，并提高流程的可靠性  
  
-   缩短执行时间和报价响应时间  
  
-   缩短手动重复处理信息的时间、获得缺失信息的时间或更正错误的时间  
  
-   更方便地洞悉流程，并允许流程监视和消息跟踪  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何满足业务需求](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [需要贸易合作伙伴集成](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [供应链挑战](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [供应链解决方案](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [基于中心的方案示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)