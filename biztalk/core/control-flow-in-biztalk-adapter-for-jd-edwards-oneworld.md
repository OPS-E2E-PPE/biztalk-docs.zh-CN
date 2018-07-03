---
title: 控制用于 JD Edwards OneWorld 的 BizTalk 适配器中的流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c777d909d5ffd405caec6641ef4a50a59e66b3b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978926"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="655de-102">控制 JD Edwards OneWorld 的 BizTalk 适配器中的流</span><span class="sxs-lookup"><span data-stu-id="655de-102">Control Flow in BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="655de-103">本主题讨论了适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器中的设计时间和运行时间控制流。</span><span class="sxs-lookup"><span data-stu-id="655de-103">This topic discusses the design time and run-time control flows in Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="design-time-flow"></a><span data-ttu-id="655de-104">设计时流</span><span class="sxs-lookup"><span data-stu-id="655de-104">Design-Time Flow</span></span>  
 <span data-ttu-id="655de-105">打开适配器时（使用“传输属性”对话框中的凭据和系统信息），将创建并轮询一个或多个 JD Edwards OneWorld 应用程序业务函数实例。</span><span class="sxs-lookup"><span data-stu-id="655de-105">When the adapter opens (using the credentials and system information from the Transport Properties dialog box), one or more instances of the JD Edwards OneWorld application business function are created and pooled.</span></span> <span data-ttu-id="655de-106">当您浏览适配器向导中的命名空间时，显示业务功能的列表。</span><span class="sxs-lookup"><span data-stu-id="655de-106">When you browse the namespace in the Adapter Wizard, a list of business functions appear.</span></span> <span data-ttu-id="655de-107">单击业务函数显示其逻辑方法以及方法签名。</span><span class="sxs-lookup"><span data-stu-id="655de-107">Clicking a business function displays its logical methods along with the methods signatures.</span></span>  
  
## <a name="run-time-flow"></a><span data-ttu-id="655de-108">运行时流</span><span class="sxs-lookup"><span data-stu-id="655de-108">Run-Time Flow</span></span>  
 <span data-ttu-id="655de-109">创建 JD Edwards OneWorld 业务函数实例和组建成池供每个线程。</span><span class="sxs-lookup"><span data-stu-id="655de-109">Instances of the JD Edwards OneWorld business function are created and pooled for each thread.</span></span> <span data-ttu-id="655de-110">方法调用提交到一种业务服务，该方法的元数据是使用 JD Edwards OneWorld 应用程序业务函数; 读取但是，如果已缓存的元数据的方法，业务功能，使用缓存的信息并将调用相应方法。</span><span class="sxs-lookup"><span data-stu-id="655de-110">When a method call is submitted to a business service, the metadata for the method is read using the JD Edwards OneWorld application business function; however, if the metadata for the method has already been cached, the business function uses the cached information and then makes a call to the appropriate method.</span></span> <span data-ttu-id="655de-111">在运行时动态构造 JD Edwards OneWorld 接口层。</span><span class="sxs-lookup"><span data-stu-id="655de-111">At run time, a JD Edwards OneWorld interface layer is dynamically constructed.</span></span> <span data-ttu-id="655de-112">它是通过接口层用于 JD Edwards OneWorld 的 BizTalk 适配器支持调用和数据转换。</span><span class="sxs-lookup"><span data-stu-id="655de-112">It is through the interface layer that BizTalk Adapter for JD Edwards OneWorld supports invocation and data conversions.</span></span>  
  
 <span data-ttu-id="655de-113">用于 JD Edwards OneWorld 的 BizTalk 适配器将映射 JD Edwards OneWorld 应用程序的方法签名的接口的描述允许 BizTalk Server 与这些接口描述进行交互。</span><span class="sxs-lookup"><span data-stu-id="655de-113">BizTalk Adapter for JD Edwards OneWorld maps interface descriptions of the method signatures of the JD Edwards OneWorld application, allowing BizTalk Server to interact with these interface descriptions.</span></span>  
  
 <span data-ttu-id="655de-114">该适配器能够在企业中的应用程序能够通过扩展从一个或多个以下的窗体中的应用程序的功能与 JD Edwards OneWorld 应用程序进行交互：</span><span class="sxs-lookup"><span data-stu-id="655de-114">The adapter enables applications in the enterprise to interact with the JD Edwards OneWorld application by extending functionality from the application in the form of one or more of the following:</span></span>  
  
- <span data-ttu-id="655de-115">本机数据格式</span><span class="sxs-lookup"><span data-stu-id="655de-115">Native data formats</span></span>  
  
- <span data-ttu-id="655de-116">过程</span><span class="sxs-lookup"><span data-stu-id="655de-116">Procedures</span></span>  
  
- <span data-ttu-id="655de-117">方法</span><span class="sxs-lookup"><span data-stu-id="655de-117">Methods</span></span>  
  
- <span data-ttu-id="655de-118">消息</span><span class="sxs-lookup"><span data-stu-id="655de-118">Messages</span></span>  
  
- <span data-ttu-id="655de-119">属性</span><span class="sxs-lookup"><span data-stu-id="655de-119">Properties</span></span>  
  
