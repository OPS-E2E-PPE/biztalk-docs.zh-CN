---
title: 如何配置 MIME SMIME 解码器管道组件 |Microsoft 文档
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
ms.openlocfilehash: a32137528de5ea18ea5698ab823c2e703651b71b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249717"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a><span data-ttu-id="872db-102">如何配置 MIME SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="872db-102">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="872db-103">MIME/SMIME 解码器管道组件用于解码和解密 MIME/SMIME 编码的消息和验证签名消息的数字签名。</span><span class="sxs-lookup"><span data-stu-id="872db-103">The MIME/SMIME Decoder pipeline component is used for decoding and decrypting MIME/SMIME encoded messages and for verifying digital signatures of signed messages.</span></span> <span data-ttu-id="872db-104">当外部合作伙伴与 BizTalk Server 之间需要进行安全文档交换时，此组件非常有用。</span><span class="sxs-lookup"><span data-stu-id="872db-104">This component is useful when secured document interchange is needed between external partners and BizTalk Server.</span></span> <span data-ttu-id="872db-105">此组件还可用于接收带附件的消息。</span><span class="sxs-lookup"><span data-stu-id="872db-105">This component can also be used for receiving messages with attachments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="872db-106">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，MIME/SMIME 解码器管道组件将不再支持本机 64 位模式。</span><span class="sxs-lookup"><span data-stu-id="872db-106">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the MIME/SMIME decoder pipeline component does not have native 64-bit support.</span></span>  <span data-ttu-id="872db-107">这意味着此组件必须运行在 32 位仿真模式进程 (WOW64) 中。</span><span class="sxs-lookup"><span data-stu-id="872db-107">This means that this component must be run in a 32-bit emulation mode process (WOW64).</span></span>  <span data-ttu-id="872db-108">这意味着运行此解码器组件（或其所属的接收管道）的主机实例必须以 32 位仿真模式运行。</span><span class="sxs-lookup"><span data-stu-id="872db-108">This implies that the host instance in which this decoder component (or the receive pipeline of which it is a part) runs must be running in 32-bit emulation mode.</span></span>  <span data-ttu-id="872db-109">请注意此限制对运行在此主机实例中的其他 BizTalk 元素性能（和其他方面）的影响。</span><span class="sxs-lookup"><span data-stu-id="872db-109">Be aware of the performance (and other) implications of this restriction for other elements of BizTalk running in this same host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="872db-110">MIME/SMIME 解码器组件也用于 POP3 适配器中。</span><span class="sxs-lookup"><span data-stu-id="872db-110">The MIME/SMIME decoder component is also used within the POP3 adapter.</span></span>  <span data-ttu-id="872db-111">因此，对于运行 POP3 适配器的主机实例，也存在同样的本机 64 位支持限制。</span><span class="sxs-lookup"><span data-stu-id="872db-111">As a result, the same native 64-bit support restriction exists for the host instance in which the POP3 adapter runs.</span></span>  <span data-ttu-id="872db-112">请参阅关于 POP3 适配器中的相关的信息[POP3 适配器](../core/pop3-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="872db-112">See related information about the POP3 adapter in [POP3 Adapter](../core/pop3-adapter.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a><span data-ttu-id="872db-113">配置 MIME/SMIME 解码器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="872db-113">To configure the properties for the MIME/SMIME Decoder pipeline component</span></span>  
  
