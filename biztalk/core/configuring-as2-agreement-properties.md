---
title: 配置 AS2 协议属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6f09f85b726869e98712abf354ad3943ce97a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233045"
---
# <a name="configuring-as2-agreement-properties"></a><span data-ttu-id="efde7-102">配置 AS2 确认属性</span><span class="sxs-lookup"><span data-stu-id="efde7-102">Configuring AS2 Agreement Properties</span></span>
<span data-ttu-id="efde7-103">本部分介绍 AS2 传输协议属性。</span><span class="sxs-lookup"><span data-stu-id="efde7-103">This section describes AS2 transport agreement properties.</span></span> <span data-ttu-id="efde7-104">作为传输协议设置的一部分，您还可以定义消息是否已经标记，以及消息是否已经加密等。</span><span class="sxs-lookup"><span data-stu-id="efde7-104">As part of the transport protocol settings, you can also define whether the message should be signed, whether the message should be encrypted, etc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efde7-105">配置 AS2 协议是可选的。</span><span class="sxs-lookup"><span data-stu-id="efde7-105">Configuring an AS2 agreement is optional.</span></span> <span data-ttu-id="efde7-106">AS2 协议定义该消息是如何使用 AS2 协议进行传输的。</span><span class="sxs-lookup"><span data-stu-id="efde7-106">An AS2 agreement defines how the messages are transferred using the AS2 protocol.</span></span> <span data-ttu-id="efde7-107">如果贸易合作伙伴决定使用任何其他协议来传输消息，可以选择不定义 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="efde7-107">If the trading partners decide to use any other transport protocol to transfer messages, they can choose not to define an AS2 agreement.</span></span> <span data-ttu-id="efde7-108">但是，贸易合作伙伴必须定义一个管理形成和编码消息方式的编码协议。</span><span class="sxs-lookup"><span data-stu-id="efde7-108">However, the trading partners must define an encoding agreement that governs how the messages are formed and encoded.</span></span> <span data-ttu-id="efde7-109">有关编码的协议的详细信息，请参阅[配置编码协议属性](../core/configuring-encoding-agreement-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="efde7-109">For more information about encoding agreements, see [Configuring Encoding Agreement Properties](../core/configuring-encoding-agreement-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efde7-110">每次在协议中更改 AS2 设置时，都必须重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例，更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="efde7-110">Every time you change an AS2 setting in an agreement, you must restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance for the changes to take effect.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="efde7-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="efde7-111">In This Section</span></span>  
  
-   [<span data-ttu-id="efde7-112">配置常规设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-112">Configuring General Settings (AS2)</span></span>](../core/configuring-general-settings-as2.md)  
  
-   [<span data-ttu-id="efde7-113">配置标识符 (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-113">Configuring Identifiers (AS2)</span></span>](../core/configuring-identifiers-as2.md)  
  
-   [<span data-ttu-id="efde7-114">配置验证（AS2）</span><span class="sxs-lookup"><span data-stu-id="efde7-114">Configuring Validation (AS2)</span></span>](../core/configuring-validation-as2.md)  
  
-   [<span data-ttu-id="efde7-115">配置确认 (MDN) (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-115">Configuring Acknowledgements (MDNs) (AS2)</span></span>](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [<span data-ttu-id="efde7-116">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-116">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)  
  
-   [<span data-ttu-id="efde7-117">配置签名证书 (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-117">Configuring Signature Certificates (AS2)</span></span>](../core/configuring-signature-certificates-as2.md)  
  
-   [<span data-ttu-id="efde7-118">配置发送端口关联 (AS2)</span><span class="sxs-lookup"><span data-stu-id="efde7-118">Configuring Send Port Association (AS2)</span></span>](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="efde7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efde7-119">See Also</span></span>  
 [<span data-ttu-id="efde7-120">配置 AS2 属性</span><span class="sxs-lookup"><span data-stu-id="efde7-120">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)