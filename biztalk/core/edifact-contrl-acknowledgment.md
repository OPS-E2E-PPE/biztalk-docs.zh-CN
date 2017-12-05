---
title: "EDIFACT CONTRL 确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddbc35fecd2412632f0c4a81750a3662e6e7bf11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="edifact-contrl-acknowledgment"></a><span data-ttu-id="b6ab9-102">EDIFACT CONTRL 确认</span><span class="sxs-lookup"><span data-stu-id="b6ab9-102">EDIFACT CONTRL Acknowledgment</span></span>
<span data-ttu-id="b6ab9-103">CONTRL 确认 (ACK) 用作 EDIFACT 编码消息的技术确认和功能确认。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-103">The CONTRL acknowledgment (ACK) serves as both technical and functional acknowledgment for EDIFACT-encoded messages.</span></span> <span data-ttu-id="b6ab9-104">作为技术确认，CONTRL 消息用于指示交换的接收。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-104">As a technical acknowledgment, the CONTRL message indicates receipt of an interchange.</span></span> <span data-ttu-id="b6ab9-105">作为功能确认，CONTRL 消息用错误或不支持功能的列表指示接收到的交换、组或消息是已接受还是拒绝。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-105">As a functional acknowledgment, the CONTRL message indicates acceptance or rejection of the received interchange, group, or message, with a list of errors or unsupported functionality.</span></span>  
  
 <span data-ttu-id="b6ab9-106">完整 CONTRL 消息用作功能确认。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-106">The full CONTRL message serves as the functional ACK.</span></span> <span data-ttu-id="b6ab9-107">功能确认的某些部分可再次用于技术确认。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-107">Sections of the functional ACK are reused for the technical ACK.</span></span> <span data-ttu-id="b6ab9-108">如果你选择了技术和功能确认中参与方属性为发送方或全局属性中，BizTalk 服务器将生成两条 CONTRL 消息： 技术的 CONTRL 确认和功能 CONTRL 确认使用</span><span class="sxs-lookup"><span data-stu-id="b6ab9-108">If you have selected both technical and functional ACKs in the party properties for a sending party or in global properties, BizTalk Server will generate two CONTRL messages: a technical CONTRL ACK and a functional CONTRL ACK.</span></span>  
  
 <span data-ttu-id="b6ab9-109">CONTRL 确认符合 EFACT_\<版本号\>_CONTRL.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-109">The CONTRL ACK conforms to the EFACT_\<Version number\>_CONTRL.xsd schema.</span></span>  
  
## <a name="technical-acknowledgement"></a><span data-ttu-id="b6ab9-110">技术确认</span><span class="sxs-lookup"><span data-stu-id="b6ab9-110">Technical Acknowledgement</span></span>  
 <span data-ttu-id="b6ab9-111">技术确认指示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="b6ab9-111">A technical ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="b6ab9-112">已收到主题交换；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-112">has received the subject interchange;</span></span>  
  
-   <span data-ttu-id="b6ab9-113">确认已检查的主题交换的各个部分，以确保复制到报告 UCI 段中的数据元素使用了正确的语法；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-113">acknowledges the parts of the subject interchange that have been checked in order to ensure that the data elements copied into the reporting UCI segment are syntactically correct;</span></span>  
  
-   <span data-ttu-id="b6ab9-114">已接受就主题交换的其他部分的确认或拒绝通知发送方这一责任；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-114">has accepted responsibility for notifying the sender of acknowledgement or rejection of the other parts of the subject interchange;</span></span>  
  
-   <span data-ttu-id="b6ab9-115">已采取合理的预防措施确保发送方能收到相应通知。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-115">and has taken reasonable precautions in order to ensure that the sender is so notified.</span></span>  
  
## <a name="functional-acknowledgement"></a><span data-ttu-id="b6ab9-116">功能确认</span><span class="sxs-lookup"><span data-stu-id="b6ab9-116">Functional Acknowledgement</span></span>  
 <span data-ttu-id="b6ab9-117">功能确认指示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="b6ab9-117">A functional ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="b6ab9-118">已收到所确认的交换的引用级别；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-118">has received the referenced levels(s) of the interchange acknowledged;</span></span>  
  
-   <span data-ttu-id="b6ab9-119">已检查在确认的引用级别中是否有可导致交换的进一步处理无法进行的致命语法错误；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-119">has checked that there are no fatal syntactic errors in the acknowledged referenced level that prevents further processing of the interchange;</span></span>  
  
-   <span data-ttu-id="b6ab9-120">已检查所有确认的服务段部分在语义上是否都是正确的（如果未报告错误，则正确）；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-120">has checked that all acknowledged parts of service segments are semantically correct (if no errors are reported);</span></span>  
  
-   <span data-ttu-id="b6ab9-121">将按照在服务段的已确认引用级别中请求的操作执行；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-121">will comply with the actions requested in the acknowledged referenced-levels of the service segments;</span></span>  
  
-   <span data-ttu-id="b6ab9-122">已接受如下责任：当以后在相关部分中检测到上述任何语法或语义错误时，或者在已在提交的 CONTRL 消息中确认相应部分之后由于其他原因而无法处理该部分时，通过发送 CONTRL 消息以外的方式通知发送方；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-122">has accepted responsibility for notifying the sender by other means than sending a CONTRL message if any syntactic or semantic errors as described above, are later detected in the relevant part, or the part cannot be processed for some other reason after the part has been acknowledged in a submitted CONTRL message;</span></span>  
  
-   <span data-ttu-id="b6ab9-123">已采取合理的预防措施确保能够检测到此类错误并相应通知发送方。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-123">and has taken reasonable precautions in order to ensure that such errors are detected and that the sender is notified.</span></span>  
  
 <span data-ttu-id="b6ab9-124">拒绝表示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="b6ab9-124">Rejection implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="b6ab9-125">由于 CONTRL 消息中指出的原因而无法确认主题交换或其相关部分；</span><span class="sxs-lookup"><span data-stu-id="b6ab9-125">cannot acknowledge the subject interchange, or the relevant parts of it, for reasons indicated in the CONTRL message;</span></span>  
  
-   <span data-ttu-id="b6ab9-126">不会对拒绝的主题交换部分中包含的业务信息进一步采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="b6ab9-126">and will not take any further action on business information contained in the rejected part of the subject interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6ab9-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6ab9-127">In This Section</span></span>  
  
-   [<span data-ttu-id="b6ab9-128">作为技术确认的 EDIFACT CONTRL 消息</span><span class="sxs-lookup"><span data-stu-id="b6ab9-128">EDIFACT CONTRL Message as Technical Acknowledgment</span></span>](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [<span data-ttu-id="b6ab9-129">作为功能确认的 EDIFACT CONTRL 消息</span><span class="sxs-lookup"><span data-stu-id="b6ab9-129">EDIFACT CONTRL Message as Functional Acknowledgment</span></span>](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6ab9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ab9-130">See Also</span></span>  
 [<span data-ttu-id="b6ab9-131">EDI 确认结构</span><span class="sxs-lookup"><span data-stu-id="b6ab9-131">EDI Acknowledgment Structure</span></span>](../core/edi-acknowledgment-structure.md)