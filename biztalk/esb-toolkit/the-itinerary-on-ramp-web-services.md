---
title: 路线接入点 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e0f30d93514fded12d20a06d9fa27fbcd632bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980710"
---
# <a name="the-itinerary-on-ramp-web-services"></a><span data-ttu-id="b22c1-102">路线接入点 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b22c1-102">The Itinerary On-Ramp Web Services</span></span>
<span data-ttu-id="b22c1-103">路线 Web 服务是路线接入点公开的方法，允许客户端将消息提交以处理由路线服务，然后迁移到目标 Microsoft BizTalk 或 ESB 操作。</span><span class="sxs-lookup"><span data-stu-id="b22c1-103">The Itinerary Web service is an itinerary on-ramp that exposes a method that allows clients to submit messages for processing by the Itinerary Service and then onward to the target Microsoft BizTalk or ESB operations.</span></span>  
  
 <span data-ttu-id="b22c1-104">该路线 Web 服务通过有效负载到 ESB 路线管道组件中，验证路线以便验证是否在定义了这些服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置。</span><span class="sxs-lookup"><span data-stu-id="b22c1-104">The Itinerary Web service passes the payload to the ESB Itinerary pipeline components, which validates the itinerary to verify that these services are defined in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration.</span></span> <span data-ttu-id="b22c1-105">然后组件将特殊的上下文属性添加到包含已验证的旅行计划的消息。</span><span class="sxs-lookup"><span data-stu-id="b22c1-105">Then the component adds special context properties to the message containing the validated itinerary.</span></span>  
  
 <span data-ttu-id="b22c1-106">对于泛型路线接入点，在提交消息期间未提供包含路线的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="b22c1-106">In the case of a generic itinerary on-ramp, a SOAP header containing an itinerary is not provided during message submission.</span></span> <span data-ttu-id="b22c1-107">相应地，ESB 路线选择器管道组件将代替 ESB 路线管道组件。</span><span class="sxs-lookup"><span data-stu-id="b22c1-107">Accordingly, the ESB Itinerary Selector pipeline component is used in place of the ESB Itinerary pipeline component.</span></span> <span data-ttu-id="b22c1-108">ESB 路线选择器管道组件解决了基于预定义冲突解决程序的连接字符串，路线，并提供相同 ESB 路线管道组件提供的验证。</span><span class="sxs-lookup"><span data-stu-id="b22c1-108">The ESB Itinerary Selector pipeline component resolves the itinerary based on a pre-defined resolver connection string, and it provides the same validation that the ESB Itinerary pipeline component provides.</span></span>  
  
 <span data-ttu-id="b22c1-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括两种变体的路线服务，以支持这两个单向和请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="b22c1-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes two variations of the Itinerary service to support both one-way and request-response message-exchange patterns.</span></span> <span data-ttu-id="b22c1-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含 ASP.NET (ASMX) 和 Windows Communication Foundation (WCF) 版本的这两种服务，并提供了泛型版本的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b22c1-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains an ASP.NET (ASMX) and a Windows Communication Foundation (WCF) version of both of these services, and it provides generic versions of the WCF services.</span></span>  
  
 <span data-ttu-id="b22c1-111">提供的单向路线服务的名称是**ESB。ItineraryService**， **ESB。ItineraryServices.WCF**，和**ESB。ItineraryServices.Generic.WCF**。</span><span class="sxs-lookup"><span data-stu-id="b22c1-111">The names of the provided one-way itinerary services are **ESB.ItineraryService**, **ESB.ItineraryServices.WCF**, and **ESB.ItineraryServices.Generic.WCF**.</span></span>  
  
 <span data-ttu-id="b22c1-112">提供双向路线服务的名称是**ESB。ItineraryServices.Response**， **ESB。ItineraryServices.Response.WCF**，和**ESB。ItineraryServices.Generic.Response.WCF**。</span><span class="sxs-lookup"><span data-stu-id="b22c1-112">The names of the provided two-way itinerary services are **ESB.ItineraryServices.Response**, **ESB.ItineraryServices.Response.WCF**, and **ESB.ItineraryServices.Generic.Response.WCF**.</span></span>  
  
 <span data-ttu-id="b22c1-113">每个路线 Web 服务公开以下方法：</span><span class="sxs-lookup"><span data-stu-id="b22c1-113">Each of the Itinerary Web services exposes the following methods:</span></span>  
  
- <span data-ttu-id="b22c1-114">**SubmitRequest**。</span><span class="sxs-lookup"><span data-stu-id="b22c1-114">**SubmitRequest**.</span></span> <span data-ttu-id="b22c1-115">对于基于 ASMX 的服务，此方法采用的实例**XmlNode**类，该类包含要提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="b22c1-115">For the ASMX-based service, this method takes an instance of the **XmlNode** class that contains the message to submit.</span></span> <span data-ttu-id="b22c1-116">对于基于 WCF 的服务，此方法采用一个 XML 字符串，包含要提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="b22c1-116">For the WCF-based service, this method takes an XML string that contains the message to submit.</span></span>  
  
- <span data-ttu-id="b22c1-117">**SubmitRequestResponse**。</span><span class="sxs-lookup"><span data-stu-id="b22c1-117">**SubmitRequestResponse**.</span></span> <span data-ttu-id="b22c1-118">对于基于 ASMX 的服务，此方法将引用的实例**XmlNode**类，该类包含要提交的消息并返回响应消息中的实例**XmlNode**传递给它。</span><span class="sxs-lookup"><span data-stu-id="b22c1-118">For the ASMX-based service, this method takes a reference to an instance of the **XmlNode** class that contains the message to submit and returns the response message in the instance of the **XmlNode** passed to it.</span></span> <span data-ttu-id="b22c1-119">对于基于 WCF 的服务，此方法将引用**对象**类型，它是一个 XML 字符串，包含要提交的消息，并返回一个数组**XmlNodes**中**对象**传递给它。</span><span class="sxs-lookup"><span data-stu-id="b22c1-119">For the WCF-based service, this method takes a reference to an **Object** type that is an XML string that contains the message to submit and returns an array of **XmlNodes** in the **Object** that was passed to it.</span></span>  
  
  <span data-ttu-id="b22c1-120">有关使用路线 Web 服务的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="b22c1-120">For more information about using the Itinerary Web services, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b22c1-121">默认情况下，路线 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。</span><span class="sxs-lookup"><span data-stu-id="b22c1-121">By default, the Itinerary Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="b22c1-122">您应要求将 SSL 用于客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和承载使用网络级别 IPSec ESBExceptions 数据库的服务器之间的连接和相应的服务配置文件级访问控制列表 (ACL) 权限。</span><span class="sxs-lookup"><span data-stu-id="b22c1-122">You should configure the service to require SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the ESBExceptions database using a network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>