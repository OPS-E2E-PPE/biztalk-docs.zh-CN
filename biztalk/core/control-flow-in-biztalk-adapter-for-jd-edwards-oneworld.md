---
title: "控制流中的 BizTalk Adapter 博士 Edwards OneWorld |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc5a8be6516b61c4049242952967ce939513e9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="71c43-102">控制 JD Edwards OneWorld 的 BizTalk 适配器中的流</span><span class="sxs-lookup"><span data-stu-id="71c43-102">Control Flow in BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="71c43-103">本主题讨论了适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器中的设计时间和运行时间控制流。</span><span class="sxs-lookup"><span data-stu-id="71c43-103">This topic discusses the design time and run-time control flows in Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="design-time-flow"></a><span data-ttu-id="71c43-104">设计时流</span><span class="sxs-lookup"><span data-stu-id="71c43-104">Design-Time Flow</span></span>  
 <span data-ttu-id="71c43-105">打开适配器时（使用“传输属性”对话框中的凭据和系统信息），将创建并轮询一个或多个 JD Edwards OneWorld 应用程序业务函数实例。</span><span class="sxs-lookup"><span data-stu-id="71c43-105">When the adapter opens (using the credentials and system information from the Transport Properties dialog box), one or more instances of the JD Edwards OneWorld application business function are created and pooled.</span></span> <span data-ttu-id="71c43-106">浏览适配器向导中的命名空间时，显示业务功能的列表。</span><span class="sxs-lookup"><span data-stu-id="71c43-106">When you browse the namespace in the Adapter Wizard, a list of business functions appear.</span></span> <span data-ttu-id="71c43-107">单击业务函数显示其逻辑的方法以及方法签名。</span><span class="sxs-lookup"><span data-stu-id="71c43-107">Clicking a business function displays its logical methods along with the methods signatures.</span></span>  
  
## <a name="run-time-flow"></a><span data-ttu-id="71c43-108">运行时流</span><span class="sxs-lookup"><span data-stu-id="71c43-108">Run-Time Flow</span></span>  
 <span data-ttu-id="71c43-109">将创建并放入池中为每个线程博士 Edwards OneWorld 业务功能的实例。</span><span class="sxs-lookup"><span data-stu-id="71c43-109">Instances of the JD Edwards OneWorld business function are created and pooled for each thread.</span></span> <span data-ttu-id="71c43-110">当方法调用提交至业务服务时，使用博士 Edwards OneWorld 应用程序业务函数; 读取方法的元数据但是，如果已缓存方法的元数据，业务功能将使用缓存的信息，然后将相应的方法调用。</span><span class="sxs-lookup"><span data-stu-id="71c43-110">When a method call is submitted to a business service, the metadata for the method is read using the JD Edwards OneWorld application business function; however, if the metadata for the method has already been cached, the business function uses the cached information and then makes a call to the appropriate method.</span></span> <span data-ttu-id="71c43-111">在运行时，动态构造博士 Edwards OneWorld 接口层。</span><span class="sxs-lookup"><span data-stu-id="71c43-111">At run time, a JD Edwards OneWorld interface layer is dynamically constructed.</span></span> <span data-ttu-id="71c43-112">它是通过接口层用于博士 Edwards OneWorld 的 BizTalk Adapter 支持调用和数据转换。</span><span class="sxs-lookup"><span data-stu-id="71c43-112">It is through the interface layer that BizTalk Adapter for JD Edwards OneWorld supports invocation and data conversions.</span></span>  
  
 <span data-ttu-id="71c43-113">用于博士 Edwards OneWorld 的 BizTalk Adapter 将映射博士 Edwards OneWorld 应用程序，调用的方法签名的接口说明允许 BizTalk Server 与这些接口说明进行交互。</span><span class="sxs-lookup"><span data-stu-id="71c43-113">BizTalk Adapter for JD Edwards OneWorld maps interface descriptions of the method signatures of the JD Edwards OneWorld application, allowing BizTalk Server to interact with these interface descriptions.</span></span>  
  
 <span data-ttu-id="71c43-114">适配器使企业中的应用程序可以通过扩展从一个或多个以下的窗体中的应用程序的功能与博士 Edwards OneWorld 应用程序进行交互：</span><span class="sxs-lookup"><span data-stu-id="71c43-114">The adapter enables applications in the enterprise to interact with the JD Edwards OneWorld application by extending functionality from the application in the form of one or more of the following:</span></span>  
  
-   <span data-ttu-id="71c43-115">本机数据格式</span><span class="sxs-lookup"><span data-stu-id="71c43-115">Native data formats</span></span>  
  
-   <span data-ttu-id="71c43-116">过程</span><span class="sxs-lookup"><span data-stu-id="71c43-116">Procedures</span></span>  
  
-   <span data-ttu-id="71c43-117">方法</span><span class="sxs-lookup"><span data-stu-id="71c43-117">Methods</span></span>  
  
-   <span data-ttu-id="71c43-118">消息</span><span class="sxs-lookup"><span data-stu-id="71c43-118">Messages</span></span>  
  
-   <span data-ttu-id="71c43-119">属性</span><span class="sxs-lookup"><span data-stu-id="71c43-119">Properties</span></span>  
  
