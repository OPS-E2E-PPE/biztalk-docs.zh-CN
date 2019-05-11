---
title: 配置动态发送端口以发送 EDI 交换和确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4883eb78a24eb7ad7254e319c901602dfcb97a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391401"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a><span data-ttu-id="2cd4b-102">配置动态发送端口以发送 EDI 交换和确认</span><span class="sxs-lookup"><span data-stu-id="2cd4b-102">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>
<span data-ttu-id="2cd4b-103">若要发送 EDI 确认或交换，可以使用静态发送端口或动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-103">To send an EDI acknowledgment or interchange, you can use either a static send port or a dynamic send port.</span></span> <span data-ttu-id="2cd4b-104">动态发送端口，您可以向多个目标，任何一个发送交换，因为它解析协议，并确定基于 DestinationPartyName 上下文属性中的值的目标地址。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-104">A dynamic send port enables you to send an interchange to any one of multiple destinations, because it resolves the agreement and determines the destination address based upon the value in the DestinationPartyName context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cd4b-105">如果发送 EDI 交换，它基于收到，一条 XML 消息，并且使用直通接收管道接收该应用程序，您必须升级 DestinationPartyName 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-105">If you are sending an EDI interchange that is based upon an XML message received, and you are using a passthrough receive pipeline to receive that application, you will have to promote the DestinationPartyName context property.</span></span> <span data-ttu-id="2cd4b-106">有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-106">For more information, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cd4b-107">如果动态发送端口将发送确认，因为该端口接收交换中的 EDI 拆装器上填充 DestinationPartyName 属性将已进行升级 DestinationPartyName 上下文属性确认。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-107">If the dynamic send port will be sending an acknowledgment, the DestinationPartyName context property will already be promoted because the EDI Disassembler in the port that received the interchange populates the DestinationPartyName property on the acknowledgment.</span></span>  
  
 <span data-ttu-id="2cd4b-108">若要创建单向动态发送端口，请使用以下配置：</span><span class="sxs-lookup"><span data-stu-id="2cd4b-108">To create a one-way dynamic send port, use the following configuration:</span></span>  
  
|<span data-ttu-id="2cd4b-109">Location</span><span class="sxs-lookup"><span data-stu-id="2cd4b-109">Location</span></span>|<span data-ttu-id="2cd4b-110">属性</span><span class="sxs-lookup"><span data-stu-id="2cd4b-110">Property</span></span>|<span data-ttu-id="2cd4b-111">设置</span><span class="sxs-lookup"><span data-stu-id="2cd4b-111">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="2cd4b-112">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-112">**Send Port Properties: General**</span></span>|<span data-ttu-id="2cd4b-113">端口类型</span><span class="sxs-lookup"><span data-stu-id="2cd4b-113">Port type</span></span>|<span data-ttu-id="2cd4b-114">动态单向</span><span class="sxs-lookup"><span data-stu-id="2cd4b-114">Dynamic One-Way</span></span>|  
|<span data-ttu-id="2cd4b-115">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-115">**Send Port Properties: General**</span></span>|<span data-ttu-id="2cd4b-116">发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2cd4b-116">Send handler</span></span>|<span data-ttu-id="2cd4b-117">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="2cd4b-117">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="2cd4b-118">**发送端口属性：常规**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="2cd4b-119">发送管道</span><span class="sxs-lookup"><span data-stu-id="2cd4b-119">Send pipeline</span></span>|<span data-ttu-id="2cd4b-120">EdiSend</span><span class="sxs-lookup"><span data-stu-id="2cd4b-120">EdiSend</span></span>|  
|<span data-ttu-id="2cd4b-121">**文件传输属性：身份验证**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-121">**FILE Transport Properties: Authentication**</span></span>|<span data-ttu-id="2cd4b-122">主机没有访问网络共享位置 （使用用户名和密码） 时使用这些凭据</span><span class="sxs-lookup"><span data-stu-id="2cd4b-122">Use these credentials when host does not have access to network share (with User name and Password)</span></span>|<span data-ttu-id="2cd4b-123">如果需要进行身份验证，设置。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-123">Set if authentication is required.</span></span>|  
|<span data-ttu-id="2cd4b-124">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-124">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="2cd4b-125">属性</span><span class="sxs-lookup"><span data-stu-id="2cd4b-125">Property</span></span>|<span data-ttu-id="2cd4b-126">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="2cd4b-126">BTS.MessageType</span></span>|  
|<span data-ttu-id="2cd4b-127">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-127">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="2cd4b-128">运算符</span><span class="sxs-lookup"><span data-stu-id="2cd4b-128">Operator</span></span>|==|  
|<span data-ttu-id="2cd4b-129">**发送端口属性：筛选器**</span><span class="sxs-lookup"><span data-stu-id="2cd4b-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="2cd4b-130">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="2cd4b-130">Value</span></span>|<span data-ttu-id="2cd4b-131">**对于交换**:</span><span class="sxs-lookup"><span data-stu-id="2cd4b-131">**For interchanges**:</span></span><br /><br /> <span data-ttu-id="2cd4b-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`或</span><span class="sxs-lookup"><span data-stu-id="2cd4b-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, or</span></span><br /><br /> <span data-ttu-id="2cd4b-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`或</span><span class="sxs-lookup"><span data-stu-id="2cd4b-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`,or</span></span><br /><br /> <span data-ttu-id="2cd4b-134">**对于确认**:</span><span class="sxs-lookup"><span data-stu-id="2cd4b-134">**For ACKs**:</span></span><br /><br /> <span data-ttu-id="2cd4b-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`或</span><span class="sxs-lookup"><span data-stu-id="2cd4b-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, or</span></span><br /><br /> <span data-ttu-id="2cd4b-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`或</span><span class="sxs-lookup"><span data-stu-id="2cd4b-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, or</span></span><br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a><span data-ttu-id="2cd4b-137">设置协议属性</span><span class="sxs-lookup"><span data-stu-id="2cd4b-137">Setting Agreement Properties</span></span>  
 <span data-ttu-id="2cd4b-138">创建发送端口后，你需要设置发送管道工作所需的协议属性。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-138">After creating the send port, you need to set the agreement properties required for the send pipeline to function.</span></span> <span data-ttu-id="2cd4b-139">这些属性设置中的多个页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2cd4b-139">These properties are set in various pages of the **Agreement Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd4b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cd4b-140">See Also</span></span>  
 [<span data-ttu-id="2cd4b-141">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="2cd4b-141">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)