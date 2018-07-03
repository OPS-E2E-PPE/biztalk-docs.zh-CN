---
title: 删除使用规则验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e5ffc3e1ca36e200055a26e8e78f341b125d8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975542"
---
# <a name="removing-usage-rule-validation"></a><span data-ttu-id="0afae-102">删除使用规则验证</span><span class="sxs-lookup"><span data-stu-id="0afae-102">Removing Usage Rule Validation</span></span>
<span data-ttu-id="0afae-103">SWIFT 标准中定义并强制实施使用规则[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]特定于每种消息类型的业务策略。</span><span class="sxs-lookup"><span data-stu-id="0afae-103">Usage rules are defined in SWIFT standards and enforced by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business policies specific to each message type.</span></span> <span data-ttu-id="0afae-104">这些使用规则是可用于提供额外的字段的验证的指南。</span><span class="sxs-lookup"><span data-stu-id="0afae-104">These usage rules are guidelines that you can use to provide extra validation for a field.</span></span> <span data-ttu-id="0afae-105">与不同的是网络验证规则，这是必需的您可以选择不需要使用规则的消息类型。</span><span class="sxs-lookup"><span data-stu-id="0afae-105">Unlike network validation rules, which are mandatory, you can choose not to require usage rules for a message type.</span></span> <span data-ttu-id="0afae-106">如果是这样，您可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="0afae-106">If that is the case, you can do either of the following:</span></span>  

-   <span data-ttu-id="0afae-107">可以删除特定的业务规则强制执行消息类型验证策略的使用情况规则。</span><span class="sxs-lookup"><span data-stu-id="0afae-107">You can remove a specific business rule that enforces a usage rule from the message-type validation policy.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="0afae-108">从策略中删除一个规则将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="0afae-108">Removing a rule from the policy will remove it permanently.</span></span>  

-   <span data-ttu-id="0afae-109">如果您不想要强制实施任何使用规则，可以取消部署消息类型的验证策略。</span><span class="sxs-lookup"><span data-stu-id="0afae-109">If you do not want to enforce any of the usage rules, you can undeploy the validation policy for a message type.</span></span>  

### <a name="to-remove-a-rule-from-a-policy"></a><span data-ttu-id="0afae-110">若要从策略中删除规则</span><span class="sxs-lookup"><span data-stu-id="0afae-110">To remove a rule from a policy</span></span>  

1.  <span data-ttu-id="0afae-111">在文本编辑器中，（如记事本） 打开的验证策略，你想要更改，例如，在 MT103_Validation_Policy *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。</span><span class="sxs-lookup"><span data-stu-id="0afae-111">In a text editor, such as Notepad, open the validation policy that you want to change, for example, MT103_Validation_Policy in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span>  

2.  <span data-ttu-id="0afae-112">删除规则节点，不想，然后保存策略。</span><span class="sxs-lookup"><span data-stu-id="0afae-112">Remove the rule node that you do not want, and then save the policy.</span></span>  

3.  <span data-ttu-id="0afae-113">使用业务规则引擎部署向导来发布和部署策略。</span><span class="sxs-lookup"><span data-stu-id="0afae-113">Use the Business Rules Engine Deployment Wizard to publish and deploy the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="0afae-114">您也可以通过创建策略的复制、 删除特定的规则，并将部署已修改的策略验证策略中删除规则。</span><span class="sxs-lookup"><span data-stu-id="0afae-114">You can also remove a rule from a validation policy by creating a copy of the policy, removing the specific rule, and then deploying the modified policy.</span></span> <span data-ttu-id="0afae-115">取消部署策略的上一版本。</span><span class="sxs-lookup"><span data-stu-id="0afae-115">Undeploy the previous version of the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="0afae-116">在业务规则编辑器中，不能从已发布或已部署的策略中删除规则。</span><span class="sxs-lookup"><span data-stu-id="0afae-116">In Business Rule Composer, you cannot delete a rule from a published or deployed policy.</span></span>  

### <a name="to-remove-the-policy-for-a-message-type"></a><span data-ttu-id="0afae-117">若要删除的消息类型的策略</span><span class="sxs-lookup"><span data-stu-id="0afae-117">To remove the policy for a message type</span></span>  

1. <span data-ttu-id="0afae-118">单击**启动**，依次指向**程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="0afae-118">Click **Start**, point to **Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  

2. <span data-ttu-id="0afae-119">在策略浏览器中对于消息类型，例如，MT103_Validation_Policy 查找已部署的验证策略。</span><span class="sxs-lookup"><span data-stu-id="0afae-119">In Policy Explorer, find the deployed validation policy for the message type, for example, MT103_Validation_Policy.</span></span>  

3. <span data-ttu-id="0afae-120">右键单击该策略，单击**Undeploy**，单击**删除**，然后单击**是**。</span><span class="sxs-lookup"><span data-stu-id="0afae-120">Right-click the policy, click **Undeploy**, click **Delete**, and then click **Yes**.</span></span>
