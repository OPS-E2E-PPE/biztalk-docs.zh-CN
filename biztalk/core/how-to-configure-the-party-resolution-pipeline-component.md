---
title: 如何配置参与方解析管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248213"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a><span data-ttu-id="07b5e-102">如何配置参与方解析管道组件</span><span class="sxs-lookup"><span data-stu-id="07b5e-102">How to Configure the Party Resolution Pipeline Component</span></span>
<span data-ttu-id="07b5e-103">参与方解析管道组件用于将客户端的用户安全 ID 和证书主题映射到 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="07b5e-103">The Party Resolution pipeline component is used to map the user security ID and the certificate subject for the client to a BizTalk Server party.</span></span> <span data-ttu-id="07b5e-104">该映射用于加强对向 BizTalk Server 发送消息的参与方的验证。</span><span class="sxs-lookup"><span data-stu-id="07b5e-104">The mapping is used to enforce authentication of the parties who send messages to BizTalk Server.</span></span> <span data-ttu-id="07b5e-105">有关合作伙伴管理的详细信息，请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。</span><span class="sxs-lookup"><span data-stu-id="07b5e-105">For more information about partner management, see[How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07b5e-106">若要启用参与方解析管道组件以验证 Windows 用户，您必须向参与方添加 WindowsUser 别名。</span><span class="sxs-lookup"><span data-stu-id="07b5e-106">To enable the Party Resolution pipeline component to validate a Windows user, you must add the WindowsUser alias to a party.</span></span> <span data-ttu-id="07b5e-107">有关详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="07b5e-107">For more information, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a><span data-ttu-id="07b5e-108">配置参与方解析管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="07b5e-108">To configure the properties for the Party Resolution pipeline component</span></span>  
  
1.  <span data-ttu-id="07b5e-109">将参与方解析管道组件拖至接收管道的“解析参与方”阶段中。</span><span class="sxs-lookup"><span data-stu-id="07b5e-109">Drag the Party Resolution pipeline component into the ResolveParty stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="07b5e-110">在属性窗口中，在**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="07b5e-110">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="07b5e-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="07b5e-111">Use this</span></span>|<span data-ttu-id="07b5e-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="07b5e-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="07b5e-113">**解析由证书的参与方**</span><span class="sxs-lookup"><span data-stu-id="07b5e-113">**Resolve Party By Certificate**</span></span>|<span data-ttu-id="07b5e-114">设置为**True**如果你想要启用基于来自其中接收的消息的参与方的签名证书的指纹的参与方解析。</span><span class="sxs-lookup"><span data-stu-id="07b5e-114">Set to **True** if you want to enable party resolution based on the thumbprint of the signature certificate from the party from where the messages are received.</span></span><br /><br /> <span data-ttu-id="07b5e-115">默认值： **True**</span><span class="sxs-lookup"><span data-stu-id="07b5e-115">Default value: **True**</span></span>|  
    |<span data-ttu-id="07b5e-116">**SID 解析参与方**</span><span class="sxs-lookup"><span data-stu-id="07b5e-116">**Resolve Party By SID**</span></span>|<span data-ttu-id="07b5e-117">设置为**True**如果你想要启用基于发件人帐户的安全标识符 (SID) 的参与方解析。</span><span class="sxs-lookup"><span data-stu-id="07b5e-117">Set to **True** if you want to enable party resolution based on the security identifier (SID) of the sender account.</span></span><br /><br /> <span data-ttu-id="07b5e-118">如果这两个属性都设置为**True**、**解决方通过证书**属性优先于**通过 SID 解析方**属性，这意味着，如果这两个证书，并且该 SID 的可用，使用证书使用者。</span><span class="sxs-lookup"><span data-stu-id="07b5e-118">If both properties are set to **True**, the **Resolve Party By Certificate** property takes precedence over the **Resolve Party By SID** property, meaning that if both the certificate and the SID are available, the certificate subject is used.</span></span> <span data-ttu-id="07b5e-119">如果无法通过证书使用者解析当事方，该组件不会回退**通过 SID 解析方**属性，且默认值 (s-1-5-7) 标为**BTS。SourcePartyID**。</span><span class="sxs-lookup"><span data-stu-id="07b5e-119">If the party cannot be resolved by using the certificate subject, the component does not fall back to the **Resolve Party By SID** property, and the default value (s-1-5-7) is stamped for **BTS.SourcePartyID**.</span></span><br /><br /> <span data-ttu-id="07b5e-120">默认值： **True**</span><span class="sxs-lookup"><span data-stu-id="07b5e-120">Default value: **True**</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="07b5e-121">如果你使用的 BizTalk 消息队列的适配器和想要解析的参与方基于用户名称，将设置**解决方通过证书**到**False**和**通过 SID 解析方**到**True**。</span><span class="sxs-lookup"><span data-stu-id="07b5e-121">If you use the BizTalk Message Queuing adapter and want to resolve the party based on user name, set **Resolve Party By Certificate** to **False** and **Resolve Party By SID** to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b5e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b5e-122">See Also</span></span>  
 <span data-ttu-id="07b5e-123">[参与方解析管道组件](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="07b5e-123">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="07b5e-124">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="07b5e-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="07b5e-125">自定义参与方解析 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="07b5e-125">Custom Party Resolution (BizTalk Server Sample)</span></span>](../core/custom-party-resolution-biztalk-server-sample.md)