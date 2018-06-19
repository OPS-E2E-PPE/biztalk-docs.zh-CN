---
title: 配置回退确认属性 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 216961dea0bdf4a67c550fba8a599eff2d0c89ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232829"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="a48f7-102">配置回退确认属性 (X 12)</span><span class="sxs-lookup"><span data-stu-id="a48f7-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="a48f7-103">在备选协议中，您可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何生成确认，以响应从参与方接收的 X12 编码的交换，以及返回到参与方的确认类型。</span><span class="sxs-lookup"><span data-stu-id="a48f7-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="a48f7-104">本节提供有关如何执行上述操作的说明。</span><span class="sxs-lookup"><span data-stu-id="a48f7-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a48f7-105">此处所述的确认属性同样适用于 HIPAA 确认。</span><span class="sxs-lookup"><span data-stu-id="a48f7-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a48f7-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a48f7-106">Prerequisites</span></span>  
 <span data-ttu-id="a48f7-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a48f7-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="a48f7-108">配置 X12 确认属性</span><span class="sxs-lookup"><span data-stu-id="a48f7-108">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="a48f7-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="a48f7-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="a48f7-110">在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**交换设置**部分中，单击**确认**.</span><span class="sxs-lookup"><span data-stu-id="a48f7-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="a48f7-111">选择**预期的 TA1**可向交换发件人返回技术 (TA1) 确认。</span><span class="sxs-lookup"><span data-stu-id="a48f7-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="a48f7-112">选择**997 预期**可向交换发件人返回功能 (997) 确认。</span><span class="sxs-lookup"><span data-stu-id="a48f7-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="a48f7-113">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a48f7-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48f7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a48f7-114">See Also</span></span>  
 [<span data-ttu-id="a48f7-115">配置 X12 回退协议属性交换处理</span><span class="sxs-lookup"><span data-stu-id="a48f7-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)