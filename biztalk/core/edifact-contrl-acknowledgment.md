---
title: EDIFACT CONTRL 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7808b02e5aebcf9f03e06a13ebbbcff8b1f43b0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350130"
---
# <a name="edifact-contrl-acknowledgment"></a><span data-ttu-id="f499f-102">EDIFACT CONTRL 确认</span><span class="sxs-lookup"><span data-stu-id="f499f-102">EDIFACT CONTRL Acknowledgment</span></span>
<span data-ttu-id="f499f-103">CONTRL 确认 (ACK) 用作 EDIFACT 编码消息的技术和功能确认。</span><span class="sxs-lookup"><span data-stu-id="f499f-103">The CONTRL acknowledgment (ACK) serves as both technical and functional acknowledgment for EDIFACT-encoded messages.</span></span> <span data-ttu-id="f499f-104">作为技术确认，CONTRL 消息指示交换的接收。</span><span class="sxs-lookup"><span data-stu-id="f499f-104">As a technical acknowledgment, the CONTRL message indicates receipt of an interchange.</span></span> <span data-ttu-id="f499f-105">作为功能确认，CONTRL 消息指示接受或拒绝收到的交换、 组或消息，与错误或不受支持的功能的列表。</span><span class="sxs-lookup"><span data-stu-id="f499f-105">As a functional acknowledgment, the CONTRL message indicates acceptance or rejection of the received interchange, group, or message, with a list of errors or unsupported functionality.</span></span>  
  
 <span data-ttu-id="f499f-106">完整 CONTRL 消息用作功能确认。</span><span class="sxs-lookup"><span data-stu-id="f499f-106">The full CONTRL message serves as the functional ACK.</span></span> <span data-ttu-id="f499f-107">功能确认的部分会重复使用的技术确认。</span><span class="sxs-lookup"><span data-stu-id="f499f-107">Sections of the functional ACK are reused for the technical ACK.</span></span> <span data-ttu-id="f499f-108">如果选择了技术和功能确认的参与方属性的发送方或全局属性中，BizTalk Server 将生成两个 CONTRL 消息： 一个技术 CONTRL 确认和功能 CONTRL 确认。</span><span class="sxs-lookup"><span data-stu-id="f499f-108">If you have selected both technical and functional ACKs in the party properties for a sending party or in global properties, BizTalk Server will generate two CONTRL messages: a technical CONTRL ACK and a functional CONTRL ACK.</span></span>  
  
 <span data-ttu-id="f499f-109">CONTRL 确认与 EFACT_\<版本号\>_CONTRL.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="f499f-109">The CONTRL ACK conforms to the EFACT_\<Version number\>_CONTRL.xsd schema.</span></span>  
  
## <a name="technical-acknowledgement"></a><span data-ttu-id="f499f-110">技术确认</span><span class="sxs-lookup"><span data-stu-id="f499f-110">Technical Acknowledgement</span></span>  
 <span data-ttu-id="f499f-111">技术确认指示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="f499f-111">A technical ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="f499f-112">已收到主题交换;</span><span class="sxs-lookup"><span data-stu-id="f499f-112">has received the subject interchange;</span></span>  
  
-   <span data-ttu-id="f499f-113">确认已选中以确保正确的语法; 复制到报告 UCI 段的数据元素的主题交换部分</span><span class="sxs-lookup"><span data-stu-id="f499f-113">acknowledges the parts of the subject interchange that have been checked in order to ensure that the data elements copied into the reporting UCI segment are syntactically correct;</span></span>  
  
-   <span data-ttu-id="f499f-114">已接受如下责任通知发件人的确认或拒绝的其他部分的主题交换;</span><span class="sxs-lookup"><span data-stu-id="f499f-114">has accepted responsibility for notifying the sender of acknowledgement or rejection of the other parts of the subject interchange;</span></span>  
  
-   <span data-ttu-id="f499f-115">已采取合理的预防措施确保发送方能收到相应通知。</span><span class="sxs-lookup"><span data-stu-id="f499f-115">and has taken reasonable precautions in order to ensure that the sender is so notified.</span></span>  
  
