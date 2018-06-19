---
title: 有关业务流程 |Microsoft 文档
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
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225133"
---
# <a name="about-orchestrations"></a><span data-ttu-id="c9838-102">有关业务流程</span><span class="sxs-lookup"><span data-stu-id="c9838-102">About Orchestrations</span></span>
<span data-ttu-id="c9838-103">业务流程是用于基于 XLANG/s 语言表示可执行业务程序的灵活且功能强大的工具。</span><span class="sxs-lookup"><span data-stu-id="c9838-103">An orchestration is a flexible, powerful tool for representing an executable business process based on XLANG/s language.</span></span> <span data-ttu-id="c9838-104">作为消息传递使用的某些表达式功能的 C# 语言，可以查看 XLANG/s。</span><span class="sxs-lookup"><span data-stu-id="c9838-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="c9838-105">您可以在直观的可视化绘图中设计流、解释和生成数据、调用自定义代码以及组织整个流程；并且在运行时，BizTalk 业务流程引擎执行 XLANG/s 文件（作为由 BizTalk 业务流程设计器生成的可执行业务流程）。</span><span class="sxs-lookup"><span data-stu-id="c9838-105">You can design flow, interpret and generate data, call custom code, and organize the entire process in an intuitive visual drawing, and at run time, the BizTalk Orchestration Engine executes XLANG/s files which are the executable business processes that are produced by BizTalk Orchestration Designer.</span></span>  
  
 <span data-ttu-id="c9838-106">消息、作用于消息的发送和接收操作以及传输消息的端口都是业务流程的基本元素。</span><span class="sxs-lookup"><span data-stu-id="c9838-106">Messages, the send and receive actions that operate on them, and the ports through which they are transported are all fundamental elements of an orchestration.</span></span> <span data-ttu-id="c9838-107">消息是业务流程与外界进行通信以及实施电子商务的媒介。</span><span class="sxs-lookup"><span data-stu-id="c9838-107">The message is the medium by which orchestrations communicate with the outside world and by which e-business is conducted.</span></span>  
  
 <span data-ttu-id="c9838-108">**接收**和**发送**形状封装需要接收消息发送到您的业务流程，并从其发送消息的功能。</span><span class="sxs-lookup"><span data-stu-id="c9838-108">**Receive** and **Send** shapes encapsulate the functionality you need to receive messages into your orchestration and send messages from it.</span></span> <span data-ttu-id="c9838-109">您应熟悉业务流程设计器提供的各种形状，而这些形状表示了业务流程的逻辑流。</span><span class="sxs-lookup"><span data-stu-id="c9838-109">You should become familiar with the various shapes that Orchestration Designer provides to represent the logical flow of your orchestration.</span></span>  
  
 <span data-ttu-id="c9838-110">您应理解高级业务流程概念，例如 Web Services、相关和长期事务。</span><span class="sxs-lookup"><span data-stu-id="c9838-110">You should understand advanced orchestration concepts such as Web services, correlation, and long-running transactions.</span></span> <span data-ttu-id="c9838-111">您可能无需使用所有这些功能，但了解其作用将会对您有很大帮助。</span><span class="sxs-lookup"><span data-stu-id="c9838-111">You might not need to use all of these facilities, but it is helpful to know what they can do for you.</span></span>  
  
 <span data-ttu-id="c9838-112">Web Services 是指接口符合 Web Services 描述语言 (WSDL) 所述标准的程序。</span><span class="sxs-lookup"><span data-stu-id="c9838-112">Web services are programs with interfaces that adhere to the standards set forth in the Web Services Description Language (WSDL).</span></span> <span data-ttu-id="c9838-113">通过使用标准方法定义消息类型、端口、端口类型和操作，不同的系统之间可有效地进行通信。</span><span class="sxs-lookup"><span data-stu-id="c9838-113">By defining message types, ports, port types, and operations in a standard way, disparate systems can communicate effectively with each other.</span></span>  
  
 <span data-ttu-id="c9838-114">相关是一种机制，消息利用该机制与正在运行的特定业务流程实例相关联，以便当正在运行的实例很多并且来回发送的消息也很多时，业务程序能够获得正确的信息。</span><span class="sxs-lookup"><span data-stu-id="c9838-114">Correlation is the mechanism by which messages are associated with particular running instances of an orchestration, so that your business process gets the appropriate information when many instances are running and many messages are being sent back and forth.</span></span>  
  
 <span data-ttu-id="c9838-115">使用事务可在出现意外问题时适当地维护业务流程的状态。</span><span class="sxs-lookup"><span data-stu-id="c9838-115">Transactions enable you to maintain the state of an orchestration appropriately if any unexpected issues arise.</span></span> <span data-ttu-id="c9838-116">业务流程设计器提供不同的方法来处理异常，使您可通过可控制和可预测的方式处理错误。</span><span class="sxs-lookup"><span data-stu-id="c9838-116">Orchestration Designer provides various ways to handle exceptions, which enable you to deal with errors in a controlled and predictable manner.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9838-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9838-117">In This Section</span></span>  
  
-   [<span data-ttu-id="c9838-118">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="c9838-118">The Orchestration Design Surface</span></span>](../core/the-orchestration-design-surface.md)  
  
-   [<span data-ttu-id="c9838-119">BizTalk 业务流程选项卡工具箱</span><span class="sxs-lookup"><span data-stu-id="c9838-119">BizTalk Orchestrations Tab, Toolbox</span></span>](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [<span data-ttu-id="c9838-120">业务流程开发中的步骤</span><span class="sxs-lookup"><span data-stu-id="c9838-120">Steps in Orchestration Development</span></span>](../core/steps-in-orchestration-development.md)  
  
-   [<span data-ttu-id="c9838-121">有关开发业务流程的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="c9838-121">Security Considerations for Developing Orchestrations</span></span>](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [<span data-ttu-id="c9838-122">XLANG-s 语言</span><span class="sxs-lookup"><span data-stu-id="c9838-122">XLANG-s Language</span></span>](../core/xlang-s-language.md)  
  
-   [<span data-ttu-id="c9838-123">有关 BizTalk 业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="c9838-123">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)