1.  <span data-ttu-id="872db-114">将 MIME/SMIME 解码器管道组件拖至接收管道的“解码”阶段。</span><span class="sxs-lookup"><span data-stu-id="872db-114">Drag the MIME/SMIME Decoder pipeline component into the Decode stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="872db-115">在属性窗口中，在**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="872db-115">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="872db-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="872db-116">Use this</span></span>|<span data-ttu-id="872db-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="872db-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="872db-118">**允许非 MIME 消息**</span><span class="sxs-lookup"><span data-stu-id="872db-118">**Allow Non MIME Message**</span></span>|<span data-ttu-id="872db-119">将此属性设置为**True**如果希望接收管道可能会收到不 MIME 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="872db-119">Set this property to **True** if you expect that the receive pipeline may get messages that are not MIME encoded.</span></span> <span data-ttu-id="872db-120">如果使用 MIME/SMIME 解码器管道组件的管道接收不同格式的消息，例如 MIME 编码或普通 XML 消息，则应使用此选项。</span><span class="sxs-lookup"><span data-stu-id="872db-120">This option is useful when the MIME/SMIME Decoder pipeline component is used in a pipeline that receives messages in different forms, for example, MIME encoded or plain XML.</span></span> <span data-ttu-id="872db-121">默认情况下，此属性设置为**False**，输入消息编码的组件生成一个错误，如果它收到非 MIME 的含义。</span><span class="sxs-lookup"><span data-stu-id="872db-121">By default, this property is set to **False**, meaning that the component generates an error if it receives a non-MIME encoded message on input.</span></span> <span data-ttu-id="872db-122">**注意：** MIME 解码器扫描以搜索"MIME 版本"标头的传入消息前 1024 个字节。</span><span class="sxs-lookup"><span data-stu-id="872db-122">**Note:**  The MIME decoder scans the first 1024 bytes of the incoming message to search for the "MIME-Version" header.</span></span> <span data-ttu-id="872db-123">如果找不到此头部，则消息将被视为非 MIME 消息。</span><span class="sxs-lookup"><span data-stu-id="872db-123">If this header is not found, the message is treated as a non-MIME message.</span></span> <br /><br /> <span data-ttu-id="872db-124">默认值： **False**</span><span class="sxs-lookup"><span data-stu-id="872db-124">Default value: **False**</span></span>|  
    |<span data-ttu-id="872db-125">**正文部分内容类型**</span><span class="sxs-lookup"><span data-stu-id="872db-125">**Body part content type**</span></span>|<span data-ttu-id="872db-126">指示 MIME 部分的内容类型。</span><span class="sxs-lookup"><span data-stu-id="872db-126">Indicates the content type of the MIME part.</span></span> <span data-ttu-id="872db-127">与此内容类型的 MIME 部分将变得 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="872db-127">The MIME part with this content type will become the body part of the BizTalk message.</span></span><br /><br /> <span data-ttu-id="872db-128">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="872db-128">Default value: None</span></span>|  
    |<span data-ttu-id="872db-129">**正文部分索引**</span><span class="sxs-lookup"><span data-stu-id="872db-129">**Body part index**</span></span>|<span data-ttu-id="872db-130">指示 MIME 部分列表中的基于 1 的索引。</span><span class="sxs-lookup"><span data-stu-id="872db-130">Indicates the 1-based index into the MIME part list.</span></span> <span data-ttu-id="872db-131">此列表中的索引位置的 MIME 部分将变得 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="872db-131">The MIME part at this index in the list will become the body part of the BizTalk message.</span></span> <span data-ttu-id="872db-132">若要按索引禁用选择的正文部分，使用值**0**。</span><span class="sxs-lookup"><span data-stu-id="872db-132">To disable the selection of body part by index, use a value of **0**.</span></span><br /><br /> <span data-ttu-id="872db-133">默认值： **0**</span><span class="sxs-lookup"><span data-stu-id="872db-133">Default value: **0**</span></span>|  
    |<span data-ttu-id="872db-134">**检查吊销列表**</span><span class="sxs-lookup"><span data-stu-id="872db-134">**Check Revocation List**</span></span>|<span data-ttu-id="872db-135">将此属性设置为**True**如果你想要检查证书吊销列表中的发件人将用于对发送到 BizTalk Server 的消息进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="872db-135">Set this property to **True** if you want to check the certificate revocation list for the certificates that senders use for signing messages that are being sent to BizTalk Server.</span></span> <span data-ttu-id="872db-136">禁用此选项可提高该组件的性能。</span><span class="sxs-lookup"><span data-stu-id="872db-136">Disabling this option increases the performance of the component.</span></span><br /><br /> <span data-ttu-id="872db-137">与证书关联的证书吊销列表从远程网站（例如 Verisign.com）下载。</span><span class="sxs-lookup"><span data-stu-id="872db-137">The certificate revocation list associated with a certificate is downloaded from a remote Web site (for example, Verisign.com).</span></span> <span data-ttu-id="872db-138">如果 BizTalk Server 无法连接远程网站，则该消息在管道中将失败。</span><span class="sxs-lookup"><span data-stu-id="872db-138">If the BizTalk Server cannot connect to the remote Web site, the message fails in the pipeline.</span></span><br /><br /> <span data-ttu-id="872db-139">默认值： **True**</span><span class="sxs-lookup"><span data-stu-id="872db-139">Default value: **True**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="872db-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="872db-140">See Also</span></span>  
 <span data-ttu-id="872db-141">[MIME SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="872db-141">[MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md) </span></span>  
 <span data-ttu-id="872db-142">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="872db-142">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="872db-143">[MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="872db-143">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="872db-144">MIME （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="872db-144">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)