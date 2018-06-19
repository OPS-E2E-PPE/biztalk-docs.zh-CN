---
title: 配置回退确认属性 (EDIFACT) |Microsoft 文档
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
ms.openlocfilehash: 5d9369eb7fff1a6217da774aaf62af6e036d0abd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233013"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a><span data-ttu-id="82477-102">配置回退确认属性 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="82477-102">Configuring Fallback Acknowledgement Properties (EDIFACT)</span></span>
<span data-ttu-id="82477-103">在备选协议中，您可以指定将何种类型的确认返回参与方。</span><span class="sxs-lookup"><span data-stu-id="82477-103">In the fallback agreement, you can specify what type of acknowledgment to return to a party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82477-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="82477-104">Prerequisites</span></span>  
 <span data-ttu-id="82477-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="82477-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="82477-106">配置 EDIFACT 确认 (CONTRL) 属性</span><span class="sxs-lookup"><span data-stu-id="82477-106">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="82477-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="82477-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="82477-108">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="82477-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="82477-109">选择**收到预期消息 (CONTRL)** 可向交换发件人返回技术 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="82477-109">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="82477-110">选择**确认 (CONTRL) 预期**可向交换发件人返回功能 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="82477-110">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="82477-111">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="82477-111">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82477-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82477-112">See Also</span></span>  
 [<span data-ttu-id="82477-113">为交换处理配置 EDIFACT 回退协议属性</span><span class="sxs-lookup"><span data-stu-id="82477-113">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)