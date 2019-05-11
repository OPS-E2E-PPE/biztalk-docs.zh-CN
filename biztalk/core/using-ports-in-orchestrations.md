---
title: 使用业务流程中的端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2204e5bb00cd6614c66f9325f043db131b402fbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396578"
---
# <a name="using-ports-in-orchestrations"></a><span data-ttu-id="5c1c1-102">使用业务流程中端口</span><span class="sxs-lookup"><span data-stu-id="5c1c1-102">Using Ports in Orchestrations</span></span>
<span data-ttu-id="5c1c1-103">端口指定如何将消息发送到您的业务流程和从其他业务流程接收消息。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-103">Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="5c1c1-104">每个端口都具有一个类型、 方向和绑定，它们共同确定通信、 通信模式、 位置或从其发送或接收消息和如何进行通信的方向。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-104">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c1c1-105">没有端口和端口类型之间的区别。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-105">There is a distinction between a port and a port type.</span></span> <span data-ttu-id="5c1c1-106">端口是端口类型; 的实例多个不同的端口可能具有相同的端口类型。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-106">A port is an instance of a port type; several different ports may have the same port type.</span></span>  
  
 <span data-ttu-id="5c1c1-107">根据这些因素，端口可能会有与它关联的 URI （物理位置）、 传输 （FILE、 HTTP、 SOAP、 SMTP 或 BizTalk 消息队列）、 发送管道来做好 （例如，按其进行组合、 加密、 压缩时，发送一条消息或对它执行一些其他操作） 和接收管道进行处理 （例如，通过拆装、 解密或对其进行解压缩） 准备接收的消息。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-107">Depending on these factors, a port may have associated with it a URI (a physical location), a transport (either FILE, HTTP, SOAP, SMTP or BizTalk Message Queuing), a send pipeline to prepare a message for sending (for example, by assembling, encrypting, compressing, or performing some other action on it), and a receive pipeline to prepare a received message for processing (for example, by disassembling, decrypting, or decompressing it).</span></span>  
  
 <span data-ttu-id="5c1c1-108">你将端口添加到业务流程相同的方式向 Web 窗体或 Windows 窗体添加控件。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-108">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="5c1c1-109">此外可以通过使用业务流程视图窗口来添加端口。</span><span class="sxs-lookup"><span data-stu-id="5c1c1-109">You can also add ports by using the Orchestration View window.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c1c1-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="5c1c1-110">In This Section</span></span>  
  
-   [<span data-ttu-id="5c1c1-111">通信模式</span><span class="sxs-lookup"><span data-stu-id="5c1c1-111">Communication Pattern</span></span>](../core/communication-pattern.md)  
  
-   [<span data-ttu-id="5c1c1-112">通信方向</span><span class="sxs-lookup"><span data-stu-id="5c1c1-112">Communication Direction</span></span>](../core/communication-direction.md)  
  
-   [<span data-ttu-id="5c1c1-113">端口绑定</span><span class="sxs-lookup"><span data-stu-id="5c1c1-113">Port Bindings</span></span>](../core/port-bindings.md)  
  
-   [<span data-ttu-id="5c1c1-114">如何使用业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="5c1c1-114">How to Use Ports in Orchestrations</span></span>](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [<span data-ttu-id="5c1c1-115">如何使用端口类型</span><span class="sxs-lookup"><span data-stu-id="5c1c1-115">How to Work with Port Types</span></span>](../core/how-to-work-with-port-types.md)  
  
-   [<span data-ttu-id="5c1c1-116">如何运行端口配置向导</span><span class="sxs-lookup"><span data-stu-id="5c1c1-116">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [<span data-ttu-id="5c1c1-117">在业务流程中使用直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="5c1c1-117">Working with Direct Bound Ports in Orchestrations</span></span>](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c1c1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c1c1-118">See Also</span></span>  
 <span data-ttu-id="5c1c1-119">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5c1c1-119">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="5c1c1-120">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="5c1c1-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)