## <a name="functional-acknowledgement"></a><span data-ttu-id="f499f-116">功能确认</span><span class="sxs-lookup"><span data-stu-id="f499f-116">Functional Acknowledgement</span></span>  
 <span data-ttu-id="f499f-117">功能确认指示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="f499f-117">A functional ACK implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="f499f-118">已收到确认; 的交换的引用的级别 (s)</span><span class="sxs-lookup"><span data-stu-id="f499f-118">has received the referenced levels(s) of the interchange acknowledged;</span></span>  
  
- <span data-ttu-id="f499f-119">已签入能继续处理交换; 的已确认引用级别中没有任何致命语法错误</span><span class="sxs-lookup"><span data-stu-id="f499f-119">has checked that there are no fatal syntactic errors in the acknowledged referenced level that prevents further processing of the interchange;</span></span>  
  
- <span data-ttu-id="f499f-120">已签入所有组成部分已确认的服务段在语义上是都正确的 （是否未不报告任何错误）;</span><span class="sxs-lookup"><span data-stu-id="f499f-120">has checked that all acknowledged parts of service segments are semantically correct (if no errors are reported);</span></span>  
  
- <span data-ttu-id="f499f-121">将遵守与已确认引用级别的服务段; 中请求的操作</span><span class="sxs-lookup"><span data-stu-id="f499f-121">will comply with the actions requested in the acknowledged referenced-levels of the service segments;</span></span>  
  
- <span data-ttu-id="f499f-122">已接受比发送一条 CONTRL 消息，如果任何语法或语义错误，上文所述更高版本中检测到的相关部分或部分而无法处理其他某种原因而后的部件具有通过其他方式通知发件人的职责已确认中提交的 CONTRL 消息;</span><span class="sxs-lookup"><span data-stu-id="f499f-122">has accepted responsibility for notifying the sender by other means than sending a CONTRL message if any syntactic or semantic errors as described above, are later detected in the relevant part, or the part cannot be processed for some other reason after the part has been acknowledged in a submitted CONTRL message;</span></span>  
  
- <span data-ttu-id="f499f-123">已采取合理的预防措施确保检测到此类错误，并且发件人将收到通知。</span><span class="sxs-lookup"><span data-stu-id="f499f-123">and has taken reasonable precautions in order to ensure that such errors are detected and that the sender is notified.</span></span>  
  
  <span data-ttu-id="f499f-124">拒绝表示交换的收件人：</span><span class="sxs-lookup"><span data-stu-id="f499f-124">Rejection implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="f499f-125">无法确认主题交换或 CONTRL 消息中; 中指出的原因而的相关部分，</span><span class="sxs-lookup"><span data-stu-id="f499f-125">cannot acknowledge the subject interchange, or the relevant parts of it, for reasons indicated in the CONTRL message;</span></span>  
  
- <span data-ttu-id="f499f-126">并不需要任何进一步的操作中的主题交换被拒绝的一部分包含的业务信息。</span><span class="sxs-lookup"><span data-stu-id="f499f-126">and will not take any further action on business information contained in the rejected part of the subject interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f499f-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="f499f-127">In This Section</span></span>  
  
-   [<span data-ttu-id="f499f-128">作为技术确认的 EDIFACT CONTRL 消息</span><span class="sxs-lookup"><span data-stu-id="f499f-128">EDIFACT CONTRL Message as Technical Acknowledgment</span></span>](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [<span data-ttu-id="f499f-129">作为功能确认的 EDIFACT CONTRL 消息</span><span class="sxs-lookup"><span data-stu-id="f499f-129">EDIFACT CONTRL Message as Functional Acknowledgment</span></span>](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a><span data-ttu-id="f499f-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f499f-130">See Also</span></span>  
 [<span data-ttu-id="f499f-131">EDI 确认结构</span><span class="sxs-lookup"><span data-stu-id="f499f-131">EDI Acknowledgment Structure</span></span>](../core/edi-acknowledgment-structure.md)