-   <span data-ttu-id="71c43-120">应用程序接口</span><span class="sxs-lookup"><span data-stu-id="71c43-120">Application interfaces</span></span>  
  
 <span data-ttu-id="71c43-121">在运行时，用于博士 Edwards OneWorld 的 BizTalk Adapter 生成与博士 Edwards OneWorld 交互的客户端应用程序的应用程序接口的描述。</span><span class="sxs-lookup"><span data-stu-id="71c43-121">At run time, BizTalk Adapter for JD Edwards OneWorld builds a description of application interfaces for client applications that interact with JD Edwards OneWorld.</span></span> <span data-ttu-id="71c43-122">该适配器可以创建、 删除和调用业务对象，如需要应用程序中执行计算并直接调用方法。</span><span class="sxs-lookup"><span data-stu-id="71c43-122">The adapter can create, delete, and invoke business objects as needed, to perform computations in the application and directly invoke methods.</span></span> <span data-ttu-id="71c43-123">所有调入博士 Edwards OneWorld 都是同步调用。</span><span class="sxs-lookup"><span data-stu-id="71c43-123">All calls into JD Edwards OneWorld are synchronous calls.</span></span> <span data-ttu-id="71c43-124">适配器从 BizTalk Server 接收的 XML 消息，将消息放入 SOAP 信封，将从 SOAP 消息进行的调用的数据转换为 Java 类型。</span><span class="sxs-lookup"><span data-stu-id="71c43-124">The adapter receives the XML messages from BizTalk Server, encloses the messages in a SOAP envelope, and transforms the data for the call from SOAP messages into Java types.</span></span>  
  
 <span data-ttu-id="71c43-125">回复发送回遵循类似的过程：</span><span class="sxs-lookup"><span data-stu-id="71c43-125">The reply is sent back following a similar process:</span></span>  
  
1.  <span data-ttu-id="71c43-126">Java 类型被转换为 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="71c43-126">The Java types are transformed into SOAP messages.</span></span>  
  
2.  <span data-ttu-id="71c43-127">SOAP 消息转换为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="71c43-127">The SOAP messages are converted into XML messages.</span></span>  
  
3.  <span data-ttu-id="71c43-128">XML 消息进行进一步处理提交给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="71c43-128">The XML messages are submitted to BizTalk Server for further processing.</span></span>  
  
### <a name="apartment-threading-of-business-functions"></a><span data-ttu-id="71c43-129">单元线程处理的业务函数</span><span class="sxs-lookup"><span data-stu-id="71c43-129">Apartment Threading of Business Functions</span></span>  
 <span data-ttu-id="71c43-130">博士 Edwards OneWorld 业务功能和任何实例，仅可在其中创建或获取线程上。</span><span class="sxs-lookup"><span data-stu-id="71c43-130">A JD Edwards OneWorld business function, and any instance, can only be used on the thread where it is created or obtained.</span></span> <span data-ttu-id="71c43-131">这称为*单元线程处理*。</span><span class="sxs-lookup"><span data-stu-id="71c43-131">This is known as *apartment threading*.</span></span> <span data-ttu-id="71c43-132">博士 Edwards OneWorld 的 BizTalk 适配器的连接池 framework 管理的池的可用连接。</span><span class="sxs-lookup"><span data-stu-id="71c43-132">The connection pooling framework of BizTalk Adapter for JD Edwards OneWorld manages a pool of available connections.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="71c43-133">连接池</span><span class="sxs-lookup"><span data-stu-id="71c43-133">Connection Pooling</span></span>  
 <span data-ttu-id="71c43-134">连接池可以调用的性能提高通过使与服务器系统的连接打开并重新使用它们而不每次调用后将其关闭。</span><span class="sxs-lookup"><span data-stu-id="71c43-134">Connection pooling improves the performance of calls by keeping connections to the server systems open and reusing them instead of closing them after each call.</span></span> <span data-ttu-id="71c43-135">博士 Edwards OneWorld 的 BizTalk 适配器可以在特定的登录 Id，连接池，同时仍然跨所有池保留的连接总数的关键控件。</span><span class="sxs-lookup"><span data-stu-id="71c43-135">BizTalk Adapter for JD Edwards OneWorld enables you to pool connections within particular logon IDs, but still maintains critical control of the total number of connections across all pools.</span></span>  
  
 <span data-ttu-id="71c43-136">任何新的业务函数实例使用的线程创建，且每次操作后销毁实例。</span><span class="sxs-lookup"><span data-stu-id="71c43-136">Any new business function instance uses the thread on which it is created, and the instance is destroyed after each operation.</span></span> <span data-ttu-id="71c43-137">对业务功能的所有博士 Edwards OneWorld 调用都是无状态;但是，在操作时，适配器可以确保业务功能使用正确线程上。</span><span class="sxs-lookup"><span data-stu-id="71c43-137">All JD Edwards OneWorld calls to business functions are stateless; however, during the operation, the adapter ensures that the business function is used on the correct thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c43-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71c43-138">See Also</span></span>  
 <span data-ttu-id="71c43-139">[开发应用程序](../core/developing-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="71c43-139">[Developing Applications](../core/developing-applications3.md) </span></span>  
 [<span data-ttu-id="71c43-140">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="71c43-140">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)