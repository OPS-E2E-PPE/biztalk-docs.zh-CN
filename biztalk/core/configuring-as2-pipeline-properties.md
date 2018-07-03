---
title: 配置 AS2 管道属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2bb679e4e150382cd8ff3e80c838d269ba908f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988870"
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="149b0-102">配置 AS2 管道属性</span><span class="sxs-lookup"><span data-stu-id="149b0-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="149b0-103">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定解析为已发送交换或已接收交换的协议时，将使用管道属性来处理传入或传出的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="149b0-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="149b0-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="149b0-104">Prerequisites</span></span>  
 <span data-ttu-id="149b0-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="149b0-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="149b0-106">AS2 管道属性</span><span class="sxs-lookup"><span data-stu-id="149b0-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="149b0-107">可在 AS2 管道中设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="149b0-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="149b0-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="149b0-108">Property</span></span>|<span data-ttu-id="149b0-109">改用</span><span class="sxs-lookup"><span data-stu-id="149b0-109">Use</span></span>|<span data-ttu-id="149b0-110">值</span><span class="sxs-lookup"><span data-stu-id="149b0-110">Values</span></span>|<span data-ttu-id="149b0-111">管道/阶段</span><span class="sxs-lookup"><span data-stu-id="149b0-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="149b0-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="149b0-112">ContentTransferEncoding</span></span>|<span data-ttu-id="149b0-113">指示将采用何种方法以 ASCII 文本格式表示二进制数据。</span><span class="sxs-lookup"><span data-stu-id="149b0-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="149b0-114">8bit（默认值）</span><span class="sxs-lookup"><span data-stu-id="149b0-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="149b0-115">7bit</span><span class="sxs-lookup"><span data-stu-id="149b0-115">7bit</span></span><br /><br /> <span data-ttu-id="149b0-116">8bit</span><span class="sxs-lookup"><span data-stu-id="149b0-116">8bit</span></span>|<span data-ttu-id="149b0-117">AS2EdiSend/编码</span><span class="sxs-lookup"><span data-stu-id="149b0-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="149b0-118">AS2Send/编码</span><span class="sxs-lookup"><span data-stu-id="149b0-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="149b0-119">设置管道属性</span><span class="sxs-lookup"><span data-stu-id="149b0-119">To set a pipeline property</span></span>  
  
1. <span data-ttu-id="149b0-120">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击使用你要设置其属性的管道的接收位置或发送端口。</span><span class="sxs-lookup"><span data-stu-id="149b0-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="149b0-121">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="149b0-121">Click **Properties**.</span></span>  
  
2. <span data-ttu-id="149b0-122">单击你要设置其属性的管道旁的省略号按钮 (…)。</span><span class="sxs-lookup"><span data-stu-id="149b0-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3. <span data-ttu-id="149b0-123">为属性输入值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="149b0-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149b0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="149b0-124">See Also</span></span>  
 [<span data-ttu-id="149b0-125">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="149b0-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)