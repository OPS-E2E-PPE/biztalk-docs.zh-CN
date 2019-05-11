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
ms.openlocfilehash: 7b8168af5ba8d9fbb242833011bfb0d9a51bdd96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391354"
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="7555b-102">配置 AS2 管道属性</span><span class="sxs-lookup"><span data-stu-id="7555b-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="7555b-103">将使用管道属性处理传入或传出 AS2 消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定解析为发送或接收交换的协议。</span><span class="sxs-lookup"><span data-stu-id="7555b-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7555b-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="7555b-104">Prerequisites</span></span>  
 <span data-ttu-id="7555b-105">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="7555b-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="7555b-106">AS2 管道属性</span><span class="sxs-lookup"><span data-stu-id="7555b-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="7555b-107">可以在 AS2 管道中设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="7555b-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="7555b-108">属性</span><span class="sxs-lookup"><span data-stu-id="7555b-108">Property</span></span>|<span data-ttu-id="7555b-109">改用</span><span class="sxs-lookup"><span data-stu-id="7555b-109">Use</span></span>|<span data-ttu-id="7555b-110">值</span><span class="sxs-lookup"><span data-stu-id="7555b-110">Values</span></span>|<span data-ttu-id="7555b-111">管道/阶段</span><span class="sxs-lookup"><span data-stu-id="7555b-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="7555b-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="7555b-112">ContentTransferEncoding</span></span>|<span data-ttu-id="7555b-113">指示将使用哪种方法表示 ASCII 文本格式的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="7555b-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="7555b-114">8 位 （默认值）</span><span class="sxs-lookup"><span data-stu-id="7555b-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="7555b-115">7bit</span><span class="sxs-lookup"><span data-stu-id="7555b-115">7bit</span></span><br /><br /> <span data-ttu-id="7555b-116">8bit</span><span class="sxs-lookup"><span data-stu-id="7555b-116">8bit</span></span>|<span data-ttu-id="7555b-117">AS2EdiSend/编码</span><span class="sxs-lookup"><span data-stu-id="7555b-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="7555b-118">AS2Send/编码</span><span class="sxs-lookup"><span data-stu-id="7555b-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="7555b-119">若要设置管道属性</span><span class="sxs-lookup"><span data-stu-id="7555b-119">To set a pipeline property</span></span>  
  
1. <span data-ttu-id="7555b-120">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置的属性的管道。</span><span class="sxs-lookup"><span data-stu-id="7555b-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="7555b-121">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="7555b-121">Click **Properties**.</span></span>  
  
2. <span data-ttu-id="7555b-122">单击你想要设置的属性的管道旁的省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="7555b-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3. <span data-ttu-id="7555b-123">为属性输入值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7555b-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7555b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7555b-124">See Also</span></span>  
 [<span data-ttu-id="7555b-125">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="7555b-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)