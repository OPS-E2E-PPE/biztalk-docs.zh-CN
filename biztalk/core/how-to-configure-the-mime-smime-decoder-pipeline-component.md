---
title: 如何配置 MIME-SMIME 解码器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, attachments
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component], configuring
- messages, verifying
- messages, decoding
- messages, digital signatures
- messages, security
ms.assetid: bfd44893-f1c3-4524-abc6-f820b8c0ef07
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cde85adeec5d1155afdba28d2e7ca2bf5647983d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386028"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a><span data-ttu-id="b0a90-102">如何配置 MIME-SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="b0a90-102">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="b0a90-103">MIME/SMIME 解码器管道组件用于解码和解密 MIME/SMIME 编码的消息和验证数字签名的签名消息。</span><span class="sxs-lookup"><span data-stu-id="b0a90-103">The MIME/SMIME Decoder pipeline component is used for decoding and decrypting MIME/SMIME encoded messages and for verifying digital signatures of signed messages.</span></span> <span data-ttu-id="b0a90-104">当外部合作伙伴与 BizTalk Server 之间需要安全的文档交换时，此组件非常有用。</span><span class="sxs-lookup"><span data-stu-id="b0a90-104">This component is useful when secured document interchange is needed between external partners and BizTalk Server.</span></span> <span data-ttu-id="b0a90-105">此组件还可用于接收带附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="b0a90-105">This component can also be used for receiving messages with attachments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0a90-106">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，MIME/SMIME 解码器管道组件不具有支持本机 64 位模式。</span><span class="sxs-lookup"><span data-stu-id="b0a90-106">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the MIME/SMIME decoder pipeline component does not have native 64-bit support.</span></span>  <span data-ttu-id="b0a90-107">这意味着，此组件必须在 32 位仿真模式进程 (WOW64) 中运行。</span><span class="sxs-lookup"><span data-stu-id="b0a90-107">This means that this component must be run in a 32-bit emulation mode process (WOW64).</span></span>  <span data-ttu-id="b0a90-108">这意味着，必须在 32 位仿真模式下运行此解码器组件 （或它的一部分的接收管道） 运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="b0a90-108">This implies that the host instance in which this decoder component (or the receive pipeline of which it is a part) runs must be running in 32-bit emulation mode.</span></span>  <span data-ttu-id="b0a90-109">要注意的性能 （和其他） 的此限制对此相同的主机实例中运行的 BizTalk 的其他元素的含义。</span><span class="sxs-lookup"><span data-stu-id="b0a90-109">Be aware of the performance (and other) implications of this restriction for other elements of BizTalk running in this same host instance.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="b0a90-110">POP3 适配器中还使用 MIME/SMIME 解码器组件。</span><span class="sxs-lookup"><span data-stu-id="b0a90-110">The MIME/SMIME decoder component is also used within the POP3 adapter.</span></span>  <span data-ttu-id="b0a90-111">因此，运行 POP3 适配器的主机实例存在相同的本机 64 位支持限制。</span><span class="sxs-lookup"><span data-stu-id="b0a90-111">As a result, the same native 64-bit support restriction exists for the host instance in which the POP3 adapter runs.</span></span>  <span data-ttu-id="b0a90-112">有关 POP3 适配器的信息，请参阅[POP3 适配器](../core/pop3-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b0a90-112">See related information about the POP3 adapter in [POP3 Adapter](../core/pop3-adapter.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a><span data-ttu-id="b0a90-113">若要配置 MIME/SMIME 解码器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="b0a90-113">To configure the properties for the MIME/SMIME Decoder pipeline component</span></span>  
  
1.  <span data-ttu-id="b0a90-114">将 MIME/SMIME 解码器管道组件拖至接收管道的解码阶段。</span><span class="sxs-lookup"><span data-stu-id="b0a90-114">Drag the MIME/SMIME Decoder pipeline component into the Decode stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="b0a90-115">在属性窗口中**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="b0a90-115">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="b0a90-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b0a90-116">Use this</span></span>|<span data-ttu-id="b0a90-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b0a90-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b0a90-118">**允许非 MIME 消息**</span><span class="sxs-lookup"><span data-stu-id="b0a90-118">**Allow Non MIME Message**</span></span>|<span data-ttu-id="b0a90-119">将此属性设置为 **，则返回 True**如果希望接收管道能够接收不是 MIME 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="b0a90-119">Set this property to **True** if you expect that the receive pipeline may get messages that are not MIME encoded.</span></span> <span data-ttu-id="b0a90-120">在不同的形式，例如，MIME 编码或普通 XML 中接收消息的管道中使用 MIME/SMIME 解码器管道组件时，此选项非常有用。</span><span class="sxs-lookup"><span data-stu-id="b0a90-120">This option is useful when the MIME/SMIME Decoder pipeline component is used in a pipeline that receives messages in different forms, for example, MIME encoded or plain XML.</span></span> <span data-ttu-id="b0a90-121">默认情况下，此属性设置为**False**，含义组件生成一个错误，如果收到非 MIME 编码的消息输入。</span><span class="sxs-lookup"><span data-stu-id="b0a90-121">By default, this property is set to **False**, meaning that the component generates an error if it receives a non-MIME encoded message on input.</span></span> <span data-ttu-id="b0a90-122">**注意：** MIME 解码器扫描传入的消息搜索"Mime-version"标头的第一个 1024 字节。</span><span class="sxs-lookup"><span data-stu-id="b0a90-122">**Note:**  The MIME decoder scans the first 1024 bytes of the incoming message to search for the "MIME-Version" header.</span></span> <span data-ttu-id="b0a90-123">如果找不到此标头，该消息被视为非 MIME 消息。</span><span class="sxs-lookup"><span data-stu-id="b0a90-123">If this header is not found, the message is treated as a non-MIME message.</span></span> <br /><br /> <span data-ttu-id="b0a90-124">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="b0a90-124">Default value: **False**</span></span>|  
    |<span data-ttu-id="b0a90-125">**正文部分内容类型**</span><span class="sxs-lookup"><span data-stu-id="b0a90-125">**Body part content type**</span></span>|<span data-ttu-id="b0a90-126">指示 MIME 部分的内容类型。</span><span class="sxs-lookup"><span data-stu-id="b0a90-126">Indicates the content type of the MIME part.</span></span> <span data-ttu-id="b0a90-127">与此内容类型的 MIME 部分将成为 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="b0a90-127">The MIME part with this content type will become the body part of the BizTalk message.</span></span><br /><br /> <span data-ttu-id="b0a90-128">默认值：None</span><span class="sxs-lookup"><span data-stu-id="b0a90-128">Default value: None</span></span>|  
    |<span data-ttu-id="b0a90-129">**正文部分索引**</span><span class="sxs-lookup"><span data-stu-id="b0a90-129">**Body part index**</span></span>|<span data-ttu-id="b0a90-130">指示 MIME 部分列表中的基于 1 的索引。</span><span class="sxs-lookup"><span data-stu-id="b0a90-130">Indicates the 1-based index into the MIME part list.</span></span> <span data-ttu-id="b0a90-131">在列表中此索引处的 MIME 部分将成为 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="b0a90-131">The MIME part at this index in the list will become the body part of the BizTalk message.</span></span> <span data-ttu-id="b0a90-132">若要禁用按索引选择正文部分，使用值**0**。</span><span class="sxs-lookup"><span data-stu-id="b0a90-132">To disable the selection of body part by index, use a value of **0**.</span></span><br /><br /> <span data-ttu-id="b0a90-133">默认值：**0**</span><span class="sxs-lookup"><span data-stu-id="b0a90-133">Default value: **0**</span></span>|  
    |<span data-ttu-id="b0a90-134">**检查吊销列表**</span><span class="sxs-lookup"><span data-stu-id="b0a90-134">**Check Revocation List**</span></span>|<span data-ttu-id="b0a90-135">将此属性设置为 **，则返回 True**如果你想要检查证书吊销列表中的发件人用于发送到 BizTalk Server 的消息进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="b0a90-135">Set this property to **True** if you want to check the certificate revocation list for the certificates that senders use for signing messages that are being sent to BizTalk Server.</span></span> <span data-ttu-id="b0a90-136">如果禁用此选项会增加该组件的性能。</span><span class="sxs-lookup"><span data-stu-id="b0a90-136">Disabling this option increases the performance of the component.</span></span><br /><br /> <span data-ttu-id="b0a90-137">与证书关联的证书吊销列表从远程网站 (例如 Verisign.com) 下载。</span><span class="sxs-lookup"><span data-stu-id="b0a90-137">The certificate revocation list associated with a certificate is downloaded from a remote Web site (for example, Verisign.com).</span></span> <span data-ttu-id="b0a90-138">如果 BizTalk Server 无法连接到远程网站中，管道中的消息失败。</span><span class="sxs-lookup"><span data-stu-id="b0a90-138">If the BizTalk Server cannot connect to the remote Web site, the message fails in the pipeline.</span></span><br /><br /> <span data-ttu-id="b0a90-139">默认值：**True**</span><span class="sxs-lookup"><span data-stu-id="b0a90-139">Default value: **True**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a90-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a90-140">See Also</span></span>  
 <span data-ttu-id="b0a90-141">[MIME-SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b0a90-141">[MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md) </span></span>  
 <span data-ttu-id="b0a90-142">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b0a90-142">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="b0a90-143">[MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b0a90-143">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="b0a90-144">MIME（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="b0a90-144">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)