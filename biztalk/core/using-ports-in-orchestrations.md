---
title: "使用在业务流程中的端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-ports-in-orchestrations"></a><span data-ttu-id="a6f4d-102">使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="a6f4d-102">Using Ports in Orchestrations</span></span>
<span data-ttu-id="a6f4d-103">端口指定了业务流程与其他业务程序之间收发消息的方式。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-103">Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="a6f4d-104">每个端口都具有类型、方向和绑定，它们共同确定通信方向、通信模式、消息的源位置或目标位置、以及进行通信的方式。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-104">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6f4d-105">端口与端口类型之间存在差别。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-105">There is a distinction between a port and a port type.</span></span> <span data-ttu-id="a6f4d-106">端口是端口类型的实例，多个不同的端口可以具有相同的端口类型。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-106">A port is an instance of a port type; several different ports may have the same port type.</span></span>  
  
 <span data-ttu-id="a6f4d-107">根据这些因素的不同，端口可能与 URI（物理位置）、传输（FILE、HTTP、SOAP、SMTP 或 BizTalk 消息队列）、用于准备消息以进行发送的发送管道（例如，通过对消息进行组装、加密、压缩或执行其他某些操作）或用于准备接收的消息以进行处理的接收管道（例如，通过对消息进行拆装、解密或解压缩）相关联。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-107">Depending on these factors, a port may have associated with it a URI (a physical location), a transport (either FILE, HTTP, SOAP, SMTP or BizTalk Message Queuing), a send pipeline to prepare a message for sending (for example, by assembling, encrypting, compressing, or performing some other action on it), and a receive pipeline to prepare a received message for processing (for example, by disassembling, decrypting, or decompressing it).</span></span>  
  
 <span data-ttu-id="a6f4d-108">向业务流程添加端口的方式与向 Web 窗体或 Windows 窗体添加控件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-108">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="a6f4d-109">还可以使用“业务流程视图”窗口来添加端口。</span><span class="sxs-lookup"><span data-stu-id="a6f4d-109">You can also add ports by using the Orchestration View window.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6f4d-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="a6f4d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a6f4d-111">通信模式</span><span class="sxs-lookup"><span data-stu-id="a6f4d-111">Communication Pattern</span></span>](../core/communication-pattern.md)  
  
-   [<span data-ttu-id="a6f4d-112">通信方向</span><span class="sxs-lookup"><span data-stu-id="a6f4d-112">Communication Direction</span></span>](../core/communication-direction.md)  
  
-   [<span data-ttu-id="a6f4d-113">端口绑定</span><span class="sxs-lookup"><span data-stu-id="a6f4d-113">Port Bindings</span></span>](../core/port-bindings.md)  
  
-   [<span data-ttu-id="a6f4d-114">如何使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="a6f4d-114">How to Use Ports in Orchestrations</span></span>](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [<span data-ttu-id="a6f4d-115">如何使用端口类型</span><span class="sxs-lookup"><span data-stu-id="a6f4d-115">How to Work with Port Types</span></span>](../core/how-to-work-with-port-types.md)  
  
-   [<span data-ttu-id="a6f4d-116">如何运行端口配置向导</span><span class="sxs-lookup"><span data-stu-id="a6f4d-116">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [<span data-ttu-id="a6f4d-117">使用在业务流程中的直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="a6f4d-117">Working with Direct Bound Ports in Orchestrations</span></span>](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6f4d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f4d-118">See Also</span></span>  
 <span data-ttu-id="a6f4d-119">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="a6f4d-119">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="a6f4d-120">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="a6f4d-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)