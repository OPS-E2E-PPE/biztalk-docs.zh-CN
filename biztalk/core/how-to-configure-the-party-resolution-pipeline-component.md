---
title: 如何配置参与方解析管道组件 |Microsoft Docs
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
ms.openlocfilehash: e9c5c56dbb5ae5c74bfefca9554d20c3f4f10afc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340766"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a><span data-ttu-id="93653-102">如何配置参与方解析管道组件</span><span class="sxs-lookup"><span data-stu-id="93653-102">How to Configure the Party Resolution Pipeline Component</span></span>
<span data-ttu-id="93653-103">参与方解析管道组件用于将用户安全 ID 和客户端证书使用者映射到 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="93653-103">The Party Resolution pipeline component is used to map the user security ID and the certificate subject for the client to a BizTalk Server party.</span></span> <span data-ttu-id="93653-104">若要强制实施的参与方将消息发送到 BizTalk Server 的身份验证，使用的映射。</span><span class="sxs-lookup"><span data-stu-id="93653-104">The mapping is used to enforce authentication of the parties who send messages to BizTalk Server.</span></span> <span data-ttu-id="93653-105">有关合作伙伴管理的详细信息，请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。</span><span class="sxs-lookup"><span data-stu-id="93653-105">For more information about partner management, see[How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93653-106">若要启用参与方解析管道组件以验证 Windows 用户，必须向参与方添加 WindowsUser 别名。</span><span class="sxs-lookup"><span data-stu-id="93653-106">To enable the Party Resolution pipeline component to validate a Windows user, you must add the WindowsUser alias to a party.</span></span> <span data-ttu-id="93653-107">有关详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="93653-107">For more information, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a><span data-ttu-id="93653-108">若要配置参与方解析管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="93653-108">To configure the properties for the Party Resolution pipeline component</span></span>  
  
1.  <span data-ttu-id="93653-109">将参与方解析管道组件拖至接收管道解析参与方阶段。</span><span class="sxs-lookup"><span data-stu-id="93653-109">Drag the Party Resolution pipeline component into the ResolveParty stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="93653-110">在属性窗口中**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="93653-110">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="93653-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="93653-111">Use this</span></span>|<span data-ttu-id="93653-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="93653-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="93653-113">**证书解析参与方**</span><span class="sxs-lookup"><span data-stu-id="93653-113">**Resolve Party By Certificate**</span></span>|<span data-ttu-id="93653-114">设置为 **，则返回 True**如果你想要启用根据从其接收消息的参与方的签名证书的指纹的参与方解析。</span><span class="sxs-lookup"><span data-stu-id="93653-114">Set to **True** if you want to enable party resolution based on the thumbprint of the signature certificate from the party from where the messages are received.</span></span><br /><br /> <span data-ttu-id="93653-115">默认值：**True**</span><span class="sxs-lookup"><span data-stu-id="93653-115">Default value: **True**</span></span>|  
    |<span data-ttu-id="93653-116">**SID 解析参与方**</span><span class="sxs-lookup"><span data-stu-id="93653-116">**Resolve Party By SID**</span></span>|<span data-ttu-id="93653-117">设置为 **，则返回 True**如果你想要启用根据发件人帐户的安全标识符 (SID) 的参与方解析。</span><span class="sxs-lookup"><span data-stu-id="93653-117">Set to **True** if you want to enable party resolution based on the security identifier (SID) of the sender account.</span></span><br /><br /> <span data-ttu-id="93653-118">如果这两个属性都设置为 **，则返回 True**，则**通过证书解析参与方**属性优先于**通过 SID 解析参与方**属性; 也就是说，如果两个证书和 SID 均可用，则使用证书使用者。</span><span class="sxs-lookup"><span data-stu-id="93653-118">If both properties are set to **True**, the **Resolve Party By Certificate** property takes precedence over the **Resolve Party By SID** property, meaning that if both the certificate and the SID are available, the certificate subject is used.</span></span> <span data-ttu-id="93653-119">如果使用证书主题无法解析参与方，该组件不会回退**通过 SID 解析参与方**属性和默认值 (s-1-5-7) 标记为**BTS。SourcePartyID**。</span><span class="sxs-lookup"><span data-stu-id="93653-119">If the party cannot be resolved by using the certificate subject, the component does not fall back to the **Resolve Party By SID** property, and the default value (s-1-5-7) is stamped for **BTS.SourcePartyID**.</span></span><br /><br /> <span data-ttu-id="93653-120">默认值：**True**</span><span class="sxs-lookup"><span data-stu-id="93653-120">Default value: **True**</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="93653-121">如果使用了 BizTalk 消息队列适配器并且想要解析的参与方基于用户名称，则设置**通过证书解析参与方**到**False**并**通过 SID 解析参与方**到 **，则返回 true**。</span><span class="sxs-lookup"><span data-stu-id="93653-121">If you use the BizTalk Message Queuing adapter and want to resolve the party based on user name, set **Resolve Party By Certificate** to **False** and **Resolve Party By SID** to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93653-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="93653-122">See Also</span></span>  
 <span data-ttu-id="93653-123">[参与方解析管道组件](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="93653-123">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="93653-124">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="93653-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="93653-125">自定义参与方解析（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="93653-125">Custom Party Resolution (BizTalk Server Sample)</span></span>](../core/custom-party-resolution-biztalk-server-sample.md)