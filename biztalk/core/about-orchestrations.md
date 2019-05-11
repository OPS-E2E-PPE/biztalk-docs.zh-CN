---
title: 有关业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8517433777e57b9811ec16ce08bb12ada139ee4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362324"
---
# <a name="about-orchestrations"></a><span data-ttu-id="682da-102">有关业务流程</span><span class="sxs-lookup"><span data-stu-id="682da-102">About Orchestrations</span></span>
<span data-ttu-id="682da-103">业务流程是一个灵活、 强大的工具，用于表示基于 XLANG/s 语言的可执行的业务过程。</span><span class="sxs-lookup"><span data-stu-id="682da-103">An orchestration is a flexible, powerful tool for representing an executable business process based on XLANG/s language.</span></span> <span data-ttu-id="682da-104">XLANG/s 可被视为的表达式功能的某些消息传递语言C#。</span><span class="sxs-lookup"><span data-stu-id="682da-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="682da-105">可以设计流、 解释和生成数据、 调用自定义代码和组织的整个过程中直观的可视化绘图，并在运行时，BizTalk 业务流程引擎执行 XLANG/s 文件即是可执行业务流程BizTalk 业务流程设计器生成的。</span><span class="sxs-lookup"><span data-stu-id="682da-105">You can design flow, interpret and generate data, call custom code, and organize the entire process in an intuitive visual drawing, and at run time, the BizTalk Orchestration Engine executes XLANG/s files which are the executable business processes that are produced by BizTalk Orchestration Designer.</span></span>  
  
 <span data-ttu-id="682da-106">消息、 发送和接收操作对它们，并通过该传输这些端口是业务流程的所有基本元素。</span><span class="sxs-lookup"><span data-stu-id="682da-106">Messages, the send and receive actions that operate on them, and the ports through which they are transported are all fundamental elements of an orchestration.</span></span> <span data-ttu-id="682da-107">消息是依据业务流程与外部世界和通信进行电子商务的媒介。</span><span class="sxs-lookup"><span data-stu-id="682da-107">The message is the medium by which orchestrations communicate with the outside world and by which e-business is conducted.</span></span>  
  
 <span data-ttu-id="682da-108">**接收**并**发送**形状封装到您的业务流程接收消息和从其发送消息所需的功能。</span><span class="sxs-lookup"><span data-stu-id="682da-108">**Receive** and **Send** shapes encapsulate the functionality you need to receive messages into your orchestration and send messages from it.</span></span> <span data-ttu-id="682da-109">您应熟悉业务流程设计器提供的用于表示您的业务流程的逻辑流的各种形状。</span><span class="sxs-lookup"><span data-stu-id="682da-109">You should become familiar with the various shapes that Orchestration Designer provides to represent the logical flow of your orchestration.</span></span>  
  
 <span data-ttu-id="682da-110">您应该了解高级业务流程概念，如 Web 服务、 关联和长时间运行的事务。</span><span class="sxs-lookup"><span data-stu-id="682da-110">You should understand advanced orchestration concepts such as Web services, correlation, and long-running transactions.</span></span> <span data-ttu-id="682da-111">您可能不需要使用所有这些功能，但最好知道他们可以为您做什么。</span><span class="sxs-lookup"><span data-stu-id="682da-111">You might not need to use all of these facilities, but it is helpful to know what they can do for you.</span></span>  
  
 <span data-ttu-id="682da-112">Web 服务是具有遵守规定 Web 服务描述语言 (WSDL) 中的标准的界面的程序。</span><span class="sxs-lookup"><span data-stu-id="682da-112">Web services are programs with interfaces that adhere to the standards set forth in the Web Services Description Language (WSDL).</span></span> <span data-ttu-id="682da-113">通过以标准方式定义消息类型、 端口、 端口类型和操作，不同的系统可以彼此有效地通信。</span><span class="sxs-lookup"><span data-stu-id="682da-113">By defining message types, ports, port types, and operations in a standard way, disparate systems can communicate effectively with each other.</span></span>  
  
 <span data-ttu-id="682da-114">相关是所依据的消息是与特定运行的业务流程实例相关联的机制，以便您的业务流程获取相应的信息时运行多个实例并且来回发送多条消息。</span><span class="sxs-lookup"><span data-stu-id="682da-114">Correlation is the mechanism by which messages are associated with particular running instances of an orchestration, so that your business process gets the appropriate information when many instances are running and many messages are being sent back and forth.</span></span>  
  
 <span data-ttu-id="682da-115">事务可以适当地维护业务流程的状态，如果出现意外的问题。</span><span class="sxs-lookup"><span data-stu-id="682da-115">Transactions enable you to maintain the state of an orchestration appropriately if any unexpected issues arise.</span></span> <span data-ttu-id="682da-116">业务流程设计器提供了各种方法来处理异常，以便你能够控制和可预测的方式处理错误。</span><span class="sxs-lookup"><span data-stu-id="682da-116">Orchestration Designer provides various ways to handle exceptions, which enable you to deal with errors in a controlled and predictable manner.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="682da-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="682da-117">In This Section</span></span>  
  
-   [<span data-ttu-id="682da-118">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="682da-118">The Orchestration Design Surface</span></span>](../core/the-orchestration-design-surface.md)  
  
-   [<span data-ttu-id="682da-119">“BizTalk 业务流程”选项卡，工具箱</span><span class="sxs-lookup"><span data-stu-id="682da-119">BizTalk Orchestrations Tab, Toolbox</span></span>](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [<span data-ttu-id="682da-120">业务流程开发步骤</span><span class="sxs-lookup"><span data-stu-id="682da-120">Steps in Orchestration Development</span></span>](../core/steps-in-orchestration-development.md)  
  
-   [<span data-ttu-id="682da-121">开发业务流程的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="682da-121">Security Considerations for Developing Orchestrations</span></span>](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [<span data-ttu-id="682da-122">XLANG-s 语言</span><span class="sxs-lookup"><span data-stu-id="682da-122">XLANG-s Language</span></span>](../core/xlang-s-language.md)  
  
-   [<span data-ttu-id="682da-123">关于 BizTalk 业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="682da-123">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)