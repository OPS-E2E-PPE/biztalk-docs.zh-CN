---
title: 配置回退确认属性 (X12) |Microsoft Docs
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
ms.openlocfilehash: 26ba465598f94f5f9ff41e74d50962a71b0ad979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391251"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="2b13f-102">配置回退确认属性 (X 12)</span><span class="sxs-lookup"><span data-stu-id="2b13f-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="2b13f-103">在后备协议中，您可以指定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]响应从参与方和类型的确认返回到参与方接收的 X12 编码交换而生成确认。</span><span class="sxs-lookup"><span data-stu-id="2b13f-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="2b13f-104">本部分将说明了如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2b13f-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b13f-105">此处所述的确认属性同样适用于 HIPAA 确认。</span><span class="sxs-lookup"><span data-stu-id="2b13f-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b13f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="2b13f-106">Prerequisites</span></span>  
 <span data-ttu-id="2b13f-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="2b13f-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="2b13f-108">若要配置 X12 确认属性</span><span class="sxs-lookup"><span data-stu-id="2b13f-108">To configure X12 ACK properties</span></span>  
  
1. <span data-ttu-id="2b13f-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="2b13f-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="2b13f-110">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**确认**.</span><span class="sxs-lookup"><span data-stu-id="2b13f-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3. <span data-ttu-id="2b13f-111">选择**预期的 TA1**向交换发件人返回技术 (TA1) 确认。</span><span class="sxs-lookup"><span data-stu-id="2b13f-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4. <span data-ttu-id="2b13f-112">选择**预期的 997**向交换发件人返回功能 (997) 确认。</span><span class="sxs-lookup"><span data-stu-id="2b13f-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5. <span data-ttu-id="2b13f-113">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2b13f-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b13f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b13f-114">See Also</span></span>  
 [<span data-ttu-id="2b13f-115">为交换处理配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="2b13f-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)