- <span data-ttu-id="655de-120">应用程序接口</span><span class="sxs-lookup"><span data-stu-id="655de-120">Application interfaces</span></span>  
  
  <span data-ttu-id="655de-121">在运行时，用于 JD Edwards OneWorld 的 BizTalk 适配器生成应用程序接口与 JD Edwards OneWorld 进行交互的客户端应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="655de-121">At run time, BizTalk Adapter for JD Edwards OneWorld builds a description of application interfaces for client applications that interact with JD Edwards OneWorld.</span></span> <span data-ttu-id="655de-122">适配器可以创建、 删除和根据需要以在应用程序中执行计算并直接调用的方法调用的业务对象。</span><span class="sxs-lookup"><span data-stu-id="655de-122">The adapter can create, delete, and invoke business objects as needed, to perform computations in the application and directly invoke methods.</span></span> <span data-ttu-id="655de-123">对 JD Edwards OneWorld 的所有调用都都同步调用。</span><span class="sxs-lookup"><span data-stu-id="655de-123">All calls into JD Edwards OneWorld are synchronous calls.</span></span> <span data-ttu-id="655de-124">适配器接收来自 BizTalk Server 的 XML 消息、 将消息封装在 SOAP 信封，并将从 SOAP 消息的调用的数据转换为 Java 类型。</span><span class="sxs-lookup"><span data-stu-id="655de-124">The adapter receives the XML messages from BizTalk Server, encloses the messages in a SOAP envelope, and transforms the data for the call from SOAP messages into Java types.</span></span>  
  
  <span data-ttu-id="655de-125">返回以下类似的过程发送回复：</span><span class="sxs-lookup"><span data-stu-id="655de-125">The reply is sent back following a similar process:</span></span>  
  
1.  <span data-ttu-id="655de-126">Java 类型转换成 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="655de-126">The Java types are transformed into SOAP messages.</span></span>  
  
2.  <span data-ttu-id="655de-127">SOAP 消息转换为 XML 消息中。</span><span class="sxs-lookup"><span data-stu-id="655de-127">The SOAP messages are converted into XML messages.</span></span>  
  
3.  <span data-ttu-id="655de-128">XML 消息提交到 BizTalk Server 进行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="655de-128">The XML messages are submitted to BizTalk Server for further processing.</span></span>  
  
### <a name="apartment-threading-of-business-functions"></a><span data-ttu-id="655de-129">单元线程处理的业务功能</span><span class="sxs-lookup"><span data-stu-id="655de-129">Apartment Threading of Business Functions</span></span>  
 <span data-ttu-id="655de-130">JD Edwards OneWorld 业务功能和任何实例，仅可以在其中创建或获取它的线程上使用。</span><span class="sxs-lookup"><span data-stu-id="655de-130">A JD Edwards OneWorld business function, and any instance, can only be used on the thread where it is created or obtained.</span></span> <span data-ttu-id="655de-131">这称为*单元线程处理*。</span><span class="sxs-lookup"><span data-stu-id="655de-131">This is known as *apartment threading*.</span></span> <span data-ttu-id="655de-132">用于 JD Edwards OneWorld 的 BizTalk 适配器的连接池 framework 管理可用连接的池。</span><span class="sxs-lookup"><span data-stu-id="655de-132">The connection pooling framework of BizTalk Adapter for JD Edwards OneWorld manages a pool of available connections.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="655de-133">连接池</span><span class="sxs-lookup"><span data-stu-id="655de-133">Connection Pooling</span></span>  
 <span data-ttu-id="655de-134">连接池提高调用的性能，方法是让服务器系统之间的连接保持打开状态并重新使用它们而不每次调用后将其关闭。</span><span class="sxs-lookup"><span data-stu-id="655de-134">Connection pooling improves the performance of calls by keeping connections to the server systems open and reusing them instead of closing them after each call.</span></span> <span data-ttu-id="655de-135">用于 JD Edwards OneWorld 的 BizTalk 适配器可以连接池内特定登录 Id，但还可以跨所有池保持的连接总数量的关键控制。</span><span class="sxs-lookup"><span data-stu-id="655de-135">BizTalk Adapter for JD Edwards OneWorld enables you to pool connections within particular logon IDs, but still maintains critical control of the total number of connections across all pools.</span></span>  
  
 <span data-ttu-id="655de-136">任何新的业务函数实例使用的线程在其创建，并且每次操作后销毁该实例。</span><span class="sxs-lookup"><span data-stu-id="655de-136">Any new business function instance uses the thread on which it is created, and the instance is destroyed after each operation.</span></span> <span data-ttu-id="655de-137">对业务功能的所有 JD Edwards OneWorld 调用都是无状态;但是，在操作时，适配器可确保业务功能使用正确的线程上。</span><span class="sxs-lookup"><span data-stu-id="655de-137">All JD Edwards OneWorld calls to business functions are stateless; however, during the operation, the adapter ensures that the business function is used on the correct thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655de-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="655de-138">See Also</span></span>  
 <span data-ttu-id="655de-139">[开发应用程序](../core/developing-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="655de-139">[Developing Applications](../core/developing-applications3.md) </span></span>  
 [<span data-ttu-id="655de-140">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="655de-140">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)