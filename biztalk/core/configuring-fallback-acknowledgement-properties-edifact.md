---
title: 配置回退确认属性 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1422e524d9527b5e7e5362d5867654026cc03768
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974174"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a><span data-ttu-id="12fca-102">配置回退确认属性 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="12fca-102">Configuring Fallback Acknowledgement Properties (EDIFACT)</span></span>
<span data-ttu-id="12fca-103">在备选协议中，您可以指定将何种类型的确认返回参与方。</span><span class="sxs-lookup"><span data-stu-id="12fca-103">In the fallback agreement, you can specify what type of acknowledgment to return to a party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12fca-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="12fca-104">Prerequisites</span></span>  
 <span data-ttu-id="12fca-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="12fca-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="12fca-106">配置 EDIFACT 确认 (CONTRL) 属性</span><span class="sxs-lookup"><span data-stu-id="12fca-106">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1. <span data-ttu-id="12fca-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="12fca-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="12fca-108">在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="12fca-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3. <span data-ttu-id="12fca-109">选择**预期接收消息 (CONTRL)** 向交换发件人返回技术 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="12fca-109">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
4. <span data-ttu-id="12fca-110">选择**确认 (CONTRL) 预期**向交换发件人返回功能 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="12fca-110">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
5. <span data-ttu-id="12fca-111">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="12fca-111">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fca-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="12fca-112">See Also</span></span>  
 [<span data-ttu-id="12fca-113">为交换处理配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="12fca-